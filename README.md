## BDP1_2025 - Introduction to Big Data Processing Infrastructures

**Welcome to the official repository of the BDP1 2025 course!**  
This repository contains educational resources, lecture summaries, quizzes, and exam preparation material for the *Introduction to Big Data Processing Infrastructures* course, part of the MSc in Bioinformatics.

---

## Abstract and Information

The course will provide basic concepts of Computing Infrastructures for processing Big Data and for running scientific applications. In particular it will focus on the Infrastructure-as-a-Service Cloud paradigm. 
The course will provide an introduction to Big Data and how they are related to scientific  applications. 
It will continue with a description of the building blocks of modern Data Centers and how they are abstracted by the Cloud computing models. 
A real-life computational challenge will be given and students will create (during the course) a Cloud-based computing model to solve this challenge. 
Access to a limited set of Cloud resources and services will be granted to students in order to complete the exercises.  
Containers and in particular Docker Containers will be introduced as for the concept of High Performance Computing (HPC). 
Notions about the emerging “Fog” and “Edge” computing paradigms and how they are linked to Cloud infrastructures will conclude the course.

---

## RECAP

#### Big Data Chapter -->

`Big Data (massive, high-volume)`
→ Massive volume of data that exceeds the capacity of traditional tools to manage and analyze.

`5Vs (diverse, high-speed, uncertain, valuable)`
→ Volume, Velocity, Variety, Veracity, Value – the core characteristics of Big Data.

`Volume (large)`
→ Total amount of data generated and stored.

`Velocity (fast)`
→ The speed at which data is produced, transmitted, and processed.

`Variety (heterogeneous)`
→ Different types and formats of data: structured, semi-structured, unstructured.

`Veracity (noisy, unreliable)`
→ The trustworthiness and quality of the data (presence of noise, inconsistency, uncertainty).

`Value (meaningful, business-driven)`
→ The useful insight or benefit extracted from the data.

---

#### Hardware Terms – PC Components -->

`CPU (fast, parallel)`
→ Central Processing Unit. Executes instructions of programs. Can have multiple cores for parallelism.

`RAM (volatile, temporary)`
→ Random Access Memory. Temporarily holds data for currently running programs.

`SSD (persistent, fast)`
→ Solid State Drive. Fast, non-volatile storage with no moving parts.

`HDD (persistent, slow)`
→ Hard Disk Drive. Traditional magnetic disk storage, slower but cheaper.

`GPU (parallel, high-throughput)`
→ Graphics Processing Unit. Optimized for massively parallel processing (used in ML, AI, simulation).

`Power Supply (critical, stable)`
→ Converts AC power to low-voltage DC power used by internal components.

`I/O Devices (external, interactive)`
→ Input/output peripherals such as keyboard, mouse, display, storage drives.

---

#### Networking -->

`MAC Address (unique, physical, hardware-based)`
→ Media Access Control address: a hardware identifier assigned to a network interface card (NIC), used in Layer 2 of OSI model.

`IP Address (logical, routable, unique)`
→ Internet Protocol address: logical identifier assigned to devices, used in Layer 3 (IPv4 or IPv6).

`Subnet (logical, bounded)`
→ A smaller network segment within a larger IP network, defined by a subnet mask.

`MTU (fixed, limiting)`
→ Maximum Transmission Unit: the largest packet size that can be transmitted without fragmentation.

`Switch (smart, local, fast)`
→ A Layer 2 device that forwards packets based on MAC address.

`Hub (simple, obsolete, broadcast-only)`
→ A basic network device that rebroadcasts all packets to every port.

`Router (intelligent, multi-network)`
→ A Layer 3 device that forwards packets between different IP networks.

`NAT (translating, dynamic)`
→ Network Address Translation: maps internal private IPs to a public IP.

`DNS (resolving, hierarchical)`
→ Domain Name System: translates human-readable domain names into IP addresses.

`QoS (prioritized, quality-based)`
→ Quality of Service: mechanism to prioritize certain traffic over others.

`Latency (delayed, measured in ms)`
→ The time taken for a packet to travel from source to destination.

`Bandwidth (wide, rate-based)`
→ Maximum data transfer capacity of a network connection, usually in Mbps or Gbps.

--Command--

`ping IP_or_domain`
→ Sends ICMP echo requests to test connectivity and measure latency.

`traceroute domain`
→ Shows the path that packets take through the network to reach a destination.

`ip addr show / ip a`
→ Displays IP and MAC addresses of all network interfaces.

`netstat -rn`
→ Displays routing table and network connections.

`ifconfig (legacy)`
→ Shows IP address and status of network interfaces.

`dig domain.com / nslookup domain.com`
→ Queries DNS servers to resolve domain names to IPs.

---

#### Batch system and scheduling -->

`Batch System (non-interactive, automated)`
→ A non-interactive job execution system where jobs are queued and run without user intervention.

