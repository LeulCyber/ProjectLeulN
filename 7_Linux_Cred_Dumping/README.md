# Red Team: Linux Credential Dumping with LaZagne

This section demonstrates how an attacker can extract saved credentials on a Linux system after gaining shell access. Using the LaZagne post-exploitation tool, we simulate a credential harvesting attack in a real-world penetration testing or Red Team scenario.

---

## 🔍 Objective

- Simulate post-compromise credential extraction on Linux
- Use open-source tooling to locate plaintext or cached credentials
- Highlight the importance of Linux hardening and secure credential storage

---

## 🛠️ Tools & Environment

- Attacker Machine: Kali Linux (VirtualBox)
- Target Machine: Ubuntu/Linux host (victim)
- Tool Used: [`LaZagne`](https://github.com/AlessandroZ/LaZagne)

Execution Method:
- Transferred `LaZagne` to the target system via SSH/SCP
- Executed LaZagne in various modules (e.g., browser, system, database)

---

## ⚙️ MITRE ATT&CK Mapping

| Technique | Description |
|----------|-------------|
| `T1003.008` | OS Credential Dumping: `/etc/shadow`, keyrings, plaintext files |
| `T1555.003` | Credentials from Web Browsers |
| `T1552.001` | Credentials in Files |
| `T1555.004` | Credentials from Password Managers |

---

## 📸 Key Step and Screenshot

| Step | Description | Screenshot |
|------|-------------|------------|
| 1    | LaZagne run on a Linux host revealing credentials | `LaZagne_Linux_Execution.png` |

---

## 🧠 Key Takeaways

- LaZagne is a powerful post-exploitation tool that retrieves credentials from multiple sources (browsers, databases, etc.).
- Many Linux systems contain credential artifacts that are easily retrievable without elevated permissions.
- Red Teamers use this to escalate access; Blue Teams must restrict software installation and file permissions.

---

## 🔐 Blue Team Detection

Detection Tips:
- Monitor for unauthorized binaries being executed (e.g., LaZagne, Mimikatz)
- Use `auditd`, `Sysmon for Linux`, or EDR tools to trace binary launches and unusual process behavior
- Monitor SCP/FTP uploads of binaries like LaZagne

---

## 📁 File in This Folder

📂 7_Linux_Cred_Dumping/
├── LaZagne_Linux_Execution.png

---

## 🧠 Learning Outcome

This section demonstrates your understanding of post-exploitation on Linux platforms. It highlights both the offensive use of tools like LaZagne and the importance of Linux credential hygiene from a defensive perspective.
