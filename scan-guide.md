1. Get Your Local IP Address

   Using ifconfig or ip:

   On Linux:	

   ```bash
   ifconfig | grep inet
   # OR
   ip a | grep inet
   ```
   
2. Nmap Scan Guide

## Nmap Command Used
![Nmap Command](screenshots/nmap_scan_code.png)

## Results Summary
[View Nmap Scan Result](nmap_scan_result.txt)
- Most IPs were marked as "host down" or had all ports filtered.
- Three hosts were detected as up:
  - `192.168.152.1` – All 1000 ports filtered.
  - `192.168.152.254` – All 1000 ports filtered.
  - `192.168.152.128` – Port **8009/tcp (ajp13)** open.

## Observations
- Only one host with an open port (potential target for further security analysis).

🔓 Port 8009/tcp – AJP13 (Apache JServ Protocol)

🛡️ What is AJP13?
The Apache JServ Protocol (AJP) is a binary protocol used to communicate between a web server (e.g., Apache HTTPD) and an application server (e.g., Apache Tomcat).

It's often used behind the scenes to forward HTTP requests from a reverse proxy to Tomcat.

⚠️ Known Vulnerabilities of AJP13 (Port 8009)
1. Ghostcat Vulnerability (CVE-2020-1938)
Severity: High (CVSS: 9.8)

Description: A vulnerability in AJP allows attackers to read arbitrary files from the Tomcat server.

Exploitability: Very easy to exploit with a known IP and open port.

2. Unauthenticated Access
AJP has no built-in authentication. If the port is exposed to external or untrusted networks, anyone can send AJP requests to Tomcat.

3. Remote Code Execution (in misconfigured environments)
In some cases, when file uploads or serialized objects are poorly handled, AJP traffic can lead to RCE.
