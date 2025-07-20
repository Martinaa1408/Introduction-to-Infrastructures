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

#### Bioinformatics tool -->

`BWA – Burrows-Wheeler Aligner (fast, memory-efficient, short-read)`
→ A software package for aligning short sequencing reads to a large reference genome using the Burrows-Wheeler Transform.

`BLASTN – Basic Local Alignment Search Tool for Nucleotides (sensitive, local, comparative)`
→ Finds regions of similarity between nucleotide sequences using local alignment.

`FASTQ (text-based, compressed, annotated)`
→ A format for storing biological sequences with associated quality scores (Phred).

`FASTA (simple, universal, plain-text)`
→ Format for representing nucleotide or protein sequences using single-letter codes and a header.

`SAM / BAM – Sequence Alignment Map / Binary Alignment Map (structured, indexed, large-scale)`
→ Formats for storing alignments of sequencing reads to a reference genome. BAM is the binary compressed version of SAM.

`Indexing (pre-processed, searchable)`
→ Process of building a reference index to enable fast alignment (BWT-based for BWA).

`Alignment (mapping, positional, comparative)`
→ The process of positioning sequencing reads relative to a reference genome.

`Reference Genome (representative, species-specific)`
→ A standard genome sequence used as the baseline for read alignment.

`Checksum (fixed-size, unique, integrity-based)`
→ A value calculated from a data set to detect changes or corruption during transfer or storage.

---Command---

-->Step 1: Create index
`bwa index ref.fasta`

-->Step 2: Align reads
`bwa mem ref.fasta sample_R1.fastq > sample.sam`

-->Step 3: Convert and sort
`samtools view -Sb sample.sam | samtools sort -o sample_sorted.bam`

-->Step 4: Index BAM
`samtools index sample_sorted.bam`

`md5sum file.txt` → Generates an MD5 checksum of the file.

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

#### Cloud computing -->

`Cloud Computing (elastic, on-demand, shared, scalable)`
→ A model for delivering computing services over the internet based on pay-per-use and abstraction.

`IaaS – Infrastructure as a Service (low-level, configurable)`
→ Users manage middleware, runtime, and apps (e.g. AWS EC2).

`PaaS – Platform as a Service (code-driven, abstracted)`
→ Users deploy code and data; providers manage runtime, OS, etc. (e.g. Heroku, GCP App Engine).

`SaaS – Software as a Service (managed, ready-to-use)`
→ Users access software via browser/API. No control over infrastructure (e.g. Gmail, Dropbox).

`Elasticity (dynamic, auto-scaling)`
→ The system can scale resources up/down automatically.

`On-Demand Self Service (user-driven, instant)`
→ Users can provision computing capabilities automatically without human interaction.

`Multi-tenancy (shared, isolated)`
→ Resources are shared between multiple users, logically separated.

`Cloud-native (stateless, scalable, fault-tolerant)`
→ Applications designed to fully exploit the cloud (e.g. containers, microservices).

`Cloud-aware (adapted, compatible)`
→ Legacy apps modified to run in the cloud (but not natively designed for it).

---Command---

`aws ec2 run-instances`
→ Launch virtual machines on AWS.

`aws s3 cp file s3://bucket/`
→ Upload file to Amazon S3 (object storage).

`gcloud compute instances create`
→ Create VM on Google Cloud.

`az vm create`
→ Create VM on Azure.

`docker run`
→ Often used with containers on IaaS.

---

### Grid Computing -->

`Grid Computing (federated, distributed, shared)`
→ A coordinated resource sharing infrastructure that connects institutions and datacenters.

`WMS – Workload Management System (distributed, automated)`
→ Submits jobs, matches to computing resources.

`CE – Computing Element (entry-point, authenticated)`
→ The access point to a local resource where jobs are received.

`WN – Worker Node (executable, stateless)`
→ Node where the job actually runs.

