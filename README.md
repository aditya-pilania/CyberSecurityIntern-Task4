# 🔐 Task 4 - Setup and Use a Firewall on Windows & Linux

## 🎯 Objective
- Configure and test basic **firewall rules** to **allow** or **block traffic**.
- Understand how **Windows Defender Firewall** and **UFW (Uncomplicated Firewall)** work on different operating systems.

---

## 🛠️ Tools Used

| OS            | Tool Used                                |
|---------------|-------------------------------------------|
| Windows 10/11 | Windows Defender Firewall with Advanced Security |
| Kali Linux    | UFW (Uncomplicated Firewall)              |

---

## 📘 Step-by-Step Firewall Setup

---

## 🪟 Part 1: Windows Defender Firewall (Outbound & Inbound Rules)

### ✅ Open Firewall Manager:
- Press `Win + R` → Type `wf.msc` → Hit Enter.

---

### 🔹 Block Outbound Traffic to Web (Ports 80 and 443)

1. Go to `Outbound Rules` → Right-click → **New Rule**
2. Select **Port**
3. Choose **TCP**, and enter specific ports: `80, 443`
4. Select **Block the connection**
5. Apply to all profiles: Domain, Private, Public
6. Name the rule: `Block_HTTP_HTTPS_Outbound`

### 🔹 Verify Rule Works
- Open browser → Try accessing any website → You should get **connection blocked**
- This proves **port 80 (HTTP)** and **443 (HTTPS)** are blocked.

---

### 🔹 List All Current Firewall Rules (PowerShell)
**I have attached a SS for the all current firewall rules**


## 🐧 Part 2: UFW on Kali Linux(Virtualbox)

## 🔧 Step-by-Step Configuration

### ✅ 1. Install UFW
UFW may not come pre-installed on Kali, so we install it using:
<pre>```bash
sudo apt update
sudo apt install ufw -y
(after the update of kali, and install of ufw, enable the ufw)

sudo ufw enable
(this will enable the Firewall Rules to the Kali Linux, You may restart the system to take effects)

sudo ufw allow 22
(this will allow SSH rule)

Will run some basic basic ports too like port 80 and 443

sudo ufw allow 80
sudo ufw allow 443
sudo ufw deny out 80
sudo ufw deny out 443

A screen shot has been attached in kali folder. You will see the rule applied for both ipv4 and ipv6.
</pre>
## ✅ Conclusion

### 🐧 On Kali Linux:
- Installed and enabled **UFW (Uncomplicated Firewall)**.
- Configured **allow rules** for essential services like SSH (22), HTTP (80), and HTTPS (443).
- Denied **outgoing web traffic** on ports 80 and 443 to simulate access restriction.
- Observed how firewall rules affect system connectivity and browsing behavior.

### 🪟 On Windows:
- Used **Windows Defender Firewall with Advanced Security**.
- Created **inbound and outbound rules** for specific ports.
- Successfully blocked **outgoing web traffic** (HTTP/HTTPS) and verified it through browser behavior.
- Used **PowerShell** and **GUI** to list, create, and manage rules effectively.

---

## 🧠 What I Learned

Through this task, I gained practical experience with firewalls on both **Linux** and **Windows** systems. I learned:

- The fundamental difference between **inbound** and **outbound** traffic.
- How to **allow and deny traffic** based on **ports**, **protocols**, and **direction**.
- That **UFW** is a simple yet powerful firewall tool in Linux for managing rules via the command line.
- How Windows offers a detailed GUI and PowerShell support to manage firewall rules with precision.
- How to test firewall effectiveness by checking **real network behavior** (e.g., blocking websites or services).
- Why firewalls are a critical component in **system hardening and cybersecurity**.

This hands-on experience deepened my understanding of network security and prepared me to configure firewall rules in real-world scenarios.
