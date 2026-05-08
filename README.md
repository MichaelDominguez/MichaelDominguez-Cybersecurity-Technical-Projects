# Michael Dominguez — Cybersecurity Technical Projects

This repository contains a hands-on cybersecurity project portfolio built from lab work, command output, packet captures, cloud-console configuration, and Linux terminal practice. The reports are written to show what was actually done in each environment instead of only listing security terms. Each project includes a markdown write-up and watermarked screenshots in the `images/` folder so a reviewer can connect the written explanation to visible tool output.

The projects move through a realistic progression. M.D.1 starts with network communication fundamentals in Windows and Wireshark. M.D.2 expands that work into host discovery, TCP port scanning, and vulnerability research. M.D.3 shifts into AWS identity and monitoring operations. M.D.4 covers credential-security testing with John the Ripper and connects the results to password storage and authentication controls. M.D.5 finishes with Kali Linux administration tasks that support security auditing and troubleshooting.

---

## Project Index

| Project | Focus | Main Tools | Report |
|---|---|---|---|
| M.D.1 | Network traffic inspection and protocol behavior | Wireshark, Windows Command Prompt, ARP, ICMP, DNS | [Network Traffic & Data Security Analysis](M.D.1_Network-Traffic-Data-Security-Analysis.md) |
| M.D.2 | Port scanning, host discovery, and vulnerability research | Nmap, Zenmap, Wireshark, CVE, NVD, Rapid7 | [Port Scanning & System Vulnerability Research](M.D.2_Port-Scanning-and-System-Vulnerabilities-Assessment.md) |
| M.D.3 | Cloud identity, monitoring, and account-security operations | AWS IAM, EC2, CloudWatch, AWS CLI | [Cloud Security Operations Review](M.D.3_Cloud-Security-Operations-Review.md) |
| M.D.4 | Password hash auditing and credential-security review | John the Ripper, Windows CMD, hash files, wordlist rules | [Password Hashing & Credential Security Testing](M.D.4_Password-Hashing-and-Credential-Security-Testing.md) |
| M.D.5 | Kali Linux networking, privilege controls, and system administration | Kali Linux, VMware, ifconfig, ip addr, dpkg, sudo | [Kali Linux Security Auditing Operations](M.D.5_Kali_Linux-Security-Auditing-Operations.md) |

---

## What the Work Shows

### M.D.1 — Network Traffic & Data Security Analysis

This project documents a Windows-based network traffic workflow where command-line tools were used to generate observable traffic and Wireshark was used to inspect the results. The work includes ARP cache review, ICMP connectivity testing to a local gateway, DNS lookup activity, and packet-level review of TCP/TLS traffic. The screenshots support the progression from running commands in an elevated prompt to viewing captured frames in Wireshark, including protocol layers such as Ethernet II, IPv4, and TCP.

The value of this project is that it shows practical packet interpretation. Instead of simply saying “Wireshark was used,” the report explains what was visible in the packet list and packet detail panes, why ARP/ICMP/DNS traffic matters, and how packet capture can support troubleshooting and security investigation.

### M.D.2 — Port Scanning & System Vulnerability Research

This project uses Nmap and Zenmap to perform host discovery and TCP port scanning while Wireshark captures the scan behavior. The report documents subnet enumeration, ARP broadcast activity caused by scanning, TCP Connect scan behavior, SYN scan behavior, and filtering traffic with `tcp.port == 80` to inspect handshake patterns around an exposed HTTP service.

The project also connects scan results to vulnerability research. Public vulnerability sources such as CVE, NVD, Rapid7, CVEDetails, Exploit-DB, and Microsoft security references were reviewed to understand how exposed services and known vulnerabilities are investigated after enumeration. The report fixes earlier spelling issues around “Vulnerabilities” and gives enough detail for a reviewer to understand the workflow: discover systems, identify services, inspect packet signatures, then research known weaknesses.

### M.D.3 — Cloud Security Operations Review

This project focuses on AWS security administration instead of local network scanning. The report documents IAM user and group configuration, managed policy review, account alias usage, and CloudWatch alarm setup. It also covers operational monitoring concepts such as EC2 utilization alarms, recovery or reboot actions, and billing alert awareness.

The included screenshots are important because cloud-security work can otherwise sound abstract. They show visible AWS console activity and configuration review, supporting that the work involved hands-on navigation of IAM and CloudWatch rather than only summarizing cloud security theory.

### M.D.4 — Password Hashing & Credential Security Testing

This project documents credential-security testing with John the Ripper in a controlled lab environment. Provided password hash files were tested using John commands such as `john passwd.des`, `john passwd.md5`, and `john --wordlist=password.lst --rules passwd.md5`. The report explains the difference between slower hash auditing attempts and faster dictionary/rule-based recovery, then connects those results to defensive controls such as stronger password policy, multifactor authentication, and careful handling of generated artifacts like `john.log`, `john.pot`, and `john.rec`.

The supporting encryption and authentication material was folded into the report so the project does not stop at “password cracking.” It explains why MD5 and SHA-1 are not appropriate for modern security-sensitive use, why SHA-256 and SHA-512 are stronger general-purpose hash families, and how authentication differs from authorization. It also mentions modern identity concepts such as OpenID Connect, OAuth 2.0, centralized identity providers, and multifactor authentication.

### M.D.5 — Kali Linux Security Auditing Operations

This project shows Linux command-line work inside a Kali Linux virtualized environment. The report documents interface enumeration with `ifconfig`, IP address review and manual interface configuration with `ip addr`, and privilege enforcement during package-management testing with `dpkg` and `sudo`. It also connects basic filesystem, permission, and process-management commands to practical security work.

This matters for cybersecurity roles because many security tools and investigation workflows depend on Linux terminal fluency. The report explains the meaning of interface flags, IP addressing, RX/TX counters, privilege-required actions, and why package installation should be restricted to authorized users.

---

## Evidence and Screenshots

The screenshots are intentionally preserved in the repository as watermarked evidence of hands-on practice. They are not decorative images; they support the written reports by showing command windows, tool output, packet captures, cloud-console configuration, and Kali Linux terminal behavior.

The `images/` folder is organized by project number. For example, the M.D.2 screenshots show the port-scanning workflow, while the M.D.4 screenshots support the John the Ripper credential-security testing workflow. The screenshots were left unredacted because they were already prepared as watermarked project evidence.

---

## Responsible Use

These projects are for authorized learning, defensive security practice, and professional portfolio review. Network scanning, credential testing, vulnerability research, and cloud administration should only be performed in environments where permission has been granted. The reports intentionally frame offensive-style tools from a defensive and educational perspective: understanding how activity appears, what risks it creates, and what controls reduce exposure.

**M. Dominguez**
