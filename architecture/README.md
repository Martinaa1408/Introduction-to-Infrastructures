# PC Architecture and Big Data: A Comprehensive Guide

## 1. Introduction

This README provides a comprehensive overview of PC architecture and its role in modern big data processing and bioinformatics workflows. It spans from the fundamental components of a computer system to the computational needs and concepts underpinning large-scale data analysis, such as NGS (Next-Generation Sequencing) alignment.

---

## 2. PC Architecture Overview

### 2.1 Processing Units

* **CPU (Central Processing Unit):** The brain of the computer responsible for executing instructions. Includes:

  * **ALU (Arithmetic Logic Unit):** Performs arithmetic and logical operations.
  * **Control Unit:** Directs operations of the processor.
  * **Registers:** Small, fast storage inside the CPU.
  * **Cache:** Levels (L1, L2, L3) for fast access to frequently used data.
* **GPU (Graphics Processing Unit):** Specialized for parallel data processing, often used in ML and NGS.
* **Cores & Threads:** Each CPU may contain multiple cores; each core may handle multiple threads via **hyperthreading**.

### 2.2 Memory Hierarchy

| Level          | Speed     | Size       | Examples          |
| -------------- | --------- | ---------- | ----------------- |
| Registers      | Very fast | Tiny       | Inside CPU        |
| L1/L2/L3 Cache | Fast      | Small      | On-chip cache     |
| RAM            | Fast      | Medium     | DRAM              |
| SSD/HDD        | Slower    | Large      | NVMe, SATA drives |
| Tape/Cloud     | Slowest   | Very large | Backup/Archives   |

* **Latency** increases and **bandwidth** decreases from top to bottom.

<img width="697" height="503" alt="Screenshot 2025-07-16 135739" src="https://github.com/user-attachments/assets/2d27a297-38df-4a68-8023-b74cbf3a799b" />

### 2.3 Storage Systems

* **HDD (Hard Disk Drive):** Magnetic storage, high capacity, slower.
* **SSD (Solid State Drive):** Flash storage, fast read/write.
* **NVMe SSDs:** Faster than traditional SATA SSDs.
* **RAID Arrays:** Redundant data storage using multiple disks.
* **Mass Storage Systems:** Used in data centers and for scientific computing.

### 2.4 System Connectivity

* **Buses:** Connect internal components (CPU ↔ RAM ↔ I/O):

  * **Data Bus**: Transfers data
  * **Address Bus**: Transfers memory addresses
  * **Control Bus**: Sends control signals
* **I/O Interfaces:** USB, PCIe, SATA, Ethernet, Thunderbolt
* **Network Connectivity:** LAN, Wi-Fi, InfiniBand (HPC)

### 2.5 Cooling Systems

* **Active Cooling:** Fans, liquid cooling
* **Passive Cooling:** Heatsinks
* **Thermal Paste:** Enhances heat transfer

### 2.6 Power Supply

* **PSU (Power Supply Unit):** Converts AC to regulated DC power.

  * Modular or non-modular, varies by wattage

### 2.7 System on Chip (SoC)

* Combines CPU, GPU, RAM, and I/O on a single chip
* Used in: Mobile, IoT, Raspberry Pi, Embedded Systems

---

## 3. Latency and Bandwidth

| Metric    | Definition                              | Example            |
| --------- | --------------------------------------- | ------------------ |
| Latency   | Time delay between request and response | Accessing memory   |
| Bandwidth | Data transferred per unit of time       | Network throughput |

* Measured in ns (RAM), ms (Disk), μs–ms (Network)

Use `ping`, `iperf`, `time` to measure in practice.

---

## 4. Digital Units and Conversion

* **Bit (b):** Binary digit (0 or 1)
* **Byte (B):** 8 bits

### Storage Hierarchy:

* 1 KB = 1024 Bytes
* 1 MB = 1024 KB
* 1 GB = 1024 MB
* 1 TB = 1024 GB
* 1 PB = 1024 TB

### Useful Commands

```bash
cat /proc/cpuinfo    # CPU info
free -m              # Memory info in MB
df -h                # Disk usage in human-readable
lscpu                # CPU architecture
iostat, vmstat       # Performance stats
```

---

## 5. Big Data Concepts and the 5 V's

### Gartner’s Definition:

> "Big Data is high-volume, high-velocity, and high-variety information assets that demand cost-effective, innovative forms of information processing for enhanced insight and decision making."

### The 5 Vs of Big Data:

* **Volume:** Massive datasets (e.g., genomics, satellites)
* **Velocity:** Fast data inflow (e.g., sensors, finance)
* **Variety:**

  * **Structured** (tables, SQL)
  * **Semi-structured** (JSON, XML)
  * **Unstructured** (text, images, videos)
* **Veracity:** Trustworthiness of data
* **Value:** Actionable insights (analytics, decision-making)

### Analytics Types:

| Type         | Description        | Example                    |
| ------------ | ------------------ | -------------------------- |
| Descriptive  | What happened?     | CPU load reports           |
| Predictive   | What might happen? | Predicting system failures |
| Prescriptive | What should we do? | Auto-scaling resources     |

---

## 6. Bioinformatics & HPC Applications

### Algorithms for NGS Alignment

* **Brute-force:** Exhaustive comparison (slow)
* **BLASTn:** Local alignment, heuristic (fast)
* **BWA:** Fast aligner using FM-index and Burrows-Wheeler Transform

### Example Workflow with BWA

```bash
bwa index ref.fa                     # Create index
bwa mem ref.fa reads.fq > aln.sam   # Align reads
samtools view -Sb aln.sam > aln.bam # Convert to BAM
```

### Multicore & Hyperthreading

* **Multicore:** Executes tasks in parallel
* **Hyperthreading:** Virtual cores per physical core
* **Thread:** Smallest execution unit in a process

### Mass Storage and Throughput

* **RAID0/RAID5/RAID10** for fault tolerance + speed
* **Parallel I/O** frameworks (HPC clusters)

---

## 7. Data Integrity: Checksum

Checksums ensure data integrity during transfers.

```bash
sha256sum file.fastq
md5sum sample.fq.gz
```

Compare hashes before/after transmission/storage.

---

## Conclusion

This README bridges foundational PC architecture with its application in big data and bioinformatics. Understanding CPU internals, memory hierarchies, disk I/O, system commands, and checksum tools is essential for data-intensive tasks. From the latency of memory access to RAID configurations and command-line utilities, this document maps theory to practice in HPC and NGS analysis.

