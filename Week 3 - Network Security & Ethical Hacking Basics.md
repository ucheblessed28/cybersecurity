
---

## **Week 3: Network Security & Ethical Hacking Basics**

### **Lesson 1: Introduction to Network Security**
A network is a collection of connected devices (computers, servers, routers) that communicate with each other. **Network security** ensures that communication remains **private, secure, and protected** from attacks.

### **1. Network Layers & Protocols**
The **OSI Model** explains how data moves through a network in 7 layers:  
| **Layer** | **Purpose** | **Example Protocols** |
|-----------|-------------|---------------------|
| 7 - Application | User interaction | HTTP, HTTPS, FTP, SSH |
| 6 - Presentation | Data translation & encryption | SSL, TLS |
| 5 - Session | Manages communication sessions | NetBIOS, RPC |
| 4 - Transport | Ensures data is sent correctly | TCP, UDP |
| 3 - Network | Routes data across networks | IP, ICMP |
| 2 - Data Link | Manages data transfer between devices | MAC, ARP |
| 1 - Physical | Physical network hardware | Ethernet, Wi-Fi |

#### **Key Network Concepts**
- **IP Address**: A unique address assigned to each device on a network (e.g., `192.168.1.1`).  
- **MAC Address**: A hardware address assigned to a device’s network interface.  
- **Subnetting**: Divides networks into smaller parts for efficiency.  
- **Ports**: Communication endpoints (e.g., **80** for HTTP, **443** for HTTPS, **22** for SSH).  

---

### **Lesson 2: Common Network Attacks**
🔹 Attackers target networks to **steal data**, **interrupt services**, or **gain unauthorized access**.  

#### **1. Man-in-the-Middle (MITM) Attack**
An attacker **intercepts communication** between two devices.  
✅ **Prevention**:  
- Use **HTTPS** (secure websites).  
- Enable **VPNs** for encryption.  
- Avoid using **public Wi-Fi** without security.

#### **2. Packet Sniffing**
Hackers use **sniffing tools** (like Wireshark) to **capture network traffic**.  
✅ **Prevention**:  
- Use **encrypted communication (SSL/TLS, SSH)**.  
- Set up **firewalls** and **intrusion detection systems (IDS)**.  

#### **3. ARP Spoofing**
Attackers trick a network by **sending fake ARP messages**, making devices send data to the wrong destination.  
✅ **Prevention**:  
- Use **ARP spoofing detection tools**.  
- Enable **port security on switches**.  

---

### **Lesson 3: Practical Networking with Linux**
Let’s run some basic networking commands in **Linux**.  

#### **1. Check Your Network Configuration**
Run:  
```bash
ifconfig       # For older Linux versions
ip a           # For newer Linux versions
```
🔹 This shows your **IP address, MAC address, and network interfaces**.  

#### **2. Check Connectivity to a Website (Ping)**
Run:  
```bash
ping google.com
```
🔹 This checks if your system can **reach Google’s servers**.  

#### **3. Trace the Route to a Website**
Run:  
```bash
traceroute google.com
```
🔹 This shows the **path** your request takes before reaching Google.  

#### **4. Scan Open Ports on Your System**
Run:  
```bash
netstat -tulnp
```
🔹 This lists **all open ports** on your machine, which attackers could exploit.  

---

### **Lesson 4: Ethical Hacking Basics**
🔹 Ethical hackers **identify security flaws** before attackers do. They use **penetration testing** to simulate attacks and fix vulnerabilities.  

#### **1. Kali Linux Tools for Ethical Hacking**
- **Nmap** – Scans networks and finds open ports.  
- **Wireshark** – Analyzes network traffic.  
- **Metasploit** – Automates penetration testing.  

#### **2. Practical Exercise: Network Scanning with Nmap**
Nmap (Network Mapper) is a powerful tool used to **scan networks for open ports and vulnerabilities**.

##### **Install Nmap (if not installed)**
Run:  
```bash
sudo apt update && sudo apt install nmap -y
```

##### **Scan Your Network for Devices**
Run:  
```bash
nmap -sn 192.168.1.0/24
```
🔹 This scans **all devices** in your local network.  

##### **Scan a Specific IP for Open Ports**
Run:  
```bash
nmap -sS -p 1-1000 192.168.1.1
```
🔹 This checks **open ports** on the target system.  

##### **Check for Vulnerabilities**
Run:  
```bash
nmap --script vuln 192.168.1.1
```
🔹 This scans the target for known **security vulnerabilities**.  

---

### **Lesson 5: Packet Sniffing with Wireshark**
Wireshark captures and analyzes network packets in real-time.  

#### **1. Install Wireshark**
Run:  
```bash
sudo apt install wireshark -y
```

#### **2. Start Capturing Network Traffic**
- Open **Wireshark**.  
- Select your **network interface** (e.g., `eth0`, `wlan0`).  
- Click **Start Capture**.  

#### **3. Analyze Packets**
- Look for **HTTP traffic** (unencrypted websites).  
- Filter results using:  
  ```
  http.request
  ```
- Identify **source/destination IP addresses**.  

✅ **Prevention Against Packet Sniffing**:  
- Always use **HTTPS websites**.  
- Avoid sending **sensitive data** over public Wi-Fi.  

---

### **Assignment 3: Hands-on Network Security**
1. **Use Nmap** to scan your local network and list **all connected devices**.  
2. **Run Wireshark**, capture network traffic, and analyze packets.  
3. **List all open ports** on your system using `netstat -tulnp`.  
4. **Identify a website's IP address** using:  
   ```bash
   nslookup google.com
   ```
5. **Block a specific IP address** using:  
   ```bash
   sudo iptables -A INPUT -s 192.168.1.100 -j DROP
   ```

---

### **End of Week 3 Summary**
✅ Learned **network security fundamentals**.  
✅ Explored **common network attacks (MITM, DDoS, ARP spoofing, packet sniffing)**.  
✅ Practiced **Linux networking commands**.  
✅ Used **Nmap and Wireshark for ethical hacking**.  
✅ Completed **hands-on assignments for scanning networks and analyzing traffic**.  

---

### **Next Lesson (Week 4) Preview: Web Security & SQL Injection**
Next week, we will:  
- Learn **web application security principles**.  
- Perform **SQL injection attacks** and **prevent them**.  
- Explore **Cross-Site Scripting (XSS) and CSRF attacks**.  
