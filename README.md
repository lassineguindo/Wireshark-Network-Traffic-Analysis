# Wireshark-Network-Traffic-Analysis
# Wireshark Network Traffic Analysis

## Overview
This project demonstrates how to analyze network traffic using **Wireshark** while setting up an **FTP server with FileZilla**. The goal is to observe how unencrypted FTP credentials can be captured and understand why secure alternatives like **SFTP/FTPS** should be used.

## Setup
To replicate this analysis, you'll need:
- **VirtualBox** (to run virtual machines)
- **Kali Linux** (for network analysis with Wireshark)
- **Windows 10** (running FileZilla Server)
- **Wireshark** (pre-installed in Kali)
- **FileZilla Server** (to host FTP connections)

## Steps
### 1. Set Up Virtual Machines
- Run **Kali Linux** and **Windows 10** simultaneously in **VirtualBox**.
- Set **both VMs to "Bridged Adapter"** in **VirtualBox Network Settings** to allow them to communicate.

### 2. Install and Configure FileZilla Server
- On **Windows 10**, download and install **FileZilla Server**.
- Open FileZilla, create a **user** with a **password**, and assign a **shared folder**.

### 3. Capture Network Traffic with Wireshark
- Open **Wireshark** in Kali and start capturing packets.
- Use **FTP** to connect from Kali to **Windows 10 FileZilla Server**.
- Observe how **username and password** are **sent in plain text**.

### 4. Analyze FTP Security Risks
- Wireshark will reveal that **FTP credentials are exposed**.
- This highlights why **FTP (port 21) is insecure** and why you should use **SFTP (port 22) or FTPS** instead.

### 5. Secure the Connection
- Configure **FileZilla Server** to use **Explicit FTP over TLS (FTPS)**.
- Retest with Wireshark to confirm that **credentials are now encrypted**.

## Key Takeaways
- **Plain FTP is insecure** because credentials are transmitted in **clear text**.
- **Wireshark can capture FTP packets**, showing why encryption is necessary.
- **SFTP (SSH-based) and FTPS (TLS-based) are secure alternatives** to FTP.

## Closing the Project
Once you've completed the analysis:
- Stop packet capture in **Wireshark**.
- Close **all terminals and FileZilla Server**.
- Shut down **your Virtual Machines**.

## Why This Matters
Understanding **network traffic analysis** is essential for **cybersecurity, penetration testing, and network administration**. This project provides hands-on experience with real-world security risks and how to mitigate them.

## License
This project is open-source and available for educational purposes.

---

This README is ready to be uploaded to GitHub. Let me know if you need any changes.

