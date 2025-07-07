# TryHackMe: Network Fundamentals - Notes

This document summarizes my learning from the **Network Fundamentals** section on [TryHackMe](https://tryhackme.com/). This module introduces key networking concepts, devices, protocols, and topologies essential for understanding computer networks and their security.

---

## What is Networking?

- A network is simply a connection between devices.
- The **Internet** is a giant network made up of many smaller private and public networks.
- The Internet originated from ARPANET (late 1960s, US Department of Defense); the World Wide Web was invented by Tim Berners-Lee in 1989.

---

## Identifying Devices on a Network

- **IP Address (Internet Protocol)**:  
  - A unique identifier for a device on a network (IPv4 uses four octets; IPv6 offers larger address space).  
  - Public IP identifies devices on the Internet; private IP identifies devices within a local network.  
  - Assigned by ISPs or local network administrators.

- **MAC Address (Media Access Control)**:  
  - Unique hardware address assigned to a device’s network interface card (NIC).  
  - Can be spoofed in a process called MAC spoofing.

- **Ping**:  
  - Uses ICMP packets to test network connectivity and measure response time.

---

## Introduction to LAN Topologies

- **Star Topology**: Devices connect through a central switch or hub. Scalable but more expensive and requires maintenance.
- **Bus Topology**: All devices share a single backbone cable. Cost-effective but prone to bottlenecks and difficult troubleshooting.
- **Ring Topology**: Devices form a loop; data travels in one direction. Minimal cabling, easier fault detection, but a single failure can break the network.

---

## Networking Devices

- **Switch**: Connects multiple devices on a network, manages traffic efficiently by mapping devices to ports.
- **Router**: Connects different networks and routes data between them, enabling communication across networks.

---

## Subnetting

- Subnetting divides a network into smaller sub-networks for improved efficiency, security, and control.
- Uses a **subnet mask** to define network, host, and default gateway addresses.

---

## ARP (Address Resolution Protocol)

- Maps IP addresses to MAC addresses on a network.
- Works via ARP requests (broadcast to find MAC for an IP) and ARP replies (response with MAC).
- Stores mappings in an ARP cache for future use.

---

## DHCP (Dynamic Host Configuration Protocol)

- Automatically assigns IP addresses to devices.
- Four-step process:  
  1. **DHCP Discover**  
  2. **DHCP Offer**  
  3. **DHCP Request**  
  4. **DHCP Acknowledgment (ACK)**

---

## Disclaimer

All activities documented here are conducted in legal, controlled environments for educational purposes only.
