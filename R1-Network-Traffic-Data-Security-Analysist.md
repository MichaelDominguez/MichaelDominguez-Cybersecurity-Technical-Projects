# Cybersecurity Practical Lab Report #1
## Network Traffic Analysis and Data Handling Security  

**Author:** Michael D.  
**Lab Context:** Cisco Networking Academy – Cybersecurity & Network Analysis  

---

## Overview

This lab presents a comprehensive analysis of how data is transmitted across a network and how it is subsequently handled, stored, and managed by modern service platforms.

The objective of this exercise is to develop a practical understanding of the full data lifecycle, beginning with packet-level transmission and extending to data ownership, privacy, and security implications in real-world environments.

By integrating network traffic analysis with data handling evaluation, this lab reflects how cybersecurity professionals must assess both technical communication processes and post-transmission data risks.

---

## Objective

- Analyze network traffic using packet capture tools  
- Examine the behavior of core TCP/IP protocols  
- Evaluate how transmitted data is processed by service providers  
- Identify security risks across both transmission and storage layers  

---

## Methodology

The lab was conducted as a continuous workflow integrating technical analysis and data evaluation:

### Network Analysis
- Utilized Wireshark to capture live packet data  
- Generated traffic using:
  - ICMP (ping)
  - DNS queries
  - Telnet connection attempts  
- Used command-line tools (arp, cmd) to inspect network behavior  

### Data Handling Evaluation
- Reviewed service-level data policies and Terms of Service  
- Assessed how transmitted data is collected, stored, processed, and retained  

---

## Network Traffic Analysis

### ARP (Address Resolution Protocol)
- Observed IP-to-MAC resolution via broadcast communication  
- Identified lack of authentication → vulnerable to spoofing  

### ICMP (Internet Control Message Protocol)
- Used for connectivity testing  
- Demonstrated predictable request-response patterns  

### DNS (Domain Name System)
- Domain resolution over UDP (port 53)  
- Lack of encryption exposes query data  

### TCP vs UDP

| Feature | TCP | UDP |
|--------|-----|-----|
| Type | Connection-oriented | Connectionless |
| Reliability | High | Low |
| Speed | Slower | Faster |
| Use Case | Web, Email | DNS, Streaming |

---

## Data Handling and Security Analysis

### Data Collection
- Personal data  
- Uploaded content  
- Behavioral data  

### Data Usage
- Analytics  
- Service optimization  
- Targeted advertising  

### Risks
- Loss of user control  
- Data persistence after deletion  
- Third-party sharing  

---

## Integrated Security Assessment

- Exposure during transmission (interception risks)  
- Exposure after storage (data misuse risks)  

**Key Insight:**  
Effective cybersecurity requires understanding both data transmission and data ownership.

---

## Conclusion

This lab demonstrates a unified view of cybersecurity, connecting network-level analysis with data privacy risks to reflect real-world security challenges.

---

## References

- Cisco Networking Academy  