`Job Scheduler (centralized, policy-based)`
→ Manages how jobs are placed in the queue and which node executes them, based on priority, fairness, etc.

`HTCondor (distributed, high-throughput)`
→ High Throughput Computing system that allows users to submit large numbers of jobs across a pool of machines.

`Job States (sequential, status-based)`
→ Typical states: Submitted → Queued → Running → Completed/Failed.

`Queue (ordered, prioritized)`
→ The waiting list of jobs, often sorted by priority, submission time, and resources.

`Wrapper Job / Pilot Job (placeholder, dynamic)`
→ Job that reserves resources and pulls real payload jobs later from a central queue (common in grid/cloud).

`Fair Share Scheduling (adaptive, proportional)`
→ Scheduling algorithm that assigns CPU based on past usage by users to ensure balanced access.

`Backfilling (opportunistic, optimizing)`
→ Strategy that fills small idle slots with low-resource jobs without delaying high-priority ones.

`Sandbox (isolated, controlled)`
→ Temporary environment where job execution is contained (input, output, logs, errors).

`Slot (atomic, assignable)`
→ A resource unit (CPU + memory) available for job execution.

`Priority (weighted, dynamic)`
→ Metric used by the scheduler to sort jobs in the queue (can be static or usage-based).

--Command--

`condor_submit job.sub`
→ Submits a job described in the .sub file to HTCondor.

`condor_q`
→ Displays the job queue with all current submissions and their statuses.

`condor_status`
→ Shows status of all machines and resources in the HTCondor pool.

`condor_rm <jobID>`
→ Removes a job from the queue (cancellation).

`condor_history`
→ View historical information about completed jobs.

`chmod +x script.sh`
→ Makes a script executable, often required before submission.


---

#### File system and storage -->

`Filesystem (hierarchical, mounted, structured)`
→ A method to organize, store, and retrieve files on a storage device.

`POSIX (standardized, compatible, UNIX-like)`
→ Portable Operating System Interface: a standard that defines compatibility in UNIX systems (e.g. file I/O, permissions).

`Mount Point (binded, accessible)`
→ Directory where a device or partition is attached to the global file hierarchy.

`Partition (bounded, logical)`
→ A defined section of a disk treated as a separate storage unit.

`Block Device (addressable, sequential)`
→ Storage that reads/writes data in blocks (e.g., SSDs, HDDs).

`Inode (metadata-rich, indexed)`
→ A structure containing metadata (owner, permissions, timestamp) for a file.

`File Descriptor (numeric, process-specific)`
→ An integer associated with an open file (e.g., stdin = 0, stdout = 1, stderr = 2).

`EXT4 / XFS / Btrfs (journaled, robust, scalable)`
→ Popular Linux filesystems with different performance and reliability features.

`FUSE (user-space, flexible)`
→ Filesystem in Userspace: allows custom filesystems to run without kernel code.

`DAS – Direct Attached Storage (simple, direct)`
→ Physically connected to a single computer, not shared.

`NAS – Network Attached Storage (shared, file-level)`
→ File-level storage shared via network protocols like NFS or SMB.

`SAN – Storage Area Network (block-level, high-performance)`
→ Dedicated storage network providing access at block level (via iSCSI, FC).

`Object Storage (unstructured, scalable, flat)`
→ Stores data as objects (e.g. S3) with metadata and unique ID instead of traditional path hierarchy.

`RAID – Redundant Array of Independent Disks (redundant, fault-tolerant)`
→ Combines multiple disks to improve performance or fault tolerance.

`Striping (parallel, performance-optimized)`
→ Data is split across multiple disks (RAID 0).

`Mirroring (duplicated, redundant)`
→ Identical copies of data on two or more disks (RAID 1).

--Command--

`lsblk` – lists block devices (disks, partitions)

`df -h` – disk usage (human-readable)

`mount` – mount a filesystem

`umount` – unmount a device

`blkid` – shows device UUID and filesystem type

`mkfs.ext4 /dev/sdX1` – format a partition with ext4

`fsck /dev/sdX1` – check and repair filesystem

`du -sh /path` – size of a directory

`tune2fs` – modify ext2/ext3/ext4 parameters










---

## SLIDE

- [🔎Google Drive](https://drive.google.com/file/d/1wzA1xtHW14hh-PvJJcho1k4J8ZIhmPxt/view?usp=sharing)
  
---

## Official Course Repository

For additional materials, examples, and practical exercises, visit the instructor's GitHub repository:  

👉 [https://github.com/dcesini/BDP1_2025](https://github.com/dcesini/BDP1_2025)

Other repository related to the course of Infrastructures for Big Data Processing:

👉 [https://github.com/alexcos78/bdp2](https://github.com/alexcos78/bdp2)

---


## Purpose

This PDF serves as a **comprehensive study guide** for the entire BDP1 course, bringing together all theoretical and practical elements into a single, well-structured document.
