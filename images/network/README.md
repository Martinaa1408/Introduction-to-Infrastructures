# README: Network Section – Introduction to Infrastructures

This README explains the **networking concepts and infrastructure layers** through visual diagrams contained in this repository. Each image highlights a specific layer, topology, or protocol important for understanding data flow and communication in computing systems and data centers.

---

## Overview

Networking is the backbone of any distributed or cloud infrastructure. This section includes concepts ranging from the physical layout of data centers to abstract communication models like the **OSI model**, and practical tools like routers, switches, and TOR architectures.

---

## Image Explanations

### `hub-switch-router.png` – **Basic Network Devices**

* **Hub:** Broadcasts data to all devices; no filtering.
* **Switch:** More intelligent; sends data only to the intended device using MAC addresses.
* **Router:** Connects different networks (e.g., LAN to Internet), performs IP routing.

*Keywords: LAN, broadcast, switching, MAC address, routing.*

### `TOR.png` – **Top-of-Rack (TOR) Network Architecture**

* Shows how **rack-mounted servers** are connected to a **Top-of-Rack switch**, which then connects to an **aggregation switch**.
* Common in modern **data center designs** for scalability and modular cabling.

*Keywords: TOR, data center, scalability, modular, aggregation switch.*

### `OSI-model.png` – **OSI 7-Layer Model**

* Visual breakdown of the **7 abstraction layers**:

  1. Physical (bit transmission)
  2. Data Link (MAC)
  3. Network (IP routing)
  4. Transport (TCP/UDP)
  5. Session (connection control)
  6. Presentation (encryption, formatting)
  7. Application (user services)

*Keywords: OSI layers, encapsulation, abstraction, protocols.*

### `OSI-TCP.png` – **OSI vs TCP/IP Comparison**

* Shows **layer mapping** between the OSI model and TCP/IP stack.
* Highlights **protocols at each level**, such as HTTP (App), TCP/UDP (Transport), IP (Network), Ethernet (Data Link).

*Keywords: TCP/IP, OSI comparison, layers, protocols, mapping.*

### `INFN-CNAF.png` – **INFN and LHCONE Networking Infrastructure**

* Depicts high-speed connections between **INFN Tier-1 center (CNAF)** and the **LHC (CERN)**.
* Includes LHCOPN and LHCONE networks, with **40Gb/s–200Gb/s links**.
* Key point: **national and international research networks**, redundancy, and high-performance transfer.

*Keywords: INFN, CNAF, LHC, Tier-1, GARR, LHCONE, high throughput.*

### `Network-Topologies.png`

*Bus Topology

All devices are connected to a single central cable (the bus or backbone).
Data travels in both directions along the cable until it reaches the destination.
Simple and cost-effective, but not scalable and prone to collisions.

*Star Topology

All devices are connected to a central hub or switch.
If one connection fails, it doesn’t affect the others, but if the hub fails, the whole network goes down.
Common in modern Ethernet networks.

*Ring Topology

Devices are connected in a circular loop.
Data travels in one direction (or both in a dual ring).
Failure in one node can disrupt the network unless it's a dual ring.

*Mesh Topology

Every device is connected to every other device.
High redundancy and reliability.
Expensive and complex to implement, used in critical systems like military or banking.

*Tree Topology

A combination of star and bus topologies.
Devices are connected in a hierarchical manner (root → branches).
Common in large organizations and structured networks.

*Point-to-Point Topology

Direct connection between two devices only.
Simple and fast, ideal for dedicated links like between two routers.

---

## Connections Between the Images

* The **OSI and TCP/IP models** provide a conceptual framework for understanding **how data moves** through the system.
* Devices like **routers, switches, hubs** map to physical and data link layers in the OSI model.
* The **TOR architecture** implements physical connectivity in a **modular and scalable fashion** within a data center.
* The **INFN diagram** shows a real-world application of high-speed scientific networks like LHCONE.

---

## Summary

This collection gives a **complete view of network components and their logical architecture**, from basic device functions to advanced datacenter connectivity. It ties together theoretical models (OSI, TCP/IP), hardware setups (switches, routers, TOR), and real-world implementation (INFN–CERN links), forming a solid foundation for anyone studying **network infrastructures in Big Data and HPC environments**.
