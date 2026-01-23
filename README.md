# Securing a Network with PKI, Firewall & IDS

This is a complete hands-on project for securing a networked system using **Public Key Infrastructure (PKI)**, **Firewall**, **Intrusion Detection System (IDS)**, and **TLS/SSL encryption**.

---

## Project Overview

The goal of this project is to implement a secure networked environment with the following components:

-  **PKI Setup**: Root CA, Sub CA, and server certificate generation
-  **Web Server Configuration**: Apache2 with multiple websites and HTTPS enforcement
-  **DNS Server**: Forward and reverse resolution for domains and subdomains
-  **Firewall Configuration**: UFW with custom rules for allowed ports
-  **IDS Setup**: Snort for detecting and logging attacks (SYN flood)
-  **Attack Simulation & Mitigation**: Perform and block a SYN flood attack
-  **SSH Hardening**: Change default SSH port and secure access
-  **TLS Handshake Analysis**: Capture and analyze TCP/TLS handshake with Wireshark

---

## Technologies Used

- **Virtualization**: Oracle VM VirtualBox
- **OS**: Ubuntu (Server & Client VMs)
- **Web Server**: Apache2
- **PKI Tools**: OpenSSL
- **DNS**: BIND9
- **Firewall**: UFW (Uncomplicated Firewall)
- **IDS**: Snort
- **Network Analysis**: Wireshark, hping3
- **SSH**: OpenSSH

---

## System Architecture

* **Server Machine**

  * Root CA & Sub CA
  * Apache HTTPS Server (Port 443)
  * DNS Server
  * Firewall (UFW)
  * IDS (Snort)

* **Client Machine**

  * HTTPS Access
  * Attack Simulation
  * Certificate Verification

---

## Environment Setup

1. Install **Oracle VM VirtualBox**
2. Install **Ubuntu** on two virtual machines
3. Configure:

   * Adapter 1: **NAT Network**
   * Adapter 2: **NAT**
4. Assign static IPs for proper DNS and server communication

---

## Certificate Authority (PKI) Setup

* Created directory structure for:

  * `Root CA`
  * `Sub CA`
  * `Server`
* Generated private keys:

  * **4096-bit** for Root CA & Sub CA (high security)
  * **2048-bit** for Server (performance optimization)
* Root CA signs Sub CA
* Sub CA signs Server Certificate
* Certificate chain merged for HTTPS deployment

---

## HTTPS Configuration

* Enabled SSL on **port 443**
* Configured Apache2 to serve a secure website
* Installed Root CA certificate in both:

  * Server OS
  * Client browser
* Verified HTTPS connection with **padlock icon**

---

## DNS Configuration

* Installed and configured **BIND9**
* Created:

  * Forward zone (`db.mywebsite.com`)
  * Reverse zone (`db.0.168.192`)
* Configured client DNS resolution
* Verified using `nslookup`

---

## Firewall Configuration (UFW)

* Default rules:

  * Allow outgoing
  * Deny incoming
* Allowed services:

  * SSH (22)
  * DNS (53)
  * HTTP (80)
  * HTTPS (443)
* Dynamically blocked attacker IPs after detection

---

## Intrusion Detection System (Snort)

* Installed **Snort** on Server
* Configured custom rules for **SYN Flood Attack**
* Detected attacks initiated from Client
* Analyzed logs using **Wireshark**
* Blocked attacker IP using UFW

---

## Network Traffic Analysis

* Captured:

  * TCP Handshake
  * TLS Handshake
* Used **Wireshark** to inspect encrypted traffic
* Verified secure key exchange and session establishment

---

## OpenSSH Access

* Installed OpenSSH server on both machines
* Enabled secure remote login from Client to Server
* Verified firewall rules for SSH access

---

## Attack Simulation

* Used **hping3** from Client
* Generated SYN Flood traffic
* Detected attack using Snort
* Mitigated attack via firewall rule insertion

---

## Final Outcome

* Successfully implemented a **secure HTTPS-enabled network**
* Demonstrated **PKI hierarchy**
* Enforced **network security policies**
* Detected and mitigated network attacks
* Verified encrypted communication end-to-end

---

## Learning Outcomes

* Practical understanding of **PKI & TLS**
* Hands-on experience with **network security tools**
* Real-world exposure to **attack detection & prevention**
* Secure server and client communication design
