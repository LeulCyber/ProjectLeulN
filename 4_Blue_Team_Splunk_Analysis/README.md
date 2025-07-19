# Blue Team: Splunk Monitoring for Threat Detection

This section highlights real-time security monitoring using Splunk. Logs from Windows systems instrumented with Sysmon are ingested into Splunk to simulate a Security Operations Center (SOC) workflow. This demonstrates your ability to configure, analyze, and respond to key indicators of compromise (IOCs) and anomalous behavior across endpoints.

---

## 🎯 Objectives

- Monitor endpoint activity using Splunk and Sysmon
- Visualize logs from Windows Event Logs and Sysmon
- Detect malicious behaviors like suspicious process execution
- Simulate attacker behavior (Red Team) and confirm Blue Team visibility
- Create actionable insights from real-world attack signals

---

## 🛠️ Tools & Configuration

- SIEM Tool: Splunk Enterprise (local or trial instance)
- Log Source: Windows 11 VM with Sysmon installed
- Data Ingestion: Forwarder or direct import of EVTX/Sysmon logs
- Log Types:
  - `Event ID 1` — Process Creation
  - `Event ID 3` — Network Connections
  - `Event ID 7` — DLL Load
  - `Event ID 11` — File Creation

---

## 📸 Screenshots and Details

| Step | Description | Screenshot |
|------|-------------|------------|
| 1    | Splunk dashboard showing log source and filtering | `Splunk_Audit_Log_Monitoring.png` |
| 2    | Process creation detection with command-line details | `Splunk_Process_Creation_Monitoring.png` |
| 3    | Visual chart of detected patterns and activity spikes | `Splunk_Analytics_Chart.png` ✅ (renamed) |

---

## 🧠 Key Takeaways

- Splunk provides deep visibility into system-level activity, especially when combined with Sysmon
- Attack simulations generate real-world logs that SOC teams must triage
- Process creation logs help catch suspicious tools (e.g., `certutil`, `powershell`, `mimikatz`)
- Detection of DLL side-loading, registry persistence, or lateral movement patterns is enhanced by custom queries

---

## 🔐 Blue Team Detection Value

This lab aligns with MITRE ATT&CK and security monitoring best practices:

| Threat Behavior | Example | MITRE Technique |
|-----------------|---------|-----------------|
| Suspicious process | `powershell.exe -enc ...` | `T1059.001` |
| Remote execution | `psexec.exe`, `wmic` | `T1021` |
| Living Off The Land | `certutil.exe` | `T1218.010` |
| Registry modifications | Persistence attempts | `T1547` |

Splunk enables proactive detection when properly configured with filters, alerts, and dashboards.

---

## 📁 Files & Screenshots in This Folder

📂 `4_Blue_Team_Splunk_Analysis/`  
├── `README.md`  
├── `Splunk_Audit_Log_Monitoring.png`  
├── `Splunk_Process_Creation_Monitoring.png`  
└── `Splunk_Analytics_Chart.png` ✅

---

## 🧠 Learning Outcome

This section demonstrates:

- Proficiency with Splunk for log analysis and SIEM workflows
- Understanding of Blue Team operations and alerting logic
- Ability to link Red Team behavior to Blue Team detection
- Mapping of Sysmon events to MITRE and NIST response actions

Compliance & Framework Mapping:

- NIST SP 800-92: Guide to Computer Security Log Management  
- NIST SP 800-53: AU-6 (Audit Review), SI-4 (System Monitoring)  
- CIS Control 8: Audit Log Management  
- MITRE ATT&CK Detection coverage: Execution, Lateral Movement, Defense Evasion

