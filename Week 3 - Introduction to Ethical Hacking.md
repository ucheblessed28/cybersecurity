

---

# **📌 Introduction to Ethical Hacking**
Ethical hacking is the practice of legally breaking into computers and devices to **test** and **improve security**. Ethical hackers, also known as **white-hat hackers**, use the same techniques as malicious hackers, but with permission from the organization to find vulnerabilities before the bad guys do.

---

## **1️⃣ What is Ethical Hacking?**
Ethical hacking involves **proactively testing** systems, networks, and applications for vulnerabilities **before attackers exploit them**. It follows these principles:  

🔹 **Legal Authorization** – Ethical hackers must have permission before hacking.  
🔹 **Well-Defined Scope** – They only test approved systems and networks.  
🔹 **Reporting Vulnerabilities** – They report findings to the company, not exploit them.  
🔹 **Confidentiality** – Ethical hackers keep discovered information private.  

💡 **Example:** Companies like Google and Facebook hire ethical hackers to find security flaws through **bug bounty programs**.

---

## **2️⃣ Types of Hackers**
Not all hackers are bad! They fall into these categories:

| **Type** | **Description** |
|----------|---------------|
| **White Hat (Ethical Hackers)** | Work legally to find vulnerabilities and help companies secure their systems. |
| **Black Hat (Malicious Hackers)** | Attack systems illegally to steal, disrupt, or destroy data. |
| **Gray Hat (Mixed-Intent Hackers)** | May break into systems without permission but report issues instead of exploiting them. |

💡 **Example:** A white-hat hacker might test a company's website for **SQL Injection**, while a black-hat hacker would use the same technique to **steal user data**.

---

## **3️⃣ The Ethical Hacking Process (Hacking Lifecycle)**
Ethical hacking follows a structured approach:

### **🔹 Step 1: Reconnaissance (Information Gathering)**
- This is the **first phase** where hackers collect information about the target.  
- Tools: **Google Dorking, Shodan, Whois, Maltego**  
- **Example:** Finding an organization's email format (`first.last@company.com`) for phishing attacks.

### **🔹 Step 2: Scanning (Identifying Vulnerabilities)**
- Hackers scan for **open ports**, services, and weaknesses.  
- Tools: **Nmap, Nessus, OpenVAS**  
- **Example:** Checking if a company’s web server has an outdated version of Apache that is vulnerable to attacks.

### **🔹 Step 3: Gaining Access (Exploitation)**
- The hacker **attacks the system** using **exploits** found in the scanning phase.  
- Tools: **Metasploit, SQLmap, Hydra**  
- **Example:** Exploiting weak passwords or unpatched software.

### **🔹 Step 4: Maintaining Access (Backdoors)**
- If an attacker gains access, they **install backdoors** to keep control.  
- Tools: **Netcat, Mimikatz, C2 Frameworks (Cobalt Strike, Empire)**  
- **Example:** Planting malware to regain access after a system reboot.

### **🔹 Step 5: Covering Tracks**
- The attacker deletes logs and hides their presence.  
- **Example:** Deleting command history on Linux (`history -c`) to erase evidence.

### **🔹 Step 6: Reporting & Remediation (Ethical Hackers Only)**
- Ethical hackers **document findings**, report issues, and suggest fixes.  
- **Example:** Telling a company, "Your website has an XSS vulnerability; here’s how to fix it."

---

## **4️⃣ Ethical Hacking Tools Overview**
| **Tool** | **Purpose** |
|----------|------------|
| **Kali Linux** | Ethical hacking OS with built-in tools. |
| **Nmap** | Scans networks and identifies open ports. |
| **Metasploit** | Exploitation framework for testing vulnerabilities. |
| **Wireshark** | Captures and analyzes network traffic. |
| **Burp Suite** | Web security testing for finding web vulnerabilities. |
| **Hydra** | Password-cracking tool for brute-force attacks. |

💡 **Windows Users:** Kali Linux tools can be used on **Windows Subsystem for Linux (WSL)** or through **VMware/VirtualBox**.

---

## **🔧 Practical Lab: Setting Up a Hacking Environment**
We'll set up a safe environment for testing.  

### **1️⃣ Install a Virtual Machine**
We'll use **VirtualBox** or **VMware** to run a hacking lab.

🔹 **Download VirtualBox** → [https://www.virtualbox.org/](https://www.virtualbox.org/)  
🔹 **Download Kali Linux** → [https://www.kali.org/downloads/](https://www.kali.org/downloads/)  

### **2️⃣ Install Kali Linux**
1️⃣ Open **VirtualBox**, click **New**, and name it "Kali Linux."  
2️⃣ Set RAM to **4GB+** (if possible).  
3️⃣ Select the Kali Linux **ISO** file and install.  
4️⃣ Follow on-screen instructions.  

💡 Once installed, we can run **Nmap, Metasploit, and Wireshark**.

---

## **🎯 What’s Next?**
Next, we’ll go deeper into **cyber threats** and hands-on ethical hacking, including:
✔ **Reconnaissance techniques**  
✔ **Port scanning with Nmap**  
✔ **Brute-force attacks**  

