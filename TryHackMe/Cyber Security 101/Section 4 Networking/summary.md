# 🌐 TryHackMe — Section 4: Networking
Authored by Rafael Mejia Galvan

## 🔎 Overview
This section explores how data moves across networks — from physical media and MAC addressing up through IP routing, transport protocols (UDP/TCP), application protocols (HTTP, DNS, email), and their secure counterparts (TLS/SSH/VPN). It also covers analyst tooling: **Wireshark**, **tcpdump**, and **Nmap**.

---

## 🧩 Networking Models

### 📚 OSI Model (7 layers)
1. ⚡ **Physical (L1):** Signals & media (electrical/optical/wireless).  
2. 🔗 **Data Link (L2):** Same-segment delivery; uses **MAC** addresses (6 bytes, hex).  
3. 🌍 **Network (L3):** Inter-network delivery/routing (IP, ICMP, VPNs).  
4. 🚚 **Transport (L4):** End-to-end comms (TCP/UDP).  
5. 🗣️ **Session (L5):** Establish/maintain/sync conversations.  
6. 🔑 **Presentation (L6):** Format/encode/compress/encrypt (ASCII, Unicode).  
7. 💻 **Application (L7):** End-user protocols (HTTP, FTP, DNS, SMTP/POP3/IMAP).  

### 🌐 TCP/IP Model (4 layers)
- Link (≈L2) → Internet (≈L3) → Transport (L4) → Application (L5–7).  
- Built for resilience (keeps working even if parts fail).

---

## 📡 IP Addresses & Subnetting
- IPv4 = 32 bits (4 octets, 0–255).  
- **Private ranges (RFC1918):**  
  `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`.  
- Routers (L3) forward packets between networks.  
- **NAT** = many private devices sharing one public IP.

---

## 🔀 UDP vs TCP
- 📦 **UDP:** Connectionless, fast, no delivery guarantee.  
- 📦 **TCP:** Connection-oriented, reliable (seq/ack, retransmit).  
  - Uses the **3-way handshake:** `SYN → SYN/ACK → ACK`.

---

## 📦 Encapsulation
Every layer wraps data:  
App Data → L4 Segment → L3 Packet → L2 Frame.  
Receiver reverses this (decapsulation).

---

## 🖥️ Legacy Protocol
- **Telnet (TCP/23):** Remote terminal, plaintext (not secure).

---

## 🛠️ Networking Essentials

- **DHCP (UDP/67–68):** Auto assigns IP, gateway, DNS. Process = `Discover → Offer → Request → Ack`.  
- **ARP:** Resolves IP ↔ MAC. Broadcast uses `ff:ff:ff:ff:ff:ff`.  
- **ICMP:** Used in `ping` (Echo Request/Reply) & `traceroute` (TTL + Time Exceeded).  
- **Routing Protocols:**  
  - 🛰️ OSPF = shortest path.  
  - 🚦 RIP = hop count.  
  - 📡 BGP = Internet’s backbone.  
  - ⚙️ EIGRP = Cisco hybrid.

---

## 🌍 Core Protocols

- **DNS (UDP/53):** Name ↔ IP. Records: A, AAAA, CNAME, MX.  
- **HTTP (TCP/80) / HTTPS (TCP/443):** Web traffic; HTTPS = HTTP + TLS.  
- **FTP (TCP/21):** File transfers (`USER`, `PASS`, `RETR`, `STOR`).  
- **SMTP (TCP/25):** Sending email.  
- **POP3 (TCP/110):** Download & delete model.  
- **IMAP (TCP/143):** Sync mailbox across devices.

---

## 🔐 Secure Protocols

- **TLS:** Provides encryption, integrity, authenticity.  
- **HTTPS/SMTPS/POP3S/IMAPS:** Secure versions of core mail/web.  
- **SSH (TCP/22):** Secure shell + tunneling + SFTP.  
- **VPN:** Encrypted tunnel for all traffic.

---

## 🔍 Wireshark
- GUI analyzer for troubleshooting & security analysis.  
- Features: filters, mark/comment, export packets/objects.  
- Can **Follow Streams** to reconstruct app-level data.  
- Expert Info highlights warnings, errors, anomalies.

---

## 🖥️ tcpdump
- CLI packet sniffer.  
- Commands:  
  - `-i <iface>` (interface), `-w file.pcap` (save), `-r file` (read).  
  - Filters by `host`, `port`, `protocol` (`tcp`, `udp`, `icmp`).  
  - Use `and/or/not` for logic.  
- Display: `-n` (no DNS), `-nn` (no DNS + no service), `-v` (verbose).  

---

## 🔎 Nmap
- Host discovery (`-sn`, `-sL`).  
- Port scans: `-sT` (connect), `-sS` (SYN), `-sU` (UDP).  
- Service/version detection: `-sV`. OS detection: `-O`.  
- Timing templates `-T0` → `-T4`.  
- Output: `-oN`, `-oX`, `-oG`, `-oA`.

---

## 🧾 Common Ports
- TELNET: 23  
- DNS: 53  
- HTTP: 80 / HTTPS: 443  
- FTP: 21  
- SMTP: 25  
- POP3: 110 / POP3S: 995  
- IMAP: 143 / IMAPS: 993  
- SSH/SFTP: 22  

---

## 🧠 What I Learned
- Understood the **OSI & TCP/IP models** and how encapsulation works.  
- Differentiated **IPv4 addressing, subnets, NAT**, and routing.  
- Compared **UDP vs TCP** and mastered the **3-way handshake**.  
- Practiced analyzing **DNS, HTTP(S), FTP, SMTP, POP3, IMAP** protocols and their **secure versions**.  
- Learned how **TLS, SSH, VPNs** secure communication.  
- Used **Wireshark** (filters, follow streams, expert info) for packet analysis.  
- Applied **tcpdump** for CLI packet captures with filters.  
- Gained skills in **Nmap scanning** for hosts, ports, services, and OS detection.

---
