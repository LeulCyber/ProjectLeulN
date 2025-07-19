# Red Team: Persistence & Lateral Movement Simulation

This phase simulates post-compromise tactics where an adversary establishes persistence on a Windows machine and explores lateral movement techniques. It demonstrates the creation of malicious registry keys, abuse of Windows features (LOLBAS), and visibility through forensic tools like Osquery.

---

## 🔍 Objective

- Simulate Windows persistence using registry modifications
- Abuse native tools (`certutil`, `AlwaysInstallElevated`) for lateral movement
- Detect persistence and abuse using endpoint telemetry (Osquery)

---

## 🛠️ Tools & Environment

- Attacker Machine: Kali Linux
- Victim Machine: Windows Server 2019 (Domain Joined)
- Detection Platform: Osquery

Key Techniques Used:
- Registry Run Key modification
- LOLBAS abuse via `certutil`
- Privilege escalation via `AlwaysInstallElevated`
- Osquery for behavioral visibility

---

## ⚙️ MITRE ATT&CK Mapping

| Technique | Description |
|----------|-------------|
| `T1547.001` | Registry Run Key persistence |
| `T1218.009` | Signed binary proxy execution: `certutil` abuse |
| `T1548.002` | Bypass UAC using `AlwaysInstallElevated` |
| `T1057` | Process discovery via Osquery |
| `T1012` | Querying system information (registry) |

---

## 📸 Key Steps and Screenshots

| Step | Description | Screenshot |
|------|-------------|------------|
| 1    | Malicious registry key added to persist on reboot | `Registry_Persistence_Added.png` |
| 2    | Osquery used to detect new registry autorun key | `Osquery_Registry_Detection.png` |
| 3    | Osquery process list shows suspicious process running | `Osquery_Process_List.png` |
| 4    | `certutil` used to simulate malicious payload download | `Certutil_Simulation.png` |
| 5    | Osquery detects `certutil` execution activity | `Certutil_Detection_Osquery.png` |
| 6    | Enabled `AlwaysInstallElevated` for potential UAC bypass | `AlwaysInstallElevated_Enabled.png` |

---

## 🧠 Key Takeaways

- Registry-based persistence is simple and stealthy but detectable via proper monitoring.
- LOLBAS tools like `certutil.exe` are built into Windows and widely abused by adversaries.
- Osquery allows deep inspection of process behavior and registry state in real-time.
- UAC bypass misconfigurations like `AlwaysInstallElevated` remain common in mismanaged environments.

---

## 🔐 Blue Team Perspective

**Recommended Detection Tactics**:
- Monitor registry changes (especially `Run`, `RunOnce`)
- Detect usage of `certutil` or other LOLBAS binaries
- Watch for elevated installations without admin approval
- Cross-reference Sysmon logs and Osquery tables for correlation

---

## 📁 Files & Screenshots in This Folder

📂 Screenshots/
├── Registry_Persistence_Added.png  
├── Osquery_Registry_Detection.png  
├── Osquery_Process_List.png  
├── Certutil_Simulation.png  
├── Certutil_Detection_Osquery.png  
├── AlwaysInstallElevated_Enabled.png

---

## 🧠 Learning Outcome

This phase demonstrates that you understand how attackers maintain access after initial compromise and how to monitor/detect these tactics. Combining Red and Blue perspectives gives you a complete view of the threat lifecycle.
