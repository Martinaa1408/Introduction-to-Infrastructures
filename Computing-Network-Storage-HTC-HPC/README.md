# Welcome to Computing-network-storage-htc-hpc repository!

This repository offers a comprehensive and modular overview of modern computational infrastructures, from network architectures to advanced paradigms like cloud computing, job scheduling, and edge computing.

The project is structured into five major components, each with its own detailed README:

---

## Repository Overview

### Core Modules

| Area                        | Description                                                      | Link                                            |
| --------------------------- | ---------------------------------------------------------------- | ----------------------------------------------- |
| Networking & Infrastructure | Network topology, OSI vs TCP/IP, nodes, DNS, hardware interfaces | [README\_networking.md](./README_networking.md) |
| Computing & Scheduling      | Batch systems, job scheduling, HTCondor, file systems            | [README\_computing.md](./README_computing.md)   |
| HPC / HTC / Cloud Systems   | Grid computing, speedup laws, PUE, service models, cloud vs VM   | [README\_hpc\_cloud.md](./README_hpc_cloud.md)  |
| Edge / Fog / IoT & Digital  | Edge computing, digital twins, IoT integration                   | [README\_edge\_iot.md](./README_edge_iot.md)    |

---

### ⚙ Glossary (Essentials)
# README: Glossary and Conceptual Links Across Infrastructure Modules

## Overview

This document summarizes key terminology and conceptual relationships across the four main modules:

* Networking
* Computing & Batch Systems
* HPC, Grid & Cloud
* IoT, Edge, Fog & Digital Twins

It acts as a glossary and conceptual map for understanding the flow from low-level infrastructure to high-level orchestration and computing paradigms.

---

## Glossary of Core Terms

| Term                   | Definition                                                        | Related Modules                       |
| ---------------------- | ----------------------------------------------------------------- | ------------------------------------- |
| **Job**                | A unit of computation scheduled and executed on a system          | Batch, Grid, Cloud, Edge              |
| **Job Scheduler**      | Software managing queueing and dispatching of jobs                | Batch, Grid (WMS), HTC, Cloud         |
| **Batch System**       | Execution environment for queued jobs, often in computing farms   | Computing, Cloud, Grid                |
| **HTC**                | High Throughput Computing: many loosely coupled jobs over time    | Grid, Bioinformatics, Cloud           |
| **HPC**                | High Performance Computing: parallelized tasks on supercomputers  | Simulation, Modeling, Physics         |
| **Grid Computing**     | Federated system of distributed compute/storage resources         | INFN, CNAF, WMS                       |
| **Cloud Computing**    | On-demand virtual compute via IaaS, PaaS, SaaS models             | AWS, Azure, Virtualization            |
| **IaaS / PaaS / SaaS** | Models describing levels of user control over infrastructure      | Cloud, Deployment                     |
| **Virtual Machine**    | Emulated hardware instance with full OS                           | Cloud, Batch, Virtualized Datacenters |
| **Container**          | Lightweight virtualized environment sharing host OS kernel        | Docker, uDocker, Cloud                |
| **Filesystem**         | Data access abstraction (POSIX, distributed, parallel)            | DAS, NAS, SAN, HSM                    |
| **Storage**            | Persistent data storage (HDD, SSD, Tape, Tiered)                  | DAS, SAN, HSM, Cloud, Edge            |
| **Throughput**         | Amount of data or tasks completed per unit time                   | HTC, Network, Batch                   |
| **Latency**            | Delay in completing a task or transmission                        | Network, HPC, IoT                     |
| **Speedup**            | Ratio of serial vs parallel execution time                        | HPC, Amdahl's Law                     |
| **GFLOPS**             | Measure of computing power (floating point operations per second) | HPC, Performance                      |
| **Node**               | Physical or virtual computing unit                                | Cluster, Cloud, Grid, Edge            |
| **Pilot Job**          | Placeholder job used to pull real tasks dynamically               | Grid, WMS                             |
| **WMS**                | Workload Management System coordinating job execution             | Grid, Tier-1, INFN                    |
| **Digital Twin**       | Virtual replica of physical system in real-time                   | IoT, Edge, Predictive Systems         |

---

## Logical Flow Across Modules

### `1. Networking`

* **Foundation Layer** for all distributed systems.
* Defines IP addressing, MAC, MTU, LAN/WAN, DNS, OSI and TCP/IP models.
* Required for **Grid**, **Cloud**, **IoT** to function.

### `2. Computing & Batch Systems`

* Focus on **how jobs are queued and executed**.
* Introduces **HTCondor**, **queues**, **worker nodes**, **data locality**.
* Ties directly into cloud batch jobs, HTC patterns.

### `3. HPC, Grid & Cloud`

* Advanced compute paradigms:

  * **HPC** = parallel computing, high GFLOPS.
  * **HTC** = long-term high-volume jobs.
  * **Grid** = institutional sharing with federated access.
  * **Cloud** = elastic, on-demand, service-oriented.

* Introduces **virtualization**, **service models (IaaS/PaaS/SaaS)**, performance equations (Amdahl’s Law).

### `4. IoT, Edge & Fog (Next)`

* Extends computing to **real-time** physical environments.
* Concepts like **latency reduction**, **digital twins**, **edge intelligence**, and **fog nodes** are key.
* Links directly with streaming architectures and hybrid cloud models.

---

## Conceptual Threads and Key Links

* **Job**: Central across every domain (batch, cloud, edge). The format, orchestration, and delivery differ.
* **Computing**: Evolves from static hardware (farm) → virtual (cloud) → embedded (IoT).
* **Scheduling**: Changes from manual queueing (batch) → dynamic (cloud/grid) → decentralized (edge).
* **Data**: Moves from files (batch, DAS) → objects (cloud, S3) → streams (IoT, Kafka).
* **Security and Monitoring**: Increase in complexity from local → multi-site → real-time, user-authenticated workflows.

---

## Summary

These four README modules build an infrastructure hierarchy:

1. **Networking** enables communication between all computing elements.
2. **Batch Systems and Storage** describe how compute and data are managed locally.
3. **HPC/HTC/Grid/Cloud** scale computing across institutions and data centers.
4. **IoT/Edge/Fog** bring compute closer to the data source, enabling real-time analytics.

Understanding this landscape enables the design of efficient, scalable, and adaptable systems for research, industry, and data-intensive applications.
