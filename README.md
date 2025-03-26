# Wireshark Network Traffic Analysis

## Overview
This project explores how **network traffic works** by setting up an **FTP server with FileZilla** and analyzing it with **Wireshark**. The main goal is to see how **unencrypted FTP credentials** can be captured and why switching to a secure alternative like **SFTP or FTPS** is important.

## What You'll Need
To follow along, you'll need:
- **VirtualBox** (to run virtual machines)
- **Kali Linux** (to capture and analyze network traffic)
- **Windows 10** (to run the FileZilla FTP server)
- **Wireshark** (already installed in Kali)
- **FileZilla Server** (to handle file transfers)

## Steps to Set It Up
### 1. Run Kali Linux and Windows 10 in VirtualBox
- Install **VirtualBox** if you haven't already.
- Create **VMs for Kali and Windows 10** and complete their setup.
- In **VirtualBox Network Settings**, set both VMs to **"Bridged Adapter"** so they can communicate.

### 2. Install and Configure FileZilla Server
- On the **Windows 10 VM**, download and install **FileZilla Server**.
- Open FileZilla, create a **user account**, and set up a **shared folder**.

### 3. Capture FTP Traffic in Wireshark
- Open **Wireshark** in Kali and start capturing packets.
- Use the **ftp** command in Kali to connect to the **Windows 10 FTP server**.
- Enter the **username and password** you created.
- Watch how credentials appear **in plain text** in Wireshark.

### 4. Understanding the Security Risk
- Since **FTP does not encrypt data**, anyone with access to the network can **steal login credentials**.
- This is why **FTP (port 21) is insecure** and should be replaced with **FTPS (port 990) or SFTP (port 22)**.

### 5. Securing the Connection
- Go back to **FileZilla Server settings** and enable **"Explicit FTP over TLS" (FTPS)**.
- Restart the server and try logging in again.
- Check Wireshark—now the credentials should be **encrypted**.

## Key Takeaways
- **Regular FTP is not secure** because usernames and passwords are sent **as plain text**.
- **Wireshark can be used to capture network traffic** and expose security risks.
- **SFTP (SSH-based) and FTPS (TLS-based) encrypt your data**, making file transfers safer.

## Wrapping Up
Once you’ve completed the project:
- Stop packet capture in **Wireshark**.
- Close the **terminal and FileZilla Server**.
- Shut down **both Virtual Machines**.

## Why This Matters
This project is a **real-world example** of why encryption is necessary in **network security**. It’s useful for anyone learning about **cybersecurity, penetration testing, or IT administration**.

## License
This project is open-source and can be used for educational purposes.

---

