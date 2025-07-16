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
</code></pre>

🔑 Keywords: RAID, redundancy, mirroring, striping, parity, usable capacityBDP1

### Speedup and Efficiency (Parallel Computing)
<pre><code> 
  Speedup = T_serial / T_parallel 
  Efficiency = CPU Time / Wall-clock Time 
</code></pre>

🔑 Keywords: speedup, efficiency, parallel computing, Amdahl's LawBDP1

### Amdahl’s Law
<pre><code> 
  Speedup_max = 1 / (Serial_fraction + (Parallel_fraction / N)) 
  Speedup_max (alternative) = 1 / (1 - P + P / N) 
</code></pre>

P = parallelizable fraction of code
N = number of processors

🔑 Keywords: Amdahl's Law, scalability, performance limitBDP1

### GFLOPS (Computing Power)
<pre><code> 
  GFLOPS = Sockets × Cores_per_Socket × Clock_Speed × FLOPs_per_Cycle 
</code></pre>

🔑 Keywords: GFLOPS, floating-point, performance, CPU, GPUBDP1

### Memory Bandwidth
<pre><code> 
  Bandwidth = Base_Clock × Transfers_per_Clock × Bus_Width × Interfaces 
</code></pre>

🔑 Keywords: memory bandwidth, latency, cache, RAMBDP1

### Latency and Throughput
<pre><code> 
  Latency = Time to complete a single task 
  Throughput = Total tasks completed / Time 
</code></pre>

🔑 Keywords: latency, throughput, performance, response time


### Power Usage Effectiveness (PUE)
<pre><code> PUE = Total Facility Energy / IT Equipment Energy </code></pre>
🔑 Keywords: PUE, data center, power, cooling, energy efficiency

