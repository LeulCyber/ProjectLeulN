# 3_Network_Setup_and_Discovery

## 📌 Goal
Establish a functioning lab network between Kali Linux (attacker) and Windows 11 (victim) virtual machines, and confirm network visibility using enumeration and scanning tools.

## 🛠️ Tools Used
- `ipconfig` (Windows)
- `ifconfig` / `ip a` (Kali)
- `ping`
- `nmap`

## 🔎 Steps Performed

### 1. Verified IP Configuration on Kali Linux
- **Screenshot**: `Kali_IP_Config_Ping.png.png`
- Confirmed that Kali VM is assigned a valid IP address on the host-only adapter.
- Pinged the Windows target to ensure connectivity between VMs.

### 2. Verified IP Configuration on Windows
- **Screenshot**: `Win_IP_Config_Check.png.png`
- Used `ipconfig` to verify the Windows VM’s IP address within the expected subnet.

### 3. Performed Host Discovery with Nmap
- **Screenshot**: `nmap_host_discovery.png`
- Used `nmap -sn 192.168.x.0/24` to discover live hosts in the environment and validate communication.
- Identified the Windows target for further enumeration.

## ✅ Outcome
- Successful network setup confirmed with ping and IP visibility.
- Nmap verified the host’s presence and readiness for Red Team enumeration.

## 💼 Why This Matters to Hiring Managers
Demonstrates foundational Red Team setup skills, including:
- Virtual lab configuration
- Basic host enumeration
- Use of scanning tools in a controlled, ethical hacking environment

---

