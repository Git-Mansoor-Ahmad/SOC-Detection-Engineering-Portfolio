# 🗺️ Master Attack Timeline: The Unified Correlation View
**Objective:** Correlating multi-stage attack telemetry into a unified incident response narrative.

### 1. The Incident Lifecycle
This view demonstrates the progression from Initial Access to Impact, proving the effectiveness of the engineered detection rules.

| Attack Phase | Threat Actor/Malware | Detection Logic | Severity |
| :--- | :--- | :--- | :--- |
| **Initial Access** | SideWinder APT | XML Decoder (.lnk Execution) | High (Level 10) |
| **Impact/Action** | Blue Locker | XML Threshold (Mass File Creation) | Fatal (Level 12) |
| **Defense Evasion** | Inferno Drainer | Regex Pattern (Entropic JS UUIDs) | Critical (Level 11) |

### 2. Unified Dashboard Proof
![Master Correlation Dashboard](./Evidence/Evidence/Master_Correlation_Dashboard.png)

### 3. Cross-Track Validation
* **Attack Logs:** Verified against the raw logs 
* **Detection Efficacy:** 100% visibility across the TTPs mapped in the Phase 3 Matrix.
