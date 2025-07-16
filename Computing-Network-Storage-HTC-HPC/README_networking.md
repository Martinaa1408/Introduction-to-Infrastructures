# README: Networking and Connectivity in Distributed Systems

## Overview

This module provides a comprehensive overview of computer networking, essential for understanding how systems communicate in local and distributed environments. It covers fundamental concepts such as addressing, protocols, data flow, infrastructure components (e.g., switches, routers), and their relationship with cloud computing, batch systems, and containerized environments. Networking is the backbone that enables **IoT**, **HTC/HPC**, **Grid computing**, and **Cloud services**.

---

## 1. Network Architecture and Topology

### 1.1 Network Nodes

* A **node** is any physical or virtual device connected to a network (e.g., PC, server, switch).
* Nodes can act as **clients**, **servers**, or **peers**.

### 1.2 Network Topologies

| Topology | Description                              | Usage Example            |
| -------- | ---------------------------------------- | ------------------------ |
| Bus      | All devices share one communication line | Legacy LANs              |
| Star     | All nodes connected to a central switch  | Modern Ethernet LANs     |
| Ring     | Nodes connected in a circular fashion    | Token Ring networks      |
| Mesh     | Devices interconnected for redundancy    | High-availability setups |

### 1.3 Connection Types

| Type | Scope              | Typical Use                  |
| ---- | ------------------ | ---------------------------- |
| LAN  | Local (office/lab) | Fast internal communication  |
| WAN  | Global             | Internet access              |
| MAN  | Metropolitan       | Campus or city-scale network |

---

## 2. OSI and TCP/IP Models

### 2.1 OSI Model (7 Layers)

| Layer           | Function                 | Protocols/Examples   |
| --------------- | ------------------------ | -------------------- |
| 7. Application  | User interface, APIs     | HTTP, FTP, SSH       |
| 6. Presentation | Encoding, encryption     | SSL/TLS, ASCII       |
| 5. Session      | Start, maintain sessions | NetBIOS, RPC         |
| 4. Transport    | Reliable delivery        | TCP, UDP             |
| 3. Network      | Routing, IP addressing   | IP, ICMP             |
| 2. Data Link    | MAC addressing           | Ethernet, ARP        |
| 1. Physical     | Hardware transmission    | Cables, Wi-Fi, Fiber |

### 2.2 TCP/IP Stack

* Simplified and more commonly used in practice.
* Fewer layers, more focused on real-world protocols.

| Layer          | Function                    | Protocols       |
| -------------- | --------------------------- | --------------- |
| Application    | End-user interactions       | HTTP, FTP, SSH  |
| Transport      | End-to-end connections      | TCP, UDP        |
| Internet       | Logical addressing/routing  | IP, ICMP        |
| Network Access | Physical addressing & media | Ethernet, Wi-Fi |

---

## 3. Addressing and Configuration

### 3.1 MAC vs IP Address

| Feature | MAC Address                          | IP Address      |
| ------- | ------------------------------------ | --------------- |
| Type    | Hardware address                     | Logical address |
| Format  | 48-bit hex (e.g., 00:1A:2B:3C:4D:5E) | IPv4/IPv6       |
| Scope   | Local network only                   | Global routing  |

### 3.2 Subnetting and MTU

* **Subnet mask** (e.g., 255.255.255.0) defines address boundaries.
* **MTU (Maximum Transmission Unit)** controls packet size.

### 3.3 IP Classes and Special Addresses

| Address         | Meaning                |
| --------------- | ---------------------- |
| 0.0.0.0         | Unspecified / bind-all |
| 127.0.0.1       | Loopback (localhost)   |
| 192.168.x.x     | Private LAN            |
| 255.255.255.255 | Broadcast address      |

---

## 4. Networking Commands

```bash
ifconfig      # View and configure interfaces
ip addr show  # Modern alternative to ifconfig
ping          # Check connectivity and latency
traceroute    # View network path
dnslookup     # Resolve hostnames
netstat -r    # Routing table
```

---

## 5. Network Infrastructure Components

| Device | Function                                  |
| ------ | ----------------------------------------- |
| Switch | Forwards frames by MAC address (Layer 2)  |
| Router | Forwards packets by IP address (Layer 3)  |
| Hub    | Broadcasts traffic to all ports (Layer 1) |
| NAT    | Translates private to public IP addresses |
| DHCP   | Dynamically assigns IP addresses          |

---

## 6. DNS and Protocols

### 6.1 DNS (Domain Name System)

* Resolves human-friendly names into IP addresses (e.g., `www.example.com → 93.184.216.34`).

### 6.2 Protocol Overview

| Protocol   | Type     | Usage                |
| ---------- | -------- | -------------------- |
| TCP        | Reliable | Web, email, SSH      |
| UDP        | Fast     | Streaming, DNS, VoIP |
| ICMP       | Utility  | Ping, traceroute     |
| HTTP/HTTPS | Web      | Browsing, APIs       |
| FTP/SCP    | File     | File transfer        |
| SSH        | Secure   | Remote access        |

---

## 7. TOR and INFN-CNAF

* **TOR (The Onion Router)**: Uses layered encryption for anonymous routing.
* **INFN-CNAF**: Italian national Tier-1 datacenter, provides high-speed network for Grid computing (used by CERN, LHC).

**Connection to other modules**: Grid/HTC nodes at INFN communicate securely over WAN using the protocols defined in this networking module.

---

## 8. Network Metrics and Performance

| Metric      | Definition                               | Unit        |
| ----------- | ---------------------------------------- | ----------- |
| Latency     | Time delay for a packet to travel        | ms          |
| Bandwidth   | Max capacity of a link                   | Mbps / Gbps |
| Throughput  | Actual data transmitted per unit of time | Mbps        |
| Packet Loss | Percentage of packets dropped            | %           |

---

## 9. Crosslinks to Other Topics

**IoT/Edge**: Require low-latency networks for real-time response.
**Cloud (VPCs)**: Use virtual networks, subnets, and gateways.
**Containers**: Rely on bridge networks or host networking.
**HTC/HPC**: High-speed interconnects like InfiniBand critical for scaling.
**Storage systems (NAS/SAN)**: Depend on reliable networking for file/data access.
**Security**: Networking firewalls, proxies, and VPNs.

---

## Summary

Networking is a core enabler of all distributed computing paradigms. Understanding its protocols, infrastructure, and performance metrics is essential for effective use of cloud, edge, IoT, and HPC resources.

Next → See `README_computing.md` for computing farms, job scheduling, and batch systems.

