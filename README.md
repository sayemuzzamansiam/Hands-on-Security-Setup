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
