# README: HPC, HTC, Grid and Cloud Infrastructures

## Overview

This module explores advanced distributed computing paradigms including High Performance Computing (HPC), High Throughput Computing (HTC), Grid systems, and Cloud architectures. These models differ in workload management, scalability, interconnects, and the underlying philosophies for computation and resource distribution. Connections with job scheduling, virtualization, and batch systems are also emphasized.

---

## 1. HPC vs HTC

| Feature   | HPC                         | HTC                            |
| --------- | --------------------------- | ------------------------------ |
| Job Type  | Tightly-coupled, parallel   | Loosely-coupled, independent   |
| Runtime   | Shorter, fixed              | Long-running, flexible         |
| Hardware  | Supercomputers, Infiniband  | Commodity clusters, LAN        |
| Scheduler | SLURM, PBS                  | HTCondor                       |
| Use Cases | Weather models, simulations | Parameter sweeps, NGS analysis |

> Connection: Both rely on computing farms (see `README_computing.md`) and efficient job queuing.

---

## 2. Grid Computing Paradigm

**Grid computing** coordinates geographically distributed resources across administrative domains. Often used in scientific collaborations (e.g., CERN).

### Features:

* **Federated Authentication**: Tools like MyProxy, VOMS.
* **Job Submission Models**: Through WMS (Workload Management Systems).
* **Middleware**: Glue between clusters, e.g., ARC, gLite.
* **Security**: PKI infrastructure and sandboxing.

### Grid Job Lifecycle:

1. Submit via UI (User Interface)
2. WMS matches resource
3. Pilot job or direct job scheduling
4. Output returned to UI or storage element

> Example: INFN-CNAF supports Grid Tier-1 infrastructure for LHC experiments.

---

## 3. Performance Metrics

### Speedup and Efficiency

```text
Speedup = T_serial / T_parallel
Efficiency = Speedup / Number_of_Processors
```

### Amdahl's Law (Limit of Parallelization)

```text
Speedup_max = 1 / ((1 - P) + P / N)
```

Where:

* P: fraction of code that is parallel
* N: number of processors

### GFLOPS (Floating Point Performance)

```text
GFLOPS = Sockets × Cores/Socket × Clock × FLOPs/cycle
```

> High GFLOPS and scalability = efficient HPC system.

---

## 4. Cloud Infrastructure

Cloud platforms offer elastic compute and storage using virtualization. They abstract the hardware layer and offer services via the IaaS, PaaS, SaaS models.

### Models:

| Model | User Control    | Example Use        | Example Tools      |
| ----- | --------------- | ------------------ | ------------------ |
| IaaS  | Full VM/Storage | AWS EC2, Azure VM  | Terraform, AWS CLI |
| PaaS  | Runtime only    | App Engine, Heroku | Docker, K8s        |
| SaaS  | Just use app    | Gmail, Google Docs | Web apps           |

### Benefits

* On-demand provisioning
* Pay-per-use model
* Global scalability

> Cloud and containers go hand in hand. See `README_computing.md` and `README_IoT_Edge.md` for more.

---

## 5. Virtualization vs Static Data Centers

| Aspect       | Traditional DC | Virtualized/Cloud         |
| ------------ | -------------- | ------------------------- |
| Provisioning | Manual         | Automated (scripts, APIs) |
| Scaling      | Fixed capacity | Elastic                   |
| Cost         | CapEx          | OpEx                      |
| Flexibility  | Low            | High                      |

> Virtualization also enables container-based batch jobs in hybrid clouds.

---

## 6. Streaming vs Batch Processing

| Feature  | Batch                     | Streaming           |
| -------- | ------------------------- | ------------------- |
| Input    | Static datasets           | Real-time data      |
| Examples | MapReduce, HTCondor       | Apache Kafka, Spark |
| Latency  | High                      | Low                 |
| Use Case | DNA alignment, simulation | IoT sensor analysis |

> IoT pipelines benefit from streaming, whereas HTC prefers batch mode.

---

## Summary

From tightly-coupled HPC jobs to cloud-native streaming workflows, this module unifies compute models under a single view. Each paradigm has specific use cases and metrics to evaluate scalability and efficiency. Grid computing bridges institutions, cloud computing offers elasticity, and HPC/HTC support massive computational workloads.

Next → See `README_IoT_Edge.md` for real-time distributed systems, edge analytics, and intelligent cyber-physical integration.

