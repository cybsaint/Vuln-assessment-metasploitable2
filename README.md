# Metasploitable 2 Reconnaissance & Enumeration

A beginner-friendly cybersecurity project demonstrating how to perform **host discovery, port scanning, service enumeration, and SMB/FTP reconnaissance** against a Metasploitable 2 virtual machine using **Nmap** and the **Nmap Scripting Engine (NSE)**.

---

## Project Objectives

* Discover live hosts on the lab subnet
* Identify open TCP ports
* Detect running services and software versions
* Enumerate SMB shares and users
* Check for anonymous FTP access
* Perform banner grabbing for service identification

---

## 🖥️ Lab Environment

| Component      | Value              |
| -------------- | ------------------ |
| Target Machine | Metasploitable 2   |
| Target IP      | `192.168.213.130`  |
| Scanner        | Kali Linux         |
| Network        | `192.168.213.0/24` |
| Tool           | Nmap 7.95          |

---

## Reconnaissance Activities

| Activity          | Purpose                                 |
| ----------------- | --------------------------------------- |
| Host Discovery    | Identify live hosts on the subnet       |
| SYN Scan          | Discover open TCP ports                 |
| TCP Connect Scan  | Verify full TCP connectivity            |
| Version Detection | Identify services and software versions |
| SMB Enumeration   | Discover shared folders and users       |
| FTP Enumeration   | Check for anonymous FTP access          |
| Banner Grabbing   | Collect service banners                 |

---

## Key Nmap Commands

```bash
# Host Discovery
sudo nmap -sn 192.168.213.0/24

# SYN Scan
sudo nmap -sS 192.168.213.130

# TCP Connect Scan
nmap -sT 192.168.213.130

# Version Detection
sudo nmap -sV 192.168.213.130

# SMB Share Enumeration
sudo nmap -p 139,445 --script smb-enum-shares 192.168.213.130

# Anonymous FTP Enumeration
sudo nmap -p 21 --script ftp-anon 192.168.213.130

# Banner Grabbing
sudo nmap -sV --script banner 192.168.213.130
```

---

## Summary of Findings

* **1 live host** discovered on the lab subnet.
* **23 open TCP ports** identified.
* Anonymous FTP login was enabled.
* SMB shares were successfully enumerated.
* Multiple legacy services were exposed, including FTP, Telnet, HTTP, SMB, MySQL, and PostgreSQL.
* Service banners revealed software versions for further vulnerability assessment.

---

## Skills Demonstrated

* Network Reconnaissance
* TCP Port Scanning
* Service Enumeration
* SMB Enumeration
* FTP Enumeration
* Banner Grabbing
* Nmap Scripting Engine (NSE)
* Security Documentation

---

## Disclaimer

This project was conducted in an **isolated VMware laboratory** using the intentionally vulnerable **Metasploitable 2** virtual machine. It is intended **solely for educational purposes and authorized security testing**.
