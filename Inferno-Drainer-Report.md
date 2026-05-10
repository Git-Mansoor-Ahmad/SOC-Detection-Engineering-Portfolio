# 🕵️ Project Report: Inferno Drainer Crypto Fraud Detection
**Status:** Phase 3 Completion 🎯

### 1. Threat Overview
Inferno Drainer is a "Scam-as-a-Service" (SaaS) model that uses sophisticated phishing and Web3 protocol spoofing (Seaport, WalletConnect) to drain wallets.
* **Attack Vector:** Social Engineering (Discord/X) -> Phishing Site -> Wallet Approval.
* **Key Challenge:** The JavaScript payloads use randomized, high-entropy UUIDs to bypass signature-based detection.

### 2. Technical Analysis: The Entropy Problem
The malware generates a unique JavaScript filename for every "customer" using a **Universally Unique Identifier (UUID)**. 
* **Example Obfuscation:** `app-7b9e12a4-55c1-4d3b-92f1-66e88d2f1a94.js`
* **Behavior:** The script uses dynamic function construction and string concatenation to hide its C2 addresses.

### 3. Detection Engineering Logic (The "Blue Team" Fix)
Since the filenames are randomized, I implemented **Regex-based detection** to catch the pattern of the UUID rather than the filename itself.

#### 🛡️ Detection Rule 1: High-Entropy UUID Pattern
**Regex Logic:**
`[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}`

#### 🛡️ Detection Rule 2: Suspicious Node.js Execution
Monitoring for `node.exe` spawning `conhost.exe --headless` from temporary directories (T1027.004).
