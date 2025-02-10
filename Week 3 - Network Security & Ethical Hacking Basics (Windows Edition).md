
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

### **What is ARP (Address Resolution Protocol)?**  

**ARP (Address Resolution Protocol)** is a network protocol used to map an **IP address** to a **MAC (Media Access Control) address** in a **local network (LAN)**.  

#### **Why is ARP Needed?**
Computers communicate using **IP addresses** (e.g., `192.168.1.10`), but data packets are actually sent using **MAC addresses** (e.g., `00:1A:2B:3C:4D:5E`).  
Since IP addresses are logical and can change, ARP is required to **resolve** or **translate** an IP address into a MAC address so that data can be sent correctly.

---

## **How ARP Works (Step-by-Step)**
When a device wants to communicate with another device on the same network:  

1. **The sender checks its ARP cache** to see if it already knows the MAC address for the destination IP.  
2. **If the MAC address is unknown**, the sender broadcasts an **ARP Request**:  
   - Example: *"Who has IP `192.168.1.10`? Tell me your MAC address!"*  
3. **The device with that IP responds with an ARP Reply**:  
   - Example: *"I am `192.168.1.10`, and my MAC is `00:1A:2B:3C:4D:5E`."*  
4. **The sender stores the MAC address in its ARP cache** for future communication.  

---

## **Check ARP Entries in Windows**
Run the following command in **Command Prompt (CMD)**:
```cmd
arp -a
```
🔹 This lists all the IP-to-MAC mappings in your ARP table.

Example Output:
```
Interface: 192.168.1.5 --- 0x8
  Internet Address    Physical Address    Type
  192.168.1.1        00-14-22-01-23-45   dynamic
  192.168.1.10       00-1A-2B-3C-4D-5E   dynamic
```

---

## **Types of ARP Entries**
| Type | Description |
|------|------------|
| **Dynamic ARP** | Created automatically when a device communicates on the network. |
| **Static ARP** | Manually assigned MAC-to-IP mapping (persistent across reboots). |

🔹 **To add a static ARP entry in Windows**, use:  
```cmd
arp -s 192.168.1.10 00-1A-2B-3C-4D-5E
```

---

## **ARP Spoofing Attack**
🔴 **What is ARP Spoofing?**  
Attackers send **fake ARP replies** to trick devices into sending data to the attacker instead of the intended recipient.

**Example:**
1. The attacker sends a fake ARP message:  
   - *"I am the router (192.168.1.1), my MAC is `AA-BB-CC-DD-EE-FF`."*  
2. The victim updates its ARP cache with the attacker's MAC.  
3. The victim unknowingly sends traffic **through the attacker**.

✅ **Prevention:**
- Use **ARP Spoofing detection tools** like **XArp**.  
- Enable **static ARP entries** for critical devices.  
- Use **VPNs or encrypted communication** to protect data.  

---

### **Practical ARP Scan on Windows**  
We’ll perform an **ARP scan** to list all devices connected to the local network and their corresponding MAC addresses.

---

### **🔹 Step 1: Open Command Prompt**
1. Press **`Win + R`**, type **`cmd`**, and press **Enter**.
2. Type the following command to display your network configuration:
   ```cmd
   ipconfig
   ```
3. Find your **Default Gateway** (e.g., `192.168.1.1`).  
   This is the IP address of your router.

---

### **🔹 Step 2: Perform an ARP Scan**
Now, run:
```cmd
arp -a
```
This will list all known IP-to-MAC address mappings on your network.

**Example Output:**
```
Interface: 192.168.1.5 --- 0x8
  Internet Address    Physical Address    Type
  192.168.1.1        00-14-22-01-23-45   dynamic
  192.168.1.10       00-1A-2B-3C-4D-5E   dynamic
  192.168.1.15       00-25-90-3F-7A-9B   dynamic
```
- **Internet Address** → IP of devices on the network  
- **Physical Address** → Corresponding MAC addresses  
- **Type** → *Dynamic* (learned automatically) or *Static* (manually assigned)  

