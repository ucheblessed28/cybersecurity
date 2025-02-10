
---

## **Week 2: Understanding Cyber Threats & Linux Basics**  

### **Lesson 1: Deep Dive into Cyber Threats**  
In Week 1, we introduced common cyber threats. Now, let’s break them down in more detail.  

### **1. Malware (Malicious Software)**
Malware is software designed to harm, exploit, or disrupt systems.  

#### **Types of Malware:**
- **Virus** – Attaches to a file and spreads when executed.  
- **Worm** – Self-replicates across networks.  
- **Trojan Horse** – Disguises itself as a legitimate program.  
- **Spyware** – Secretly collects user information.  
- **Ransomware** – Encrypts files and demands payment to unlock them.  

#### **Example: WannaCry Ransomware Attack (2017)**
- Exploited a Windows vulnerability to encrypt files worldwide.  
- Affected **hospitals, banks, and businesses**.  
- Stopped by a **security researcher who found a "kill switch" domain**.  

🔹 **Defense Against Malware:**  
- Install and update **antivirus software** (e.g., Windows Defender, Bitdefender).  
- **Don’t open unknown attachments** in emails.  
- Keep **operating systems and software updated**.  

---

### **2. Phishing Attacks**
Phishing is when an attacker tricks someone into providing sensitive information (e.g., passwords, credit card details).  

#### **Common Types of Phishing:**
- **Email Phishing** – Fake emails pretending to be from trusted sources.  
- **Spear Phishing** – Targeted attacks aimed at specific individuals.  
- **Smishing & Vishing** – Phishing via SMS (Smishing) and Voice Calls (Vishing).  

#### **Example: 2020 Twitter Hack**
- Hackers used **spear phishing** to gain access to **high-profile accounts** (Elon Musk, Obama, etc.).  
- Sent fake tweets asking for Bitcoin donations.  

🔹 **Defense Against Phishing:**  
- Don’t click on **suspicious email links**.  
- Verify sender addresses before responding.  
- Use **Multi-Factor Authentication (MFA)** for extra security.  

---

### **3. Denial of Service (DoS) & Distributed Denial of Service (DDoS) Attacks**
These attacks **overload** a system with traffic, making it **slow or completely unavailable**.  

#### **Example: GitHub DDoS Attack (2018)**
- GitHub was hit with **1.3 terabits per second** of traffic!  
- Attackers used **botnets** to flood GitHub’s servers.  

🔹 **Defense Against DDoS:**  
- Use **firewalls** and **Intrusion Prevention Systems (IPS)**.  
- Deploy **DDoS protection services** like Cloudflare.  

---

### **Lesson 2: Introduction to Linux for Cybersecurity**
Linux is widely used in cybersecurity because it gives users more control over their system.  

### **1. Linux Distributions for Cybersecurity**
- **Kali Linux** – Best for penetration testing.  
- **Parrot Security OS** – Lightweight alternative to Kali Linux.  
- **Ubuntu** – Good for cybersecurity beginners.  

### **2. Basic Linux Commands (Must-Know)**
| **Command** | **Description** |
|------------|----------------|
| `pwd` | Shows current directory. |
| `ls` | Lists files in a directory. |
| `cd` | Changes directory. |
| `mkdir` | Creates a new folder. |
| `rm` | Deletes a file. |
| `rmdir` | Deletes an empty directory. |
| `cp` | Copies files. |
| `mv` | Moves files. |
| `nano` or `vim` | Opens a text editor. |
| `chmod` | Changes file permissions. |
| `chown` | Changes file ownership. |
| `ifconfig` / `ip a` | Shows network information. |
| `ping` | Tests connectivity to a server. |
| `netstat -an` | Shows active connections. |
| `ps aux` | Lists running processes. |

🔹 **Practical Exercise:**  
1. Open **Kali Linux** or any Linux terminal.  
2. Run the command: `ls` (This will list files in the current directory).  
3. Create a test folder: `mkdir test_folder`  
4. Move into the folder: `cd test_folder`  
5. Create a file: `touch myfile.txt`  
6. Edit the file: `nano myfile.txt` (Type something and save with `CTRL + X`, `Y`, and `Enter`).  
7. Check network information: `ip a`  

---

### **Practical Session 2: Linux Security Hardening**
Now, let’s learn how to **secure a Linux system**.  

#### **1. Updating Your System**
Run:  
```bash
sudo apt update && sudo apt upgrade -y
```
This updates all software and security patches.  

#### **2. Managing User Accounts**
- Add a new user:  
  ```bash
  sudo adduser newuser
  ```
- Change a user's password:  
  ```bash
  sudo passwd newuser
  ```
- Delete a user:  
  ```bash
  sudo deluser newuser
  ```

#### **3. File Permissions**
- View file permissions:  
  ```bash
  ls -l
  ```
- Change file permissions:  
  ```bash
  chmod 600 myfile.txt
  ```
  (This makes the file **only readable/writable by the owner**).  

---

### **Assignment 2: Hands-on Linux Practice**
1. **Create a new user** and **assign them a password**.  
2. **Create a file**, change its **permissions**, and make it **read-only**.  
3. **List all running processes** using:  
   ```bash
   ps aux
   ```
   Identify any suspicious processes.  

---

### **End of Week 2 Summary**
✅ Learned about **different cyber threats** and **real-world attack examples**.  
✅ Understood **how to defend against malware, phishing, and DDoS attacks**.  
✅ Gained **hands-on experience with Linux commands**.  
✅ Practiced **basic security hardening techniques** in Linux.  

---

### **Next Lesson (Week 3) Preview: Network Security & Ethical Hacking Basics**
In the next lesson, we will:  
- Learn **network security principles**.  
- Perform **basic penetration testing** with **Nmap** and **Wireshark**.  
- Understand how hackers **scan for vulnerabilities**.  
