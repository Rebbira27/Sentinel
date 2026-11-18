# Sentinel
# SentinelLab: Cyber Attack Detection & Incident Response Simulator

## 1. Project Information

**Description & Purpose:**
SentinelLab is an interactive blue team SOC (Security Operations Center) training and incident response platform. Its primary purpose is to provide students and analysts with a realistic environment to practice detecting and mitigating cyber attacks. By simulating multi-stage attacks, it bridges the gap between theoretical knowledge and practical defense skills.

**Key Features:**
*   **Concrete MITRE ATT&CK Chains:** Simulates realistic multi-stage attack scenarios, including:
    *   *Scenario 1:* Credential Stuffing & Account Takeover (Recon/Initial Access T1110.004 -> Valid Accounts T1078 -> Privilege Escalation T1068 -> Impact)
    *   *Scenario 2:* Lateral Movement & Data Exfiltration (Compromised Workstation -> Internal Port Scan -> Sensitive File Access -> Staged Upload)
*   **Formalized Correlation Engine:** Links events using composite entity keys (username, source_ip, asset_id) within a sliding time window (e.g., delta t <= 10 min). It uses a state machine to transition events from NORMAL -> SUSPICIOUS -> INCIDENT_CRITICAL.
*   **Actionable Incident Response (Simulated SOAR):**
    *   *Containment:* Isolate Host (LAB-PC-01), Terminate Active Sessions, Temporary IP Block.
    *   *Remediation:* Force Password Reset, Revoke Admin Role.
    *   *Feedback Loop:* Containment actions immediately block subsequent simulated events from that entity, logging them as BLOCKED_BY_POLICY.
*   **Objective Student Scoring:** Tracks Mean Time to Detect (MTTD) and Mean Time to Respond (MTTR), assesses root cause and scope accuracy, and applies penalties for false positives.
*   **Core Platform Modules:** Includes a Log Analysis & Normalization Engine, Detection Rules Manager, Incident Investigation Workspace, Training & CTF Scenarios, and Incident Reporting.


2. Team Information

*   Olifen Mulatu - CTC-1456-26
*   Yobsan Fufa - CTC-129-26
*   Rebira Fufa - CTC-1672-26
*   Bona Tesfa - CTC-441-26
*   Rebbira Gizachew - CTC-790-26
##3. Development Guide

To run this project locally, you will need Node.js and npm installed.

```bash
# Clone the repository
git clone https://github.com/Rebbira27/Sentinel

# Navigate into the directory
cd sentinel

# Install dependencies
npm install

# Run the development server
npm run dev