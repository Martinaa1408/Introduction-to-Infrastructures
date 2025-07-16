# HTC & HPC – High Throughput and High Performance Computing
This folder contains visual diagrams illustrating different computing paradigms ranging from local server access to large-scale distributed computing and Grid infrastructures. Each image offers a step-by-step view of how users interact with computing resources, how jobs are submitted and distributed, and how data storage is managed.

`computing-on-server.png`
This image represents a simple architecture where a user connects via a jump host and a VPN to a remote server node (uil), which has access to a local DAS storage (/data/). This is the most basic model of remote computing: centralized, direct, and without job distribution or orchestration. It's ideal for standalone or small-scale computation and provides the foundation for more complex models.

`Computing-on-datacenter.png`
Here, the infrastructure evolves into a Condor cluster inside a datacenter. A master node handles job submission to several worker nodes (wn-1 to wn-4). Storage is now partially shared via NAS, allowing concurrent access by multiple nodes. The user still connects through jump host → uil, but jobs are now scheduled and distributed within the cluster. This setup introduces the concept of batch processing and parallel execution within a localized environment (LAN).

`Distributed-computing.png`
This diagram extends the datacenter model into multi-site distributed computing. Several Condor clusters (each with its own master, worker nodes, NAS, and DAS) are deployed across different sites. The user has a single point of entry (uil/jumphost) but can submit jobs across multiple clusters. This model reflects HTC (High Throughput Computing): large numbers of loosely coupled tasks are run over long timeframes, taking advantage of distributed resources. It demonstrates the complexity of job routing, resource federation, and data locality management.

`GRID-paradigm.png`
This image represents the Grid computing paradigm, where various types of users (mobile devices, workstations, visual systems) interact with a wide range of heterogeneous resources such as supercomputers, storage systems, sensor networks, and experimental platforms via a centralized Grid Middleware. The middleware acts as a broker and orchestrator, enabling seamless and secure access to distributed computing resources. This is characteristic of HPC (High Performance Computing) and scientific collaboration at global scale.

## Conceptual Connections

-From Local to Global: The journey begins with basic server access and moves through datacenters, distributed sites, and finally to Grid infrastructures.

-Storage Evolution: Starts with local DAS, then NAS for shared access, and finally integrated heterogeneous data systems in Grid.

-Job Scheduling: From manual execution to automated job submission in Condor clusters and orchestration via Grid middleware.

-User Abstraction: While computing-on-server requires direct control, GRID-paradigm offers abstraction, scalability, and fault tolerance.

> This directory provides a conceptual progression that helps understand how modern scientific computation scales in both complexity and capability, moving from HTC (throughput, long-running jobs) to HPC (performance, tightly-coupled parallel jobs).

