# Job Scheduling
This folder contains key visual representations of job scheduling strategies and architectures in distributed computing infrastructures, particularly for HTC (High-Throughput Computing) and HPC (High-Performance Computing) environments.

`HTC-HPC-workflow.png`

This image illustrates different types of job execution workflows in HTC/HPC environments:

Shapes represent different types of tasks: rectangles for parallel HPC runs, ovals for scalar pre/post-processing.

Arrows indicate logical dependencies and data flow, which can be local or remote depending on the infrastructure.

These workflows show common patterns such as task parallelism, pipelines, and fan-in/fan-out stages.

Connection: This representation is essential for understanding how jobs are broken into sub-tasks, which are then managed by scheduling systems and queued appropriately (queue.png).

`job-management-service.png`

This architecture diagram shows how a Job Management System (JMS) works:

Users submit jobs via a UI (e.g., job monitor, submission panel).

Services like monitoring, accounting, and cataloging support the job lifecycle.

Agents distribute jobs to resources across sites or grid systems.

Connection: This image bridges the conceptual gap between abstract workflows (HTC-HPC-workflow.png) and real-world resource orchestration. It shows how jobs are handled, tracked, and distributed after they are submitted.

`queue.png`

This image illustrates the concept of pilot-based job scheduling:

A central queue accepts job requests.

A factory requests resources, then launches pilot jobs via a gateway on the target infrastructure.

The pilot executes multiple payload jobs, allowing for efficient resource utilization.

Connection: This diagram complements the previous two:

It shows how jobs move from abstract representation (`HTC-HPC-workflow.png`) through submission and management (`job-management-service.png`), down to actual execution and resource binding.

## Summary of Connections

From logic to execution: The flow starts from structured workflows (`HTC-HPC-workflow.png`), goes through a job lifecycle management system (`job-management-service.png`), and ends with dynamic, pilot-based execution (`queue.png`).

Resource optimization: By using queues and pilot jobs, the infrastructure maximizes job throughput and hardware utilization, which is critical in large-scale HTC/HPC systems.
