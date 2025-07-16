# README – `images/intro/` Directory

This README documents and explains the educational material in the `images/intro/` folder of the **Introduction-to-Infrastructures** repository. These images provide essential visual aids for understanding topics such as computing hardware, data processing, big data properties, and infrastructure cooling systems.

---

## 1. `overviewCPU.png`

**Topic**: CPU Architecture & Operation
This diagram explains the main internal and external components of a CPU:

* **ALU (Arithmetic Logic Unit)**: performs arithmetic and logical operations
* **Control Unit**: directs the operations of the processor
* **Cache Memory**: fast-access memory for CPU operations
* **Main Memory**: general RAM used for running programs
* **Input/Output Devices**: connected peripherals
* **Backing Storage**: long-term data storage

Keywords: ALU, cache, control unit, main memory, CPU components

---

## 2. `cooling-system.png`

**Topic**: Data Center Cooling & Power Redundancy
This diagram shows a complete **IT infrastructure cooling and backup system**, including:

* **UPS (Uninterruptible Power Supply)** and **Diesel Generators**
* Dual lines for **cooling system redundancy** (green/red lines)
* Main cooling unit connected to power transfer and control stations

Keywords: cooling, UPS, redundancy, diesel engine, IT equipment

---

## 3. `bruteforce-bwa-blastn.png`

**Topic**: Algorithm Efficiency Comparison
Comparison of time (in seconds) required by different approaches to read 1 and 1000 lines of data:

* **Brute Force**: Extremely inefficient (409s / 410000s)
* **BLASTn**: Optimized search (\~0.54s / 574.1s)
* **BWA**: Best performance (\~3.2s / 3.6s)

Highlights the advantage of using **specialized bioinformatics tools** for scalability.

Keywords: brute force, BLAST, BWA, performance, bioinformatics

---

## 4. `BIGDATA.png`

**Topic**: The 4 V's of Big Data
Illustrates the core properties of big data:

* **Volume**: huge amounts of data
* **Variety**: different formats (structured/unstructured)
* **Velocity**: speed of generation and processing
* **Veracity**: reliability and truthfulness

Keywords: big data, 4Vs, unstructured, variety, velocity, veracity

---

## 5. `5Vs.png`

**Topic**: Big Data Characteristics – Extended
Expands the previous concept by adding the 5th V:

* **Value**: ability to extract useful insights from data
  Includes how big data impacts real life: sensors, logs, real-time decisions.

Keywords: value, 5Vs, data streams, data processing, insight extraction

---

## 6. `latency-bandwidth.png`

This diagram illustrates the memory hierarchy inside a processor, comparing read bandwidth (GB/s) and latency (ns, nanoseconds) at different memory levels:

Registers are the fastest units, reaching ~84 GB/s with just 2 ns latency.

L1 Cache offers ~60 GB/s bandwidth with 7 ns latency (14 cycles).

L2 Cache delivers ~30 GB/s with 26 ns delay.

L3 Cache is shared across cores (~30 GB/s, 26 ns).

Local Memory (main RAM/DRAM) is the slowest (~10 GB/s) and highest in latency (90 ns).

This hierarchy demonstrates the trade-off between speed and size: closer memory (registers, L1) is faster but limited, while deeper memory (L3, DRAM) has more capacity but is slower. These aspects are essential for performance tuning in parallel systems, scientific computing, and HPC environments.

Keywords: latency, bandwidth, cache levels, memory access, CPU architecture, DRAM, performance

---

## 7. `NUMA.png`

Non uniform memory access: multi-CPU + single-RAM (local memory)
