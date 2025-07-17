# BDP1-ALL KEY FORMULAS

### Basic Units and Storage Conversions
<pre><code> 
1 Byte (B) = 8 bits (b) 
1 Kilobyte (KB) = 1024 Bytes 
1 Megabyte (MB) = 1024 KB 
1 Gigabyte (GB) = 1024 MB 
1 Terabyte (TB) = 1024 GB 
</code></pre>

🔑 Keywords: bit, byte, storage units, conversion, memory capacity

### RAID Capacity
<pre><code> 
  RAID 0 usable capacity = N × size_of_smallest_disk 
  RAID 1 usable capacity = size_of_smallest_disk (mirrored) 
  RAID 5 usable capacity = (N - 1) × size_of_smallest_disk 
  
Let N = number of physical disks
</code></pre>

🔑 Keywords: RAID, redundancy, mirroring, striping, parity, usable capacityBDP1

### Speedup and Efficiency (Parallel Computing)
<pre><code> 
  Speedup = Performance_B / Performance_A  
  Speedup = Time_Sequential / Time_Parallel  
  Efficiency = Speedup / Number_of_Processors  
  Max Speedup = 1 / α   (where α = serial fraction)  
</code></pre>

🔑 Keywords: speedup, efficiency, parallel computing

### Amdahl’s Law
<pre><code> 
  Speedup_max = 1 / (Serial_fraction + (Parallel_fraction / N)) 
  Speedup_max (alternative) = 1 / (1 - P + P / N) 
  
P = parallelizable fraction of code
N = number of processors
</code></pre>

🔑 Keywords: Amdahl's Law, scalability, performance limitBDP1

### GFLOPS (Computing Power)
<pre><code> 
  GFLOPS = Sockets × Cores_per_Socket × Clock_Speed × FLOPs_per_Cycle 

  Sockets: number of physical CPU sockets
  Cores per Socket: how many cores per CPU
  Clock Speed: GHz, cycles per secon
  FLOPs/Cycle: floating-point ops per core per cycle
</code></pre>

🔑 Keywords: GFLOPS, floating-point, performance, CPU, GPUBDP1

### Memory Bandwidth
<pre><code> 
  Bandwidth = Base_Clock × Transfers_per_Clock × Bus_Width × Interfaces 
</code></pre>

🔑 Keywords: memory bandwidth, latency, cache, RAMBDP1

### Peak Performance and Speedup
<pre><code> 
  Speedup(B/A) = Peak_Performance_B / Peak_Performance_A
  Performance = Efficiency × Peak_Bandwidth_Capability
  Performance = Efficiency × Peak_Compute_Capability
</code></pre>

🔑 Keywords: performance theoric, bandwidth, compute capability


### Latency and Throughput
<pre><code> 
  Latency = Time to complete a single task 
  Throughput = Total tasks completed / Time 
</code></pre>

🔑 Keywords: latency, throughput, performance, response time


### Power Usage Effectiveness (PUE)
<pre><code> 
  PUE = Total Facility Energy / IT Equipment Energy  
      = 1 + (Non-IT Energy / IT Equipment Energy)

PUE = 1.0 → ideal (only IT equipment uses power)
PUE > 1.0 → realistic, includes cooling, power distribution
</code></pre>

🔑 Keywords: PUE, data center, power, cooling, energy efficiency

---
##### Speedup, Efficiency, and Amdahl’s Law help assess how well parallel systems scale and where bottlenecks occur in multi-core or distributed environments.

##### RAID Capacity is essential for understanding the reliability and performance trade-offs in storage systems — a core part of file systems, data centers, and cloud volumes.

##### Memory Bandwidth and GFLOPS allow us to estimate the compute and data transfer limits of a given architecture (CPU, GPU, memory bus), which is key in performance tuning.

##### Latency and Throughput are critical when evaluating network topology, streaming, or data transfer strategies (e.g. HPC farms, grid computing, cloud APIs).

##### PUE connects IT infrastructure to energy efficiency and sustainability — a growing priority in data centers and cloud economics.

##### CPU Time / Wall-clock Time reveal real-world resource usage, tying theory to the behavior of batch jobs, containers, or cloud workload
---
