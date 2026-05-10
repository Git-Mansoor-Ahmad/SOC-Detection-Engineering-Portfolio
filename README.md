# 🛡️ SOC Detection Engineering Portfolio
### 🚀 Key Projects
#### 1. SideWinder APT Detection
* **Scenario:** Documenting `.lnk` payload execution and C2 beaconing.
* **Work:** Custom XML decoders for fatal alert triggering in Wazuh.
* **Outcome:** 100% detection rate on initial access attempts.

#### 2. Blue Locker Ransomware
* **Scenario:** Detecting entropic web proxy bypasses and file encryption.
* **Work:** Sysmon ID 11 (File Create) and ID 1 (Process Creation) monitoring logic.
  
#### 3. Inferno Drainer Crypto Fraud
* **Scenario:** Identification of high-entropy JavaScript UUIDs used in drainer scripts.
* **Detection Logic:** Pattern-based detection using **Regular Expressions (Regex)** to catch randomized 32-character filenames.
* **Report:** [Inferno-Drainer-Analysis.md](./Reports/Inferno-Drainer-Analysis.md)

### 🏆 Elite Differentiator: Master Attack Timeline
* **[Unified Correlation View](./Master-Attack-Timeline.md):** A master dashboard showing the synchronized progression of Phishing -> PowerShell Hijacking -> C2 Beaconing -> Lateral Movement.
* **Verification:** All detections are verified against raw logs to ensure 100% visibility of the attack lifecycle.

### 🛠️ Technical Arsenal
* **SIEM/IDS:** Wazuh, ELK Stack, Splunk
* **Forensics:** Wireshark (TLS 1.3/DNS/HTTP analysis), Sysmon
* **Scripting:** Regular Expressions (Regex), Python, Bash
