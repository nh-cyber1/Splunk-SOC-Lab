# 🛡️ Virtual SOC Lab: Splunk & Sysmon

## 📌 Project Overview
The goal of this project is to build a functional Security Operations Center (SOC) environment to simulate real-world cyber attacks and analyze them using Splunk.

📍 Phase 1: Infrastructure & Virtual Networking

Virtualization: Configured VMware/VirtualBox with an isolated host-only network (e.g., 10.0.0.0/24).
Endpoints: Deployed a Windows 11 Target and a Kali Linux Attack Node.
Static Addressing: Configured manual IP assignments to ensure consistent communication between nodes.

📍 Phase 2: Telemetry & Log Ingestion (The "Eyes")

Sysmon Deployment: Installed and configured Sysmon on the Windows target using a custom XML schema (like SwiftOnSecurity) to capture granular process and network data.
Splunk Installation: Set up Splunk Enterprise to act as the central SIEM.
Universal Forwarder (UF): Configured the Splunk UF on the Windows machine to ship logs (Security, System, and Sysmon) to the indexer.

📍 Phase 3: Defensive Hardening & Troubleshooting

Audit Policy Tuning: Enabled "Audit Logon Failure" via auditpol to ensure Windows actually records 4625 events.
Bypassing Security Baselines: Modified Windows registry and SMB settings to allow lab-based brute force testing while documenting why modern Windows defaults (Rate Limiting/Stealth Mode) block these attacks.
ACL & Permission Fixes: Resolved UF permission issues to allow the forwarder to read the Sysmon and Security event streams.

📍 Phase 4: Attack Simulation & Detection (Where you are now!)

Brute Force Attacks: Executed RDP and SMB brute force simulations using Hydra and NetExec.
Detection Engineering: Built Splunk queries to identify Event ID 4625 (Failed Logon) and differentiated between Local (Type 2) and Network (Type 3) logins.
Dashboarding: Created a real-time SOC dashboard to visualize the volume and source of incoming attacks.

Current PRogress:
[ ] Project: Detecting LSASS Memory Dumping

### 🌐 Network Topology
![Network Diagram](./network/NetworkDiagram.png)

"Configured static IP assignments for endpoint telemetry; currently utilizing a flat network topology with DNS resolution deferred to the local host for simplified log routing during Phase 1."
