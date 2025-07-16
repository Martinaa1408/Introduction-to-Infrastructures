# README: Computing Farms, Batch Systems and File Storage

## Overview

This module focuses on computing infrastructures and data handling in distributed environments. It explains how computing farms are structured, how job scheduling works, and the types of file systems and storage used. It also links these components with networking and cloud infrastructure previously discussed, setting the foundation for advanced HPC and HTC models.

---

## 1. What is a Computing Farm?

A **computing farm** (or compute cluster) is a collection of interconnected nodes used to process tasks in parallel or in batch mode.

### Main Components:

* **Submit Node**: Entry point for users to submit jobs.
* **Worker Nodes**: Nodes that execute the jobs.
* **Shared Filesystem**: Centralized location where input/output is shared.
* **Scheduler**: Software managing job distribution.

> Connection: Requires strong LAN and shared storage access (see Networking module).

---

## 2. Batch Systems: Anatomy and Scheduling

Batch systems are used to manage large volumes of computational tasks that are queued and executed as resources become available.

### Core Concepts

* **Job**: A unit of computation submitted by the user.
* **Queue**: Where jobs are stored until scheduled.
* **Scheduler**: Controls job priority and assignment (e.g., HTCondor, SLURM).

### Scheduling Strategies

| Strategy               | Description                            |
| ---------------------- | -------------------------------------- |
| First Come First Serve | Jobs run in order of arrival           |
| Fair Share             | Balances load between users            |
| Backfilling            | Fills gaps in schedule with short jobs |
| Reservation            | Allocates specific time for a job      |

### Job Types

* **Interactive**: Immediate execution for debugging.
* **Batch**: Queued and scheduled.
* **Parallel**: Multi-core or multi-node execution.

---

## 3. HTCondor and Job Lifecycle

HTCondor is a popular batch system designed for High Throughput Computing (HTC).

### Job Lifecycle

1. **Submit** (`condor_submit`)
2. **Queue**
3. **Matchmaking**
4. **Execute** on a worker node
5. **Complete / Retry / Hold**

### Practical Concepts

* **ClassAds**: Describe job requirements and machine attributes.
* **Pilot Jobs**: Start a generic job that pulls real tasks dynamically.
* **Sandboxes**: Input (ISB) and output (OSB) packaging environments.

> Connection: Often used in distributed research environments like INFN-CNAF or WLCG.

---

## 4. Storage Systems and Data Access

Storage systems are critical to support I/O in batch and cloud jobs.

### Storage Architectures:

* **DAS (Direct Attached Storage)**: Local to node, fast, not sharable.
* **NAS (Network Attached Storage)**: File-level sharing over network.
* **SAN (Storage Area Network)**: Block-level storage, ideal for databases or VM disks.

| Type | Access Level | Use Case                |
| ---- | ------------ | ----------------------- |
| DAS  | Local disk   | Temporary scratch space |
| NAS  | File system  | Central file server     |
| SAN  | Raw blocks   | Virtual machines, DBs   |

### File System Models

* **POSIX-compliant**: Linux file systems, strict hierarchy.
* **Parallel FS (e.g., Lustre)**: High performance, scalable.
* **Distributed FS (e.g., HDFS, Ceph)**: Fault-tolerant, for big data.

---

## 5. Hierarchical Storage Management (HSM)

HSM systems automatically move data between high-performance and long-term storage tiers.

### Features

* **Migration**: Move data from SSD → HDD → Tape.
* **Recall**: Retrieve data on demand.
* **QoS (Quality of Service)**: Define policies for storage levels.

---

## 6. Crosslinks to Other Domains

**Cloud**: Batch systems can run in virtual clusters (e.g., AWS Batch).
**HPC/HTC**: Rely on efficient job scheduling and scalable storage.
**Networking**: NAS and SAN systems require stable and fast networks.
**Containers**: Can be used as job payloads in batch systems.

---

## Summary

Computing farms and batch systems form the backbone of large-scale scientific and industrial workloads. Their efficiency relies on effective scheduling and robust storage. Technologies like HTCondor, SAN/NAS, and HSM integrate with cloud and HPC environments to ensure scalable and flexible computation.

Next → See `README_hpc_cloud.md` to explore grid computing, high performance, and cloud-based infrastructures.

