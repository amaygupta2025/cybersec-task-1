# cybersec-task-1

# Task 1 – Network Port Scanning using Nmap

##  Tools Used
- Nmap
- Operating System: Windows
- Scan type: TCP SYN Scan (-sS)

## Nmap Command Used
nmap -sS -oN scan_results.txt 192.168.137.0/24

## Scan Summary

- **Network scanned:** 192.168.137.0/24
- **Host found:** 192.168.137.1
- **Open Ports Discovered:**
  - 135/tcp – MSRPC
  - 139/tcp – NetBIOS-SSN
  - 445/tcp – Microsoft-DS (SMB)
  - 2869/tcp – ICSLAP (Internet Connection Sharing)
  - 3306/tcp – MySQL

 ## Risk Analysis of Open Ports

| Port | Service      | Risk Description |
|------|--------------|------------------|
| 135  | MSRPC        | Used for Windows RPC, vulnerable to DCOM exploits |
| 139  | NetBIOS-SSN  | Legacy Windows sharing, can leak system info|
| 445  | Microsoft-DS | SMB, commonly targeted in ransomware attacks|
| 2869 | ICSLAP       | Often used by UPnP, risky if not needed |
| 3306 | MySQL        | Should not be exposed publicly without access control|


## Recommendations
- Block unused ports via firewall.
- Disable legacy services (NetBIOS, SMBv1).
- Ensure MySQL is bound only to localhost or firewalled.
- Regularly update your OS and services.

## Key Learnings
- Nmap helps identify potential exposures in a network.
- Even a single device can have multiple risky ports.
- Open ports should be managed and monitored continuously.


## Files Included
- scan_results.txt: Raw Nmap output
- README.md: This report

## Author
- Amay Gupta
- Cybersecurity Internship - Task 1
