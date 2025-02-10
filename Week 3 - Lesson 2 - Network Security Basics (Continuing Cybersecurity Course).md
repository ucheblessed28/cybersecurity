## **Lesson 2: Network Security Basics (Continuing Cybersecurity Course)**  

Now that we’ve covered **ARP (Address Resolution Protocol)** and performed a practical **ARP scan**, let's move forward with **Network Security Basics**.  

### **🔹 What is Network Security?**
Network security refers to the **policies, practices, and technologies** used to protect the integrity, confidentiality, and accessibility of data and systems within a network. It prevents unauthorized access, cyberattacks, and data breaches.

---

## **🔹 Key Concepts of Network Security**
We will break it down into three main components:

| **Concept**   | **Description** |
|--------------|---------------|
| **Confidentiality** | Ensures that data is accessible only to authorized users (e.g., encryption, authentication). |
| **Integrity** | Ensures that data is not altered or tampered with (e.g., hashing, digital signatures). |
| **Availability** | Ensures that networks and systems remain accessible to authorized users (e.g., DDoS protection, redundancy). |

Now, let’s go through each component with examples.

---

## **🔹 1. Confidentiality (Protecting Data from Unauthorized Access)**
Confidentiality ensures that only the **intended recipient** can access data.  
Techniques used include:

1. **Encryption** – Scrambling data so only authorized parties can read it.
   - Example: **HTTPS (TLS/SSL) encrypts web traffic** to prevent hackers from intercepting data.
   - 🔥 **Practical:** We will install **Wireshark** later to analyze encrypted vs. unencrypted traffic.

2. **Authentication** – Verifying user identity using passwords, biometrics, or multi-factor authentication (MFA).
   - Example: **Logging into an email account with a password and OTP (One-Time Password).**

3. **Access Control** – Restricting data access based on user roles.
   - Example: **A company’s HR database should only be accessed by HR employees, not regular staff.**

---

## **🔹 2. Integrity (Preventing Data Manipulation)**
Data integrity ensures that information is **not modified, corrupted, or altered** in an unauthorized way.  
Techniques include:

1. **Hashing** – Converts data into a unique fixed-size value.
   - Example: **SHA-256 hashing is used in password storage and blockchain.**
   - 🔥 **Practical:** We will use Python later to generate a hash of a file.

2. **Digital Signatures** – Used to verify the authenticity of messages or files.
   - Example: **When you download software, it often comes with a digital signature to verify its authenticity.**

---

## **🔹 3. Availability (Ensuring Services Stay Online)**
Availability ensures that authorized users can always access the network and services when needed.  
Common threats include:

1. **DDoS (Distributed Denial of Service) Attacks**  
   - Attackers send massive amounts of traffic to a server to overwhelm and crash it.
   - Example: **A hacker sends millions of fake requests to an online store, causing it to go offline.**

2. **Redundancy & Backups**  
   - Keeping backup systems online in case of failure.
   - Example: **Banks have backup data centers to ensure services remain online.**

---

## **🔹 Practical Lab: Checking Network Connections in Windows**
Let’s check active **network connections** and **open ports** on a Windows machine.

### **Step 1: View Active Network Connections**
1. Open **Command Prompt** (`Win + R`, type `cmd`, press Enter).
2. Run the following command:
   ```cmd
   netstat -an
   ```
3. You will see a list of active network connections, showing:
   - **Local IP and Port** (e.g., `192.168.1.5:443` means your computer is using port `443` for HTTPS).
   - **Foreign Address** (shows the remote system connected to you).
   - **State** (`ESTABLISHED`, `LISTENING`, etc.).

### **Step 2: Identify Open Ports**
To check which **ports** your system is listening on:
```cmd
netstat -ano | find "LISTENING"
```
This will show all **listening ports** and their **process IDs (PIDs)**.

---

## **🔹 Homework Assignment:**
1. **Run the `netstat -an` command** and analyze the connections.
2. **Use `arp -a` again** and compare it with your previous results.
3. **Research on how encryption protects network traffic** and find examples of sites using HTTPS.

