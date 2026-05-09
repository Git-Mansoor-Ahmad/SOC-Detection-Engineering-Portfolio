# Detection Engineering Report: SideWinder APT / Inferno Drainer

## 1. Threat Profile
**Target Threat:** SideWinder APT (also known as Rattlesnake) / Inferno Drainer.
**Attack Vector:** This threat actor frequently utilizes malicious JavaScript payloads. These files are often obfuscated and renamed using randomized 32-character hexadecimal strings (MD5 patterns) to bypass basic signature-based security filters.

## 2. Detection Strategy
To identify these randomized payloads, I implemented a **Regular Expression (Regex)** detection strategy within the SIEM (Wazuh). Rather than looking for a specific filename, the SIEM monitors for the *pattern* of the filename, allowing us to catch "zero-day" or newly generated malicious scripts that follow the group's naming convention.

## 3. Technical Logic
I developed **Rule ID: 100005** to monitor file creation events. The core of the detection is the following Regex:

`[a-f0-9]{32}\.js`

**Logic Breakdown:**
* `[a-f0-9]`: Matches any hexadecimal character (numbers 0-9 and letters a-f).
* `{32}`: Specifically looks for a string that is exactly 32 characters long.
* `\.js`: Matches the `.js` file extension.

This ensures that only randomized 32-character JavaScript files are flagged, minimizing false positives from standard system scripts.

## 4. MITRE ATT&CK Mapping
* **Tactics:** Defense Evasion (TA0005)
* **Technique:** Obfuscated Files or Information (**T1027**)

## 5. Visual Evidence
The rule was validated using the Wazuh Ruleset Test tool. The logic successfully triggered a match against the test string `5f3c2e1a8b9d0c7e6f5a4b3d2e1f0a9b.js`.

![SideWinder Regex Match](Evidence/Rejix_Test_string.png)
