# TryHackMe: Network Fundamentals - Notes

This document summarizes my learning from the **Network Fundamentals** module on [TryHackMe](https://tryhackme.com/). This room covers key networking principles including topologies, protocols, OSI layers, IP addressing, packet structure, and security technologies.

---

## 🌐 What is Networking?

- A **network** is simply a collection of connected devices.
- The **Internet** is a massive global network composed of smaller private/public networks.
- Origin: ARPANET (late 1960s, U.S. DoD); the modern Internet began with Tim Berners-Lee’s **World Wide Web** in 1989.

---

## 🔎 Identifying Devices on a Network

### IP Addresses (IPv4 & IPv6)
- Unique addresses for devices on a network.
- IPv4 uses 4 octets; IPv6 provides a much larger address space (2^128).
- **Public IP**: assigned by ISPs for Internet access.  
- **Private IP**: used within local networks.

### MAC Address
- Hardware address assigned to a device's NIC.
- 12-character hexadecimal ID.
- Can be spoofed via MAC spoofing.

### Ping
- Uses **ICMP packets** to test connectivity and measure response time between devices.

---

## 🏠 Local Area Network (LAN) Topologies

### Star Topology
- Devices connect to a central switch/hub.
- Expensive but scalable and reliable.

### Bus Topology
- All devices share a single backbone cable.
- Low cost, but prone to bottlenecks and failure.

### Ring Topology
- Devices form a loop (token-based).
- Simple cabling, easy fault detection, but one failure can bring down the network.

---

## 🔌 Networking Devices

### Switch
- Aggregates devices on a network using Ethernet.
- Tracks MAC addresses and directs traffic efficiently.

### Router
- Connects separate networks and routes data between them.
- Operates at OSI Layer 3.

---

## 📐 Subnetting

- Divides a network into smaller sub-networks (subnets).
- Uses **subnet masks** to define network, host, and gateway addresses.
- Benefits: improves efficiency, security, and control.

---

## 📡 ARP (Address Resolution Protocol)

- Maps **IP addresses to MAC addresses**.
- Sends ARP Requests to discover a device's MAC, which responds with an ARP Reply.
- Results are stored in the **ARP cache**.

---

## 🔄 DHCP (Dynamic Host Configuration Protocol)

- Automatically assigns IP addresses to devices.
- Four-step process:
  1. DHCP Discover  
  2. DHCP Offer  
  3. DHCP Request  
  4. DHCP Acknowledgment (ACK)

---

## 📶 OSI Model (7 Layers)

1. **Physical** – hardware, electrical signals, Ethernet cables.  
2. **Data Link** – MAC addressing, NICs.  
3. **Network** – routing, IP addresses (OSPF, RIP).  
4. **Transport** – protocols like TCP (reliable) and UDP (fast).  
5. **Session** – manages, maintains, and terminates sessions.  
6. **Presentation** – data translation, encryption.  
7. **Application** – user interface protocols (e.g., DNS, HTTPS).

---

## 📦 Packets & Frames

- **Packets** (Layer 3+) include IP-related headers.  
- **Frames** (Layer 2) deal with MAC addressing.
- Encapsulation wraps data with headers at each OSI layer.

### TCP/IP Packet Fields
- Time to Live (TTL), Checksum, Source/Destination IPs, Ports, Sequence/Ack numbers, Flags, and Data.

---

## 🤝 TCP/IP and UDP

### TCP (Transmission Control Protocol)
- Reliable, connection-based (3-way handshake).
- Used for file transfers, emails, browsing.

### UDP (User Datagram Protocol)
- Fast, connectionless, no guarantees.
- Ideal for streaming, voice chat, gaming.

---

## 🔢 Ports 101

- Range: 0–65535  
- Common ports:
  - **FTP** – 21  
  - **SSH** – 22  
  - **HTTP** – 80  
  - **HTTPS** – 443  
  - **SMB** – 445  
  - **RDP** – 3389

---

## 🔁 Extending Your Network

### Port Forwarding
- Makes services (e.g., web servers) accessible from outside the local network.
- Configured at the router.

### Firewalls
- Filter inbound/outbound traffic based on:
  - Source/Destination
  - Port
  - Protocol

#### Types:
- **Stateful** – Tracks full connections (uses more resources).  
- **Stateless** – Evaluates packets individually (faster, but less intelligent).

### VPNs (Virtual Private Networks)
- Secure tunnels between geographically distant networks.
- Provide **privacy, security, and anonymity**.

#### Protocols:
- **PPTP** (easy setup, weak encryption)  
- **IPsec** (stronger, complex)  
- **PPP** (used for authentication/encryption)

### VLANs (Virtual LANs)
- Logically separate devices on the same physical network.
- Enhances security and control.

---

## 📝 Final Thoughts

This module builds a critical foundation for understanding how devices communicate, how data moves through networks, and how security is layered in. These fundamentals are essential for both red and blue team roles in cybersecurity.

---

## Disclaimer

All activities documented here are conducted in legal, controlled environments for educational purposes only.
