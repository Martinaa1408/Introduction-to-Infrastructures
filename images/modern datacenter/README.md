# Modern Datacenter – README

This folder contains key diagrams explaining the architecture and components of a **modern datacenter**. Each image provides insight into how infrastructure is organized to support high-performance, scalable, and resilient computing systems.

---

## File: `Datacenter-component.png`

### Description:

This image provides an **overview of the main physical and logical components** of a data center:

* **CRAC (Cooling)**: Maintains temperature and humidity control.
* **UPS & Generator**: Provide power redundancy.
* **Storage (SAN)**: Dedicated network-accessible storage for multiple servers.
* **Server Farm**: Processing units that execute tasks.
* **LAN & WAN**: Internal and external networking.
* **Cabling**: Ensures connectivity between components.

### Relevance:

It shows the **holistic view of infrastructure**, necessary to understand dependencies between **power, compute, storage, and networking** inside a data center.

---

## File: `distributed-filesystem.png`

### Description:

This diagram compares:

* **SAN-based architecture**: Centralized storage accessed over the network by compute nodes (left side).
* **Distributed File System (DFS)**: Each compute node is also a storage node, eliminating central bottlenecks (right side).

### 🔗 Relevance:

Explains the shift from **centralized to distributed storage** models for better **scalability and fault-tolerance**, especially relevant in **big data** and **cloud-native** infrastructures.

---

## Conceptual Links:

* A **distributed file system** is often used in modern data centers to support **cloud storage**, **HPC**, or **containerized workloads**.
* The **SAN and server farm** models help visualize **virtualization backends**, **VM hosting**, and **container orchestration**.
* Both diagrams are complementary:

  * `Datacenter-component.png` gives the **macro-architecture**.
  * `distributed-filesystem.png` zooms into the **storage model evolution**.

---

## Summary:

These images together provide a **foundational understanding** of the technologies and layouts used in modern infrastructure management. Grasping these elements is crucial for working with:

* Cloud Platforms (IaaS, PaaS)
* HPC/HTC clusters
* Edge computing and IoT
* Containerized or virtualized environments

> Suggested prerequisite concepts: SAN, DFS, server farm, cooling systems, power redundancy, network segmentation.