---

# **Lesson 3: Firewalls and Packet Filtering (Cybersecurity Course)**  

Now that we have covered **network security basics**, let’s move on to **firewalls**—one of the most important tools in cybersecurity.

---

## **🔹 What is a Firewall?**  
A **firewall** is a **security system** that monitors and controls incoming and outgoing network traffic based on **predefined security rules**. It acts as a **barrier** between your computer/network and the outside world (e.g., the internet), filtering traffic to prevent unauthorized access.

### **🔹 Why Do We Need a Firewall?**  
Firewalls help to:  
✅ Block unauthorized access to networks and devices.  
✅ Prevent malware, hacking attempts, and data breaches.  
✅ Control which applications can send/receive data.  
✅ Monitor and log network activity for security audits.  

---

## **🔹 Types of Firewalls**
There are different types of firewalls, each with its unique function.  

| **Firewall Type** | **Description** | **Example** |
|------------------|---------------|------------|
| **Packet Filtering Firewall** | Examines individual data packets and blocks/allows them based on rules. | **Windows Firewall** |
| **Stateful Inspection Firewall** | Monitors the state of active connections and makes intelligent filtering decisions. | **Cisco ASA, pfSense** |
| **Proxy Firewall** | Acts as an intermediary between a user and the internet, filtering malicious requests. | **Squid Proxy** |
| **Next-Generation Firewall (NGFW)** | Includes deep packet inspection, intrusion prevention, and advanced security features. | **Fortinet, Palo Alto** |

🔹 **For this course, we will focus on Packet Filtering Firewalls, especially Windows Firewall.**  

---

## **🔹 Understanding Packet Filtering (How Firewalls Work)**

