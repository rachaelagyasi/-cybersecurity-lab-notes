Nmap Network Discovery and Port Scanning

1. Project Overview

This project documents a practical network scanning exercise using Nmap in a Kali Linux virtual machine running in Oracle VirtualBox.

The purpose was to identify active hosts, scan network ports, detect services and versions, and save scan results for security analysis.

2. Lab Environment

* Operating System: Kali Linux
* Virtualization: Oracle VirtualBox
* Network scanning tool: Nmap 7.99
* Target: Local virtual lab network
* Target IP: 10.0.2.2

3. Objectives

* Perform network host discovery.
* Identify open TCP and UDP ports.
* Detect running services and software versions.
* Practice operating system detection.
* Save scan results in a text report.
* Interpret findings and identify areas requiring further investigation.

4. Commands Practiced

Command	Purpose
nmap --version	Check Nmap version
ip addr	View network interface information
nmap -sn 10.0.2.0/24	Discover active hosts
nmap 10.0.2.2	Scan default TCP ports
nmap -sV 10.0.2.2	Detect services and versions
nmap -p 53,135,445 10.0.2.2	Scan selected ports
sudo nmap -O 10.0.2.2	Attempt operating system detection
sudo nmap -sS 10.0.2.2	Perform TCP SYN scan
nmap -sT 10.0.2.2	Perform TCP Connect scan
sudo nmap -sU --top-ports 20 10.0.2.2	Scan selected UDP ports
nmap -T4 -p 53,135,445 10.0.2.2	Use aggressive timing
nmap -sV -p 53,135,445 -oN final_report.txt 10.0.2.2	Scan selected ports and save results

5. Final Scan Results

The final scan identified the following open TCP ports:

Port	State	Service	Detection
53/tcp	Open	DNS	dnsmasq 2.90
135/tcp	Open	MSRPC	Microsoft Windows RPC
445/tcp	Open	Microsoft-DS	SMB-associated service

The target host responded successfully.

Nmap reported Windows-related service information. This should not be treated as definitive operating system confirmation.

6. Security Observations

* Port 53 is associated with DNS services.
* Port 135 is associated with Microsoft RPC.
* Port 445 is associated with SMB file sharing.
* Open ports should be investigated to determine whether services are necessary and securely configured.
* An open port does not automatically indicate a vulnerability.

7. Skills Demonstrated

* Kali Linux command-line operations
* Network discovery
* TCP and UDP scanning
* Port identification
* Service and version detection
* Basic OS fingerprinting
* Nmap scan reporting
* Technical documentation
* Basic security analysis

8. Conclusion

This practical exercise provided experience using Nmap to discover network hosts, identify open ports, examine running services, and document scan findings.

The exercise provides a foundation for further vulnerability assessment using tools such as Nessus.

9. Scope and Authorization

All scanning was performed within an authorized personal virtual lab environment for educational purposes.