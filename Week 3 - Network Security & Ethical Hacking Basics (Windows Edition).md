
---

# **Week 3: Network Security & Ethical Hacking Basics (Windows Edition)**

## **Lesson 1: Introduction to Network Security**
Network security ensures **safe data transmission** across networks by **preventing unauthorized access** and attacks.

### **1. Network Layers & Protocols**
The **OSI Model** explains how data moves through a network:  

| **Layer** | **Purpose** | **Example Protocols** |
|-----------|-------------|---------------------|
| 7 - Application | User interaction | HTTP, HTTPS, FTP, SSH |
| 6 - Presentation | Data encryption & formatting | SSL, TLS |
| 5 - Session | Manages communication sessions | NetBIOS, RPC |
| 4 - Transport | Ensures data delivery | TCP, UDP |
| 3 - Network | Routes data across networks | IP, ICMP |
| 2 - Data Link | Transfers data between devices | MAC, ARP |
| 1 - Physical | Physical network connections | Ethernet, Wi-Fi |

---

### **Lesson 2: Common Network Attacks**
💀 Attackers exploit **vulnerabilities** to steal data or disrupt services.  

#### **1. Man-in-the-Middle (MITM) Attack**
Attackers **intercept network traffic** between two users.  
✅ **Prevention**:  
- Use **HTTPS** (encrypted websites).  
- Enable **VPNs** for encryption.  
- Avoid public Wi-Fi without security.  

#### **2. Packet Sniffing**
Attackers use **packet sniffers** to capture network traffic.  
✅ **Prevention**:  
- Use **SSL/TLS encryption** (HTTPS, SSH).  
- Enable **Windows Defender Firewall**.  

#### **3. ARP Spoofing**
Attackers trick networks into sending data to the wrong destination.  
✅ **Prevention**:  
- Use **ARP spoofing detection tools** (e.g., **XArp**).  
- Enable **firewall protection** in Windows Defender.  

---

## **Lesson 3: Windows Networking Commands**
📌 These commands work in **Command Prompt (CMD)** and **PowerShell**.

#### **1. Check Your Network Configuration**
Run in **CMD**:  
```cmd
ipconfig /all
```
🔹 Displays your **IP address, MAC address, and DNS settings**.

#### **2. Check Connectivity to a Website (Ping)**
Run in **CMD**:  
```cmd
ping google.com
```
🔹 Checks if your PC can **reach Google’s servers**.

#### **3. Trace the Route to a Website**
Run in **CMD**:  
```cmd
tracert google.com
```
🔹 Shows the **hops** your data takes before reaching Google.

#### **4. View Open Ports on Your PC**
Run in **PowerShell**:  
```powershell
netstat -ano
```
🔹 Lists all **open ports**, **active connections**, and **running services**.

#### **5. Find Devices on Your Network**
Run in **PowerShell**:  
```powershell
arp -a
```
🔹 Displays **all connected devices** on your network.

#### **6. Block a Specific IP Address**
Run in **PowerShell**:  
```powershell
New-NetFirewallRule -DisplayName "Block_IP" -Direction Inbound -Action Block -RemoteAddress 192.168.1.100
```
🔹 Blocks incoming traffic from **192.168.1.100**.

---

## **Lesson 4: Ethical Hacking Basics**
🛡 Ethical hackers **find security flaws** before attackers do.  

### **1. Install Essential Hacking Tools for Windows**
✅ **Nmap** – Scans networks & detects open ports.  
✅ **Wireshark** – Captures and analyzes network traffic.  
✅ **Metasploit** – Penetration testing framework.

---

## **Lesson 5: Network Scanning with Nmap (Windows)**
Nmap (Network Mapper) helps **scan networks** for devices, ports, and vulnerabilities.

### **1. Install Nmap on Windows**
1. **Download Nmap** from [nmap.org](https://nmap.org/download.html).  
2. Install **Nmap** and **Zenmap (GUI version)**.  
3. Open **Command Prompt (CMD)** and run:  
   ```cmd
   nmap --version
   ```
   ✅ If installed correctly, it will display the Nmap version.

### **2. Scan Your Local Network**
Run in **CMD**:  
```cmd
nmap -sn 192.168.1.0/24
```
🔹 Detects **all connected devices** in your network.

### **3. Scan a Specific IP for Open Ports**
Run in **CMD**:  
```cmd
nmap -sS -p 1-1000 192.168.1.1
```
🔹 Scans **first 1000 ports** of the target system.

### **4. Check for Vulnerabilities**
Run in **CMD**:  
```cmd
nmap --script vuln 192.168.1.1
```
🔹 Scans for **security vulnerabilities**.

---

## **Lesson 6: Packet Sniffing with Wireshark**
Wireshark **captures and analyzes network packets**.

### **1. Install Wireshark on Windows**
1. **Download Wireshark** from [wireshark.org](https://www.wireshark.org/download.html).  
2. Install with **WinPcap** (required for network capturing).  
3. Open **Wireshark**.

### **2. Start Capturing Network Traffic**
1. Select your **network interface** (e.g., **Wi-Fi, Ethernet**).  
2. Click **Start Capture**.  

### **3. Analyze Packets**
- Filter by **HTTP traffic** (unencrypted websites):  
  ```
  http.request
  ```
- Find **source/destination IP addresses**.  

✅ **Prevention Against Packet Sniffing**:  
- Always use **HTTPS websites**.  
- Avoid sending **passwords over public Wi-Fi**.

---

## **Assignment 3: Hands-on Network Security (Windows)**
1. **Use Nmap** to scan your network and list **all connected devices**.  
2. **Run Wireshark**, capture network traffic, and analyze packets.  
3. **List all open ports** on your system using `netstat -ano`.  
4. **Identify a website's IP address** using:  
   ```cmd
   nslookup google.com
   ```
5. **Block a suspicious IP address** using:  
   ```powershell
   New-NetFirewallRule -DisplayName "Block_IP" -Direction Inbound -Action Block -RemoteAddress 192.168.1.100
   ```

---

## **End of Week 3 Summary**
✅ Learned **network security fundamentals**.  
✅ Explored **common network attacks (MITM, DDoS, ARP spoofing, packet sniffing)**.  
✅ Practiced **Windows networking commands**.  
✅ Used **Nmap and Wireshark for ethical hacking**.  
✅ Completed **hands-on assignments for scanning networks and analyzing traffic**.  

---

## **Next Lesson (Week 4) Preview: Web Security & SQL Injection**
🔹 Learn **web security basics**.  
🔹 Perform **SQL injection attacks & prevention**.  
🔹 Explore **Cross-Site Scripting (XSS) and CSRF attacks**.  

---