---

### **🔹 Step 3: Scan the Entire Network**
You can use **ping** to scan all devices in your subnet:
```cmd
for /l %i in (1,1,254) do @ping -n 1 192.168.1.%i | find "Reply"
```
🔹 This will ping every IP from `192.168.1.1` to `192.168.1.254` and list the ones that reply.

---

### **🔹 Step 4: Refresh and Recheck ARP Table**
After scanning, re-run:
```cmd
arp -a
```
Now, new devices that responded to the ping should appear in your ARP table.

---

### **Bonus: Install a Graphical ARP Scanner (Optional)**
For a more detailed ARP scan, install **Advanced IP Scanner** (free tool):  
🔗 [Download Advanced IP Scanner](https://www.advanced-ip-scanner.com/)  

---

### **Step-by-Step Guide to Install and Use Advanced IP Scanner on Windows**

**Advanced IP Scanner** is a free and user-friendly tool to scan your network, show devices connected, and display their IP and MAC addresses.

---

### **🔹 Step 1: Download and Install Advanced IP Scanner**
1. Visit the official website:  
   [Download Advanced IP Scanner](https://www.advanced-ip-scanner.com/)

2. Click the **Download** button to get the installer file.

3. Once downloaded, **double-click** the installer to start the setup.

4. Follow the on-screen instructions to complete the installation.  
   - Click **Next** to accept the default settings.
   - Choose the installation location (you can leave it as the default).
   - Click **Install**.

---

### **🔹 Step 2: Launch Advanced IP Scanner**
1. After installation, launch **Advanced IP Scanner**.
   - You can search for it in the **Start Menu** or find it in your **Desktop**.

2. The main window will appear with a **Scan Range** box, where you can specify the network range to scan.

---

### **🔹 Step 3: Set Your IP Range**
1. **Find Your Network Range:**
   - Open **Command Prompt** and run:
     ```cmd
     ipconfig
     ```
   - Look for your **Default Gateway** (e.g., `192.168.1.1`), and **Subnet Mask** (e.g., `255.255.255.0`).
   
2. In the **Advanced IP Scanner** window:
   - Enter the network range based on your IP and Subnet Mask.  
     For example, if your gateway is `192.168.1.1` and your subnet mask is `255.255.255.0`, use:
     ```text
     192.168.1.1 - 192.168.1.254
     ```
   
---

### **🔹 Step 4: Start Scanning the Network**
1. Once the network range is set, click the **"Scan"** button.
   
2. The tool will start scanning your network, and you will see the list of devices connected, including:
   - **IP Address**
   - **MAC Address**
   - **Device Name** (if detected)

---

### **🔹 Step 5: Review Scan Results**
- **Connected Devices**: You’ll see a list of devices like your router, computers, printers, and other networked devices.
- **IP Address**: Each device’s IP address.
- **MAC Address**: Each device’s MAC address.
- **Device Name**: Some devices might show their hostnames (e.g., "Laptop", "Router").

---

### **🔹 Step 6: Export Scan Results (Optional)**
1. You can export the scan results for future reference:
   - Click **File** > **Export Results**.
   - Choose the format (CSV, HTML, or TXT) and save it.

---

### **🔹 Step 7: Additional Features**
- **Remote Shutdown**: Advanced IP Scanner also allows you to remotely shut down or wake up devices on your network (requires configuration).
- **Device Management**: You can **right-click** on any device to get options like **pinging** it, **opening its shared folders**, or **getting more information**.

---

### **🔹 Step 8: Review and Use the Data**
Now that you have a list of devices, you can:
1. **Check MAC and IP Addresses** of devices on your local network.
2. **Ensure no unauthorized devices** are connected to your network.
3. **Identify and verify devices** by their MAC addresses.

---

### **Important Notes:**
- **Admin Permissions**: Running the scan might require admin privileges on your computer, so make sure to allow permissions when prompted.
- **Local Network Only**: This tool works for local network scanning. It will not scan devices outside your network.

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

