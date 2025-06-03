# Unauthenticated_vs_Authenticated-Scans

This project compares the results of **unauthenticated** and **authenticated** vulnerability scans performed on a Windows 10 Virtual Machine in Azure.  
It demonstrates the critical importance of using authenticated scans to reveal deeper system vulnerabilities.

---

## ⚙️ Technology Utilized
- **Tenable.io** – Vulnerability scanning and management platform.
- **Azure Virtual Machines** – Windows 10 VM for scanning and target testing.
- **Windows Firewall** – Disabled for demonstration of unauthenticated scans.
- **PowerShell** – For VM configuration and environment setup.

---

## 📁 Project Structure

---

## 📝 Phase 1: VM Creation and Environment Setup
✅ **Created a Windows 10 VM** in Azure.  
![Created VM]![1- Created VM Windows 10](https://github.com/user-attachments/assets/2b6ef14b-5b2e-4a85-9918-d00c37218091)


✅ **Disabled Windows Firewall Inside VM** to allow scanning of internal services.  
![Firewall Disabled]![2- Disabled Firewall inisde the VM](https://github.com/user-attachments/assets/21b311a4-bbde-457a-ab61-63ddc67735fc)

---

## 📝 Phase 2: Unauthenticated Scan
✅ **Scan Setup in Tenable:**  
![4- Creating a Basic Scan in Tenable](https://github.com/user-attachments/assets/e65efcf7-e47d-4ac7-b62e-dd21c48279e4)
 ![5- Editing the Unauthenticated Scan for a Internal Scan](https://github.com/user-attachments/assets/ca9433b0-0f77-4ce8-b5f8-5a474f42c62a)
  ![6- Targeting the private IP from the VM](https://github.com/user-attachments/assets/5de6cb22-f2f5-4bff-afd5-50737229dd09)
  ✅ **Editing in the Discovery page to Custom, and enabling a fast network discovery:**
  ![7- Editing the Discovery page to Custom, and enabling a fast network discovery](https://github.com/user-attachments/assets/6f05294b-0d97-427e-b30b-6e056f6f5618)
    ✅ ** Unathenticated Scan in Progress:**
![8- Initiating Unauthenticated Scan](https://github.com/user-attachments/assets/9422b42c-0156-434e-bd8c-67451062adb1)

✅ **Scan Results:**  
![9- Results from Unauthenticated Scan](https://github.com/user-attachments/assets/02d38629-e94a-40b6-9ecf-2a515a4b5d09)
![10- Results Exported](https://github.com/user-attachments/assets/c2d05f6d-a4e9-456e-9a14-c05479dbf654)



---

## 📝 Phase 3: Authenticated Scan
✅ **Modifying to an Authenticated Scan in Tenable:**  
[11- Modifying to a Authenticated Scan](https://github.com/user-attachments/assets/e904b588-985f-4e60-a506-6eb01eb0ba78)

✅ **Adding the VM Credential for Authenticated Scan:** 
![12- Adding the Credentials for a Authenticated Scans](https://github.com/user-attachments/assets/b6f8f083-7963-45e3-ba44-21aaba230291)


✅ **Authenticated Scan in Progress:**  
![13- Authenticate Scan in Progress](https://github.com/user-attachments/assets/316d2ed8-686c-41a4-b65c-a43c6062e135)


✅ **Authenticated Scan Results:**  
![14- Authenticated Scan Results](https://github.com/user-attachments/assets/7fb84db0-dd97-4c02-a694-b2d28e12cbe7)
![15- Exported Authenticated Scan Results](https://github.com/user-attachments/assets/127a59d0-0c0a-4511-b651-20f8be2e6fd5)


---

## 💬 Group Meeting Chat
**Mock discussion to plan the next steps:**

> **Felipe (Security Engineer):** Hey team, I ran the unauthenticated scan on the VM and got six medium vulnerabilities, mostly around TLS, SSL, and SMB.  
> **John (SysAdmin):** That’s expected—no credentials means we miss local issues.  
> **Felipe:** Exactly. After enabling authenticated scans, I found 1 critical, 5 high, and 19 medium vulnerabilities.  
> **John:** Let’s prioritize critical and high findings for the next CAB meeting.  
> **Felipe:** Agreed! I’ll prepare a remediation plan for those.  

---

## 🔍 Comparison of Scan Results
| Metric                       | Unauthenticated Scan | Authenticated Scan |
|------------------------------|----------------------|--------------------|
| Critical Vulnerabilities     | 0                    | 1                  |
| High Vulnerabilities         | 0                    | 5                  |
| Medium Vulnerabilities       | 6                    | 19                 |
| Low Vulnerabilities          | 1                    | 3                  |
| Info/Low-Level Findings      | 29                   | 136                |
| **Total Vulnerabilities**    | 36                   | 164                |

Authenticated scans provide a more accurate view of system vulnerabilities and should be prioritized in enterprise environments.

---