`VO – Virtual Organization (collaborative, logical)`
→ A group of users with shared access and policies.

`VOMS – Virtual Organization Membership Service (identity-based, role-aware)`
→ Manages roles, groups, and permissions in grid computing.

`Proxy Certificate (temporary, delegated)`
→ A limited-lifetime certificate that grants grid credentials without exposing private keys.

`LCG – LHC Computing Grid`
→ One of the first large-scale grid infrastructures, used at CERN.

`EGI – European Grid Infrastructure`
→ Modern evolution of LCG, offering pan-European grid services.

---Command---

`voms-proxy-init`
→ Creates a proxy certificate for secure authentication in grid.

`glite-wms-job-submit -a job.jdl`
→ Submits a job using JDL (Job Description Language).

`lcg-cp, lcg-ls`
→ Copy or list files in grid storage.

`edg-job-status, edg-job-cancel`
→ Monitor or cancel a job.

---

#### Conteiner and Docker -->

`Container (lightweight, portable, isolated, ephemeral)`
→ OS-level virtualization unit that packages code and dependencies together.

`Image (immutable, layered, reusable)`
→ A read-only template used to create containers.

`Docker (popular, platform-independent)`
→ The most widely adopted container engine.

`Dockerfile (scripted, layered, declarative)`
→ File used to define and build a Docker image.

`Docker Compose (multi-service, YAML-based)`
→ Tool for defining and running multi-container applications.

`Registry (centralized, remote, versioned)`
→ A server that stores and distributes Docker images (e.g. Docker Hub).

`Volume (persistent, shared, mounted)`
→ A directory stored outside the container filesystem for saving data.

`Bind Mount (direct, host-based)`
→ A type of volume that maps a specific directory on the host into the container.

`OverlayFS (union, layered)`
→ A copy-on-write filesystem used to implement container layering.

`Namespace (isolated, kernel-level)`
→ Provides separation between container and host for resources like PID, network, filesystem.

`Control Group (cgroup) (restricted, hierarchical)`
→ Limits and monitors CPU, memory and I/O of containers.

`uDocker (unprivileged, portable, rootless)`
→ Docker-like tool for executing containers in user space, no root needed.

`Ephemeral (short-lived, disposable)`
→ Container data is lost after stopping unless a volume is used.

`Stateless (replicable, self-contained)`
→ Container does not retain internal state after execution.

`Rootless (non-privileged, sandboxed)`
→ Container can run without root permissions.

---Command--

`docker build -t myimg`
→ Build an image from a Dockerfile.

`docker run -it myimg`
→ Run an image interactively in a terminal.

`docker ps`
→ List running containers.

`docker stop <ID>`
→ Stop a running container.

`docker pull <image> / docker push <image>`
→ Download/upload images from/to a registry.

`docker volume create`
→ Create a persistent volume.

`docker-compose up`
→ Start multi-container services defined in docker-compose.yml.

`udocker pull <image> / udocker run <image>`
→ Run container in user space (no root needed).

---

#### Performance - Amdahl Law -->

`Performance (quantitative, measurable)`
→ How efficiently a system completes a task, often measured in time, speed, or resource utilization.

`Throughput (global, aggregated)`
→ Total amount of work done per unit of time (e.g., jobs/sec, MB/s).

`Latency (individual, per-operation)`
→ Time between the start and completion of a single task.

`Scalability (horizontal, vertical, efficient)`
→ The system's ability to handle increased load by adding resources (scale-up/scale-out).

`Speedup (relative, performance-based)`
→ Ratio of serial execution time to parallel execution time.

`Efficiency (normalized, per-CPU)`
→ Ratio of speedup to the number of processors used.

`Amdahl's Law (theoretical, limiting)`
→ A formula that predicts the theoretical maximum speedup achievable using parallel computing.

`Parallelism (concurrent, subdivided)`
→ The degree to which a computation can be executed in parallel.