### 🔹 **What is a Network Packet?**
A **packet** is a small chunk of data sent over the network. Every packet contains:  
📌 **Source IP** (where it came from)  
📌 **Destination IP** (where it's going)  
📌 **Protocol** (HTTP, HTTPS, FTP, etc.)  
📌 **Port Number** (e.g., 80 for HTTP, 443 for HTTPS)

Firewalls analyze these packets and decide whether to **allow** or **block** them based on rules.

---

## **🔹 How Windows Firewall Works**
Windows Firewall (also called **Windows Defender Firewall**) is a **built-in** security feature in Windows that **monitors and controls network traffic**.

🔹 **Key Functions of Windows Firewall:**
✅ **Block unauthorized incoming connections**  
✅ **Allow or block applications from accessing the internet**  
✅ **Monitor network activity for suspicious behavior**  

---

## **🔹 Practical Lab: Configuring Windows Firewall Rules**
Now, let’s **open Windows Firewall and configure a rule** to block or allow an application.

### **Step 1: Open Windows Firewall**
1️⃣ **Press `Win + R`**, type `wf.msc`, and press **Enter**.  
2️⃣ The **Windows Defender Firewall with Advanced Security** window will open.  
3️⃣ You’ll see three main profiles:  
   - **Domain Profile** (used in corporate networks)  
   - **Private Profile** (home or trusted networks)  
   - **Public Profile** (open Wi-Fi or untrusted networks)

---

### **Step 2: Create an Inbound Rule to Block an Application**
Let’s block a specific application (e.g., `chrome.exe`) from accessing the internet.

1️⃣ Click **Inbound Rules** in the left panel.  
2️⃣ Click **New Rule...** (on the right-hand side).  
3️⃣ Select **Program**, then click **Next**.  
4️⃣ Choose **This program path** and browse to the application (`chrome.exe`).  
5️⃣ Click **Next**, then select **Block the connection**.  
6️⃣ Choose where to apply the rule (**Private, Public, or Domain** networks).  
7️⃣ Name the rule (e.g., **Block Chrome Internet Access**) and click **Finish**.  

✅ **Now, Chrome won’t be able to access the internet!**  
To remove the block, find the rule and **disable or delete it**.

---

### **Step 3: Test Windows Firewall with Netstat**
Now, let's see which programs are allowed to connect to the internet.

1️⃣ Open **Command Prompt** (`Win + R`, type `cmd`, press Enter).  
2️⃣ Run the following command to list **all network connections**:
   ```cmd
   netstat -an
   ```
3️⃣ You’ll see a list of **open connections**, including:
   - Local and foreign IP addresses.
   - Ports in use.
   - Connection status (e.g., **ESTABLISHED, LISTENING**).

✅ **If an application is blocked by the firewall, it will not appear as an active connection.**

---

## **🔹 Practical Use Cases for Firewalls**
Here are some **real-world examples** where firewalls are used:

1️⃣ **Blocking Hackers:** Prevents unauthorized access to your network.  
2️⃣ **Preventing Malware:** Stops malicious software from connecting to remote servers.  
3️⃣ **Controlling Employee Access:** In a company, firewalls can block social media sites during work hours.  
4️⃣ **DDoS Protection:** Firewalls can mitigate excessive traffic to prevent service outages.  

---

## **🔹 Homework Assignment**
1️⃣ Open Windows Firewall (`wf.msc`) and **explore existing inbound and outbound rules**.  
2️⃣ Use **`netstat -an`** and write down three **active connections** on your PC.  
3️⃣ Research **Next-Generation Firewalls (NGFWs)** and how they differ from traditional firewalls.

---

## **🚀 Next Lesson: Installing and Using Wireshark for Network Traffic Analysis**
In the next lesson, we will install **Wireshark** and analyze real-time **network traffic** to see how data flows through a network.

---

# **Lesson 4: Installing and Using Wireshark for Network Traffic Analysis**  

Now that we have learned about **firewalls**, let’s take a deep dive into **network traffic analysis** using **Wireshark**, a powerful tool for monitoring and analyzing data packets.

---

## **🔹 What is Wireshark?**  
Wireshark is a **packet analyzer** that allows you to **capture, inspect, and analyze network traffic in real time**. It's widely used by cybersecurity professionals, network administrators, and ethical hackers to monitor network activity.

### **🔹 Why Use Wireshark?**  
✅ **Monitor network activity** in real time.  
✅ **Detect unauthorized access** or cyberattacks.  
✅ **Analyze security threats** like malware or suspicious traffic.  
✅ **Troubleshoot network issues** and performance bottlenecks.  
✅ **Inspect HTTP, DNS, and ARP packets** to understand how data flows.  

---

## **🔹 Installing Wireshark on Windows**  
Let’s install **Wireshark** and capture network traffic.

### **Step 1: Download and Install Wireshark**  
1️⃣ Visit the official website: 👉 **[https://www.wireshark.org/download.html](https://www.wireshark.org/download.html)**  
2️⃣ Download the **latest stable version** for Windows.  
3️⃣ Run the installer and follow these steps:  
   - **Select “Wireshark”** and click **Next**.  
   - When prompted, install **WinPcap** (this is required for capturing live network traffic).  
   - When prompted, install **Npcap** (this helps capture packets in Windows).  
   - Click **Finish** once installation is complete.  
4️⃣ Restart your PC to ensure Wireshark runs properly.

---

## **🔹 Wireshark Interface Overview**
When you open **Wireshark**, you’ll see:

📌 **Capture Interfaces** – A list of network adapters (Wi-Fi, Ethernet, etc.).  
📌 **Packet List Pane** – Displays captured packets in real time.  
📌 **Packet Details Pane** – Shows detailed information about a selected packet.  
📌 **Packet Bytes Pane** – Displays raw data of a selected packet in hexadecimal format.

---

## **🔹 Capturing Network Traffic in Wireshark**  
Let’s capture real-time network traffic.

### **Step 1: Start a Packet Capture**
1️⃣ **Open Wireshark.**  
2️⃣ Select your **active network adapter**:
   - **Wi-Fi** (for wireless connections).  
   - **Ethernet** (for wired connections).  
3️⃣ Click the **Shark Fin Icon** 🦈 (Start Capture) at the top.  
4️⃣ Open a **web browser** and visit any website (e.g., `https://www.google.com`).  
5️⃣ Wireshark will start capturing **network packets**.

---

## **🔹 Analyzing Captured Packets**
Now that we've captured network traffic, let's analyze it.

### **Step 1: Stop the Capture**
1️⃣ Click the **Red Square 🟥 (Stop Capture)** button.  
2️⃣ You’ll see a list of captured packets.

### **Step 2: Filter Packets**
Wireshark captures a LOT of data, so we use **filters** to find what we need.

| **Filter** | **Description** |
|-----------|---------------|
| `http` | Shows only HTTP traffic (web browsing) |
| `https` | Shows only secure HTTPS traffic |
| `tcp` | Displays TCP traffic (used in most communications) |
| `udp` | Displays UDP traffic (used in streaming, gaming) |
| `arp` | Shows ARP packets (used for MAC address resolution) |
| `icmp` | Displays ICMP (ping requests) |
| `ip.addr == 192.168.1.1` | Filters packets from a specific IP address |

#### **Example: Filtering HTTP Traffic**
1️⃣ In the **filter bar**, type:  
   ```
   http
   ```
2️⃣ Press **Enter** – Now you will only see **HTTP packets** (unencrypted web traffic).  
3️⃣ Click on any **HTTP packet**, then expand the "Hypertext Transfer Protocol" section to see the **website request details**.

---

## **🔹 Practical Lab: Capturing and Inspecting Packets**
### **🔹 Lab 1: Capture and Inspect Your Own Web Traffic**
1️⃣ Start a **Wireshark capture**.  
2️⃣ Open your web browser and visit `http://example.com`.  
3️⃣ In Wireshark, filter for `http`.  
4️⃣ Click on a **GET request** packet and inspect the details.  
5️⃣ Find the **Host field** (this shows the website you visited).  

🔴 **Note:** Modern websites use **HTTPS**, so HTTP requests might be limited. You can filter `https` traffic, but the data will be encrypted.

---

### **🔹 Lab 2: Capture ARP Packets**
1️⃣ Start a **Wireshark capture**.  
2️⃣ In **Command Prompt (`cmd`)**, type:
   ```cmd
   arp -a
   ```
   This will display your **ARP cache** (MAC addresses of devices in your network).  
3️⃣ In Wireshark, filter for:
   ```
   arp
   ```
4️⃣ Look for ARP **Request** and **Reply** packets.  
   - **Who has 192.168.1.1? Tell 192.168.1.100** → ARP Request  
   - **192.168.1.1 is at AA:BB:CC:DD:EE:FF** → ARP Reply  

🔹 **This shows how devices communicate to find each other’s MAC addresses!**

---

## **🔹 Common Attacks Detectable with Wireshark**
Using Wireshark, we can detect common cybersecurity threats:

### **1️⃣ ARP Spoofing (Man-in-the-Middle Attack)**
- An attacker **poisons the ARP cache** to intercept network traffic.  
- You can detect it by filtering for **`arp`** and checking for duplicate IP addresses.  

### **2️⃣ DNS Spoofing (Fake Websites)**
- An attacker **redirects you to a fake website** by manipulating DNS responses.  
- You can detect it by filtering for **`dns`** and checking if a suspicious IP is assigned to a domain.

### **3️⃣ Unauthorized Network Scanning (Nmap, Malicious Reconnaissance)**
- Attackers use scanning tools like **Nmap** to find open ports on a system.  
- You can detect it by filtering for **`tcp.flags.syn == 1 and tcp.flags.ack == 0`**, which shows SYN packets (used in scanning).

---

## **🔹 Homework Assignment**
1️⃣ Capture network traffic on your system for **5 minutes**.  
2️⃣ Filter for **HTTP, HTTPS, and ARP** packets and take screenshots.  
3️⃣ Find **your public IP address** in Wireshark by filtering:  
   ```
   ip.src == your_public_ip
   ```
   Replace `your_public_ip` with your actual IP (find it at **[https://www.whatismyip.com](https://www.whatismyip.com)**).  
4️⃣ Research **DNS Spoofing** and how attackers manipulate DNS responses.

---