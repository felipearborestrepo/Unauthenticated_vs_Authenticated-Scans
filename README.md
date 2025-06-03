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
![Created VM](./screenshots/1- Created VM Windows 10.png)

✅ **Disabled Windows Firewall** to allow scanning of internal services.  
![Firewall Disabled](./screenshots/2- Disabled Firewall inisde the VM.PNG)

---

## 📝 Phase 2: Unauthenticated Scan
✅ **Scan Setup in Tenable:**  
- ![Editing Scan](./screenshots/5- Editing the Unauthenticated Scan for a Internal Scan.png)
- ![Targeting IP](./screenshots/6- Targeting the private IP from the VM.png)

✅ **Scan Results:**  
- ![Results](./screenshots/9- Results from Unauthenticated Scan.png)
- ![Exported Results](./screenshots/10- Results Exported.png)

---

## 📝 Phase 3: Authenticated Scan
✅ **Enabled Authenticated Scan in Tenable:**  
- ![Modifying to Authenticated Scan](./screenshots/11- Modifying to a Authenticated Scan.png)
- ![Adding Credentials](./screenshots/12- Adding the Credentials for a Authenticated Scans.png)

✅ **Scan in Progress:**  
- ![Scan In Progress](./screenshots/13- Authenticate Scan in Progress.png)

✅ **Authenticated Scan Results:**  
- ![Results](./screenshots/14- Authenticated Scan Results.png)
- ![Exported Results](./screenshots/15- Exported Authenticated Scan Results.png)

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

## 🐍 Python Script
We created a script to **compare scan outputs** and identify common or unique vulnerabilities.  
Run it with:

```bash
pip install -r requirements.txt
python compare_scans.py
