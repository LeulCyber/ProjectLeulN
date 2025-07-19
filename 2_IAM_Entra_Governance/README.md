# IAM Governance with Microsoft Entra ID (Azure AD)

This section of the portfolio demonstrates strong Identity and Access Management (IAM) governance using Microsoft Entra (formerly Azure AD). The artifacts and configurations shown here follow the principles of least privilege, Zero Trust, and regulatory alignment with NIST SP 800-53 and CIS Controls v8.

---

## 🎯 Objectives

- Define and assign roles based on the principle of least privilege
- Implement Conditional Access to reduce unauthorized access risks
- Enforce Multi-Factor Authentication (MFA) organization-wide
- Use Privileged Identity Management (PIM) for just-in-time access
- Document and demonstrate identity governance practices with screenshots

---

## 🛠️ Key Policies & Tools

- 'Role-Based Access Control (RBAC)'
- 'Conditional Access Policies'
- 'Privileged Identity Management (PIM)'
- 'Access Reviews'
- 'Multi-Factor Authentication (MFA)'

All configurations were implemented and verified in Microsoft Entra Admin Center (Azure AD).

---

## 📸 Screenshots and Descriptions

| Configuration | Description | Screenshot |
|---------------|-------------|------------|
| Conditional Access – Legacy Block | Blocks legacy apps that bypass MFA | `Conditional_Access_Block_Legacy.png` |
| Conditional Access – MFA Required | Requires MFA for all cloud app access | `Require_MFA_All_Users.png` |
| Global Admin Role Assignment | Shows assigned global admin (minimum personnel) | `Global_Admin_Assignment.png` |
| User Administrator Role Assignment | Delegates user admin rights to HR (Alice) | `User_Admin_Role_Assignment.png` ✅ |
| PIM Role Configuration | Enables just-in-time activation for privileged roles | `PIM_Configuration.png` |
| Access Review Setup | Review setup for access certifications | `Access_Review_Setup.png` |

---

## 📋 Governance Artifacts

- 'IAM_Governance_Policy_Leul.pdf' 
  Defines the access control policy, segregation of duties, and least privilege expectations.

- 'Conditional_Access_Policy.pdf'  
  Contains screenshots and configuration details for policies that enforce MFA and block legacy authentication.

---

## 🔐 Security Benefits

- Least privilege RBAC minimizes attack surface
- PIM prevents standing administrative privileges
- Conditional Access reduces risk of token replay, phishing
- Access reviews and MFA help meet compliance with HIPAA, NIST SP 800-53, and CIS v8

---

## 📁 Files in This Folder

📄 IAM_Governance_Policy_Leul.pdf  
📄 Conditional_Access_Policy.pdf  

📂 Screenshots/
├── Access_Review_Setup.png  
├── Conditional_Access_Block_Legacy.png  
├── Require_MFA_All_Users.png  
├── Global_Admin_Assignment.png  
├── User_Admin_Role_Assignment.png  
├── PIM_Configuration.png

---

## 🧠 Learning Outcome

By completing this section, you demonstrate the ability to:

- Implement secure IAM policies in Microsoft Entra ID
- Apply Zero Trust and least privilege principles
- Configure Conditional Access and PIM for compliance
- Communicate identity governance effectively with documentation

This directly maps to:
- NIST SP 800-53: AC-2, AC-5, AC-6, IA-2, IA-8
- CIS Controls v8: Control 5 (Account Management), Control 6 (Access Control Management)

