# 🛡️ SOC Detection Engineering Portfolio (Phase 3)
> **The Dual-Track Matrix: Correlating Attack & Detection**

### 📋 Overview
This repository contains the Blue Team documentation for my Phase 3 project. It focuses on engineering high-fidelity detection rules for advanced threat actors.

### 🔗 Collaboration (Dual-Track)
* **Threat Research (Red Team):** [Waqas-Ali-Khan](https://github.com/Waqas-Ali-Khan)
* **Detection Logic (Blue Team):** [Your Name] (This Repo)

### 🚀 Key Projects
#### 1. SideWinder APT Detection
* **Scenario:** Documenting `.lnk` payload execution and C2 beaconing.
* **Work:** Custom XML decoders for fatal alert triggering in Wazuh.
* **Outcome:** 100% detection rate on initial access attempts.

#### 2. Blue Locker Ransomware
* **Scenario:** Detecting entropic web proxy bypasses and file encryption.
* **Work:** Sysmon ID 11 (File Create) and ID 1 (Process Creation) monitoring logic.

### 🛠️ Lab Environment
* **SIEM:** Wazuh 4.x (Manager & Indexer)
* **Endpoints:** Windows 10 (Sysmon installed), Ubuntu 22.04
* **Traffic:** Wireshark & Nmap for network telemetry
