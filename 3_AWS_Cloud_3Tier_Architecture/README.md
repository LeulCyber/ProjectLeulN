# AWS Cloud Security: 3-Tier Architecture Implementation

This section showcases a secure AWS deployment using a classic 3-tier architecture model: Web, App, and DB. The design emphasizes network segmentation, least privilege, and monitoring using native AWS tools, such as CloudTrail and GuardDuty. This simulation demonstrates both architectural planning and hands-on implementation with validated screenshots.

---

## 🎯 Objectives

- Deploy a secure Virtual Private Cloud (VPC) with public/private subnet isolation
- Create secure routing via route tables, internet gateway, and NAT
- Launch and configure EC2 instances in appropriate tiers
- Apply Security Groups with tight ingress/egress rules per layer
- Validate connectivity and simulate inter-tier communication
- Monitor activity with CloudTrail and GuardDuty

---

## 🛠️ Architecture Overview


- Public Subnet: Accessible via SSH; holds the web server
- Private Subnet: Hosts application and (simulated) database tier
- Security Groups: Define strict access (e.g., only Web ↔ App, no public DB)
- Monitoring Tools: CloudTrail (logs), GuardDuty (threat detection)

---

## 📸 Screenshots and Descriptions

| Step | Description | Screenshot |
|------|-------------|------------|
| 1    | VPC and Subnet configuration | `VPC_And_Subnets.png` ✅ |
| 2    | Internet Gateway attached to VPC | `Internet_Gateway_Attached.png` ✅ |
| 3    | Route Table for public subnet (with IGW route) | `Route_Table_Public_Subnet.png` ✅ |
| 4    | Security Groups showing inbound/outbound rules | `Security_Groups_Overview.png` ✅ |
| 5    | EC2 instance launch details (web/app) | `EC2_Instance_Details.png` ✅ |
| 6    | SSH into EC2 web server for verification | `SSH_Into_Web_Server.png` ✅ |
| 7    | Web server reachable in browser (public IP) | `Web_Server_Reachable.png` ✅ |
| 8    | curl command from web to app tier (internal ping) | `Curl_Web_To_App_Success.png` ✅ |
| 9    | GuardDuty detecting threats and findings | `GuardDuty_Findings.png` |
| 10   | CloudTrail logging activity to S3 bucket | `CloudTrail_Logs_S3_Bucket.png` |

---

## 🔐 Security Controls Applied

- Segmentation: Web/App/DB isolation using subnets
- Least Privilege: Security Groups restrict traffic between layers
- Monitoring: GuardDuty alerts on malicious activity, CloudTrail audits changes
- No Public DB Access: Database tier remains fully internal
- SSH only to Web Tier: Jump-box-style access

---

## 📁 Files & Screenshots in This Folder

📂 Screenshots/  
├── VPC_And_Subnets.png  
├── Internet_Gateway_Attached.png  
├── Route_Table_Public_Subnet.png  
├── Security_Groups_Overview.png  
├── EC2_Instance_Details.png  
├── SSH_Into_Web_Server.png  
├── Web_Server_Reachable.png  
├── Curl_Web_To_App_Success.png  
├── GuardDuty_Findings.png  
└── CloudTrail_Logs_S3_Bucket.png

---

## 🧠 Learning Outcome

This section demonstrates:

- Competence in AWS core services: VPC, EC2, IAM, GuardDuty, CloudTrail
- Infrastructure-as-Security mindset: proactive controls in design
- Real-world understanding of layered security
- Mapping of cloud architecture to common compliance goals (HIPAA, NIST, ISO 27001)

**Mapped to NIST SP 800-53 & CIS Controls v8:**

- AC-4 (Information Flow Enforcement)  
- SC-7 (Boundary Protection)  
- AU-12 (Audit Generation)  
- SI-4 (Information System Monitoring)  
- CIS Control 3: Data Protection  
- CIS Control 4: Secure Configuration  
- CIS Control 13: Network Monitoring

