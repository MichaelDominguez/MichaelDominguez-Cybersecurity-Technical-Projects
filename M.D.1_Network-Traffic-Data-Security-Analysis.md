# M.D.1 — Network Traffic & Data Security Analysis
## Windows Network Diagnostics, Wireshark Packet Capture, and Protocol Security Review

**Technical Context:** Windows Network Diagnostics, Wireshark Packet Capture, and Protocol Security Review

---

## Overview

This project focused on analyzing live network communication behavior using Windows command-line networking tools and Wireshark packet inspection. The goal was to understand how common protocols appear during real network activity and how packet-level visibility can reveal security-relevant details about local communication, name resolution, and TCP-based connections.

The work followed a practical workflow: generate network traffic using command-line utilities, capture the traffic in Wireshark, inspect packet headers and protocol fields, and interpret the security implications of what was observed.

---

## Evidence Screenshots

### Command Prompt Preparation

![Command Prompt launched for network testing](images/M.D.1%20Network%20Analysis%20Part%201.png)

The Windows Command Prompt was launched with administrative access to run networking commands used throughout the project. This environment supported direct interaction with ARP cache inspection, ICMP connectivity testing, DNS lookup activity, and TCP connection attempts.

### ICMP Connectivity Verification

![ICMP ping test to local gateway](images/M.D.1%20Network%20Analysis%20Part%202.png)

The `ping` command was used to test connectivity to the local gateway. The output shows successful replies with 0% packet loss, confirming that the system could communicate with the gateway before deeper packet inspection was performed in Wireshark.

### Wireshark Packet Capture Review

![Wireshark packet capture showing TCP, DNS, SSDP, and TLS traffic](images/M.D.1%20Network%20Analysis%20Part%203.png)

Wireshark captured live traffic from the active network interface. The packet list showed multiple protocols, including TCP acknowledgments, DNS traffic, SSDP traffic, and TLS application data. The packet-detail pane exposed protocol layering such as Frame, Ethernet II, IPv4, and TCP header information, demonstrating packet analysis beyond basic command output.

---

## Objective

The objective was to develop practical visibility into how data moves across a network and how different protocols support common communication tasks. The project also considered how transmitted data can create security risks during and after network communication.

Key goals included:

- Inspecting local network behavior using command-line tools
- Capturing live traffic with Wireshark
- Identifying ARP, ICMP, DNS, and TCP activity
- Comparing connection-oriented and connectionless communication behavior
- Recognizing security risks associated with plaintext protocols and observable metadata

---

## Methodology

Traffic was generated from a controlled local Windows environment using standard command-line utilities. Wireshark was used to capture and inspect the resulting packets.

Commands and actions used during testing included:

```text
arp -a
arp -d
ping [local gateway]
nslookup kean.edu
telnet eve.kean.edu
```

Sensitive system and network identifiers were generalized where appropriate for privacy.

---

## ARP Cache Review and Local Address Resolution

The ARP table was inspected using `arp -a` to review local IP-to-MAC address mappings. Dynamic ARP entries confirmed that the workstation was actively communicating with devices on the local network.

After clearing ARP entries with `arp -d`, new ARP broadcast packets were observed during renewed communication attempts. This demonstrated how hosts re-initiate address resolution when they need to map an IP address to a physical MAC address.

From a security perspective, ARP is important because it relies on local broadcast behavior and does not provide strong authentication. This makes ARP traffic relevant when studying spoofing, man-in-the-middle positioning, and local-network trust assumptions.

---

## ICMP Connectivity Testing

ICMP traffic was generated using `ping` against the local gateway. Successful echo replies confirmed that the host had working Layer 3 connectivity to the local network gateway.

The Wireshark capture allowed the connectivity test to be analyzed from a packet perspective rather than only relying on command-line output. This helped connect the visible terminal result with the underlying ICMP request/reply exchange.

This portion demonstrated how basic troubleshooting output can be validated through packet inspection.

---

## DNS Query Observation

DNS traffic was generated using `nslookup kean.edu`. The lookup produced name-resolution traffic that could be inspected in Wireshark.

The capture demonstrated how DNS requests are sent to resolve a human-readable domain name into network-address information. Standard DNS lookups commonly use UDP port 53, and the query/response structure can reveal which domains are being requested.

Security relevance: standard DNS queries can expose browsing or lookup behavior to network observers unless encrypted DNS protections are used. This makes DNS monitoring important for both defensive visibility and privacy awareness.

---

## TCP Communication and Telnet Review

A Telnet connection attempt was generated using `telnet eve.kean.edu`. Telnet is valuable for demonstration purposes because it uses TCP and historically operates over port 23, but it is considered insecure for modern production use because it transmits data without encryption.

Wireshark provided visibility into TCP connection behavior during the attempt. This included SYN-based connection initiation and packet-level communication details associated with TCP session establishment.

Security relevance: Telnet demonstrates why plaintext administrative protocols are risky. Modern environments typically replace Telnet with encrypted alternatives such as SSH.

---

## TCP vs UDP Behavior

This project also reinforced the difference between TCP and UDP behavior. TCP provides connection-oriented communication with reliability mechanisms such as acknowledgments and sequencing. UDP provides lower-overhead communication without the same session-establishment behavior.

This distinction was useful when comparing DNS traffic against TCP-based communication observed during the packet capture.

---

## Data Handling and Security Considerations

The project also connected network transmission to broader data-handling concerns. Once data reaches external systems, the risk model expands beyond transmission security into storage, processing, retention, and third-party access.

Security considerations included:

- Metadata exposure through observable protocols
- Plaintext protocol risks
- Loss of direct control after data is uploaded to external services
- Retention and processing risks after transmission
- Centralized storage increasing breach impact

Key insight: effective cybersecurity requires understanding both packet-level communication and the broader lifecycle of data after transmission.

---

## Technical Skills Demonstrated

- Windows command-line networking
- ARP cache inspection and reset behavior
- ICMP connectivity testing
- DNS query generation and review
- TCP connection analysis
- Wireshark packet capture and inspection
- Protocol hierarchy review
- Security interpretation of observable network traffic

---

## Conclusion

This project demonstrated how common network operations can be captured, inspected, and interpreted using Wireshark and Windows networking utilities. The work connected command-line results with packet-level evidence and highlighted how protocols such as ARP, ICMP, DNS, and TCP support everyday communication while also introducing security considerations.

---

## References

- Wireshark Foundation. *Wireshark User Guide*. https://www.wireshark.org/docs/
- Cisco Networking Academy. *Cybersecurity Operations Fundamentals*.
- Gregg, M., & Santos, O. (2022). *CEH Certified Ethical Hacker Cert Guide*. Pearson Education.

**M. Dominguez**