`Bottleneck (limiting, sequential)`
→ A component or task that restricts overall performance.

`Strong Scaling (fixed-size, time-reduction)`
→ Measures performance increase when adding resources to solve the same-sized problem faster.

`Weak Scaling (problem-size growing)`
→ Measures performance when increasing both the problem size and resources proportionally.

---Command---

`time ./program`
→ Measures real, user, and system execution times.

`top, htop`
→ Shows CPU and memory usage of running processes.

`perf stat ./binary`
→ Linux performance analysis tool (cycles, instructions, etc.).

---

#### HPC and HTC -->

`HPC – High Performance Computing (tightly coupled, parallel, low-latency)`
→ Computing model focused on solving complex problems using parallel processing on supercomputers or clusters. Tasks are tightly synchronized.

`HTC – High Throughput Computing (loosely coupled, long-term, job-centric)`
→ Computing model focused on delivering large numbers of tasks over time, often independent and asynchronous.

`Supercomputer (powerful, centralized, expensive)`
→ Massive machine with thousands of processors, designed for HPC workloads (weather simulation, molecular dynamics).

`Cluster (modular, local, distributed)`
→ Group of networked computers that work together and appear as a single system.

`Job Queue (ordered, dynamic)`
→ A list of pending jobs managed by a batch system.

`Task Granularity (coarse/fine-grained)`
→ Describes how computational work is divided (fine = many small tasks, coarse = fewer larger ones).

`Interconnect (fast, low-latency, fabric)`
→ High-speed communication layer in HPC systems (e.g., Infiniband).

`Scalability (strong, weak, linear)`
→ Ability of a system to increase performance as more resources are added.

`Job Parallelism (data-parallel, task-parallel)`
→ Whether tasks work on the same data (data-parallel) or different workloads (task-parallel).

`Latency-Sensitive (HPC)`
→ HPC tasks are sensitive to delays in communication.

`Throughput-Oriented (HTC)`
→ HTC systems prioritize the volume of tasks completed over time.

---Command---

`condor_q`, `condor_submit`, `condor_status` → Used in HTC environments (HTCondor).

`mpirun -np N ./prog` → Used in HPC to launch parallel MPI jobs.

`pbsnodes, qsub, squeue, sbatch` → Job submission in SLURM, PBS, etc.


#### IoT, Edge & Fog Computing -->

`IoT – Internet of Things (connected, distributed, embedded)`
→ A network of physical devices (sensors, actuators, appliances) embedded with software and connectivity to collect and exchange data.

`Edge Computing (low-latency, near-source, decentralized)`
→ Processing data at the edge of the network, close to where it is generated, to reduce latency and bandwidth usage.

`Fog Computing (intermediate, hierarchical, layered)`
→ Architecture that extends cloud capabilities to the network edge, providing computation, storage, and networking closer to end devices.

`Cloud Computing (centralized, scalable, elastic)`
→ Remote, centralized computing resources delivered over the internet.

`Sensor (embedded, passive)`
→ A device that detects and measures physical conditions (e.g., temperature, pressure).

`Actuator (mechanical, responsive)`
→ A device that acts upon the environment based on commands (e.g., turning on a fan).

`Digital Twin (virtual, synchronized, data-driven)`
→ A digital replica of a physical object or system that synchronizes in real-time using IoT data.

`Latency (delay-sensitive, time-critical)`
→ The time taken for a signal to travel from sender to receiver and back.

`Real-time (immediate, deterministic)`
→ System that processes and responds to input within a guaranteed time.

`Bandwidth (limited, shared)`
→ The data capacity of a communication channel.

`Data Aggregation (summarized, fused)`
→ Combining data from multiple sources before sending to cloud.

`Resource-constrained (limited, low-power)`
→ Devices with limited computing, memory, and energy capabilities.

`Gateway (interfacing, protocol-bridging)`
→ A node that connects edge/IoT networks to the internet or fog layer.

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
