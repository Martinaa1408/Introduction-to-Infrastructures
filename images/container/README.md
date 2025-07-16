# 🐳 Docker & Containers: Infrastructure Overview – README

This README explains the images and key concepts related to **Docker**, **udocker**, container networking, storage, and system architecture, as presented in the repository.

---

## 1. Docker vs udocker (Image: `docker-udocker.png`)

This image compares **Docker** with **udocker**.

* **Docker** is a containerization engine that requires root privileges and a daemon.
* **udocker** is a rootless container execution tool, allowing containers to be run without root and without Docker daemon.

*Key Commands*:

```
Docker:    docker run --name=mycontainer ubuntu
udocker:   udocker run mycontainer
```

**Keywords**: container, rootless, CLI, compatibility, HPC environments

---

## 2. Docker System Architecture (Image: `docker-system.png`)

* Shows how containers are built and run using the **Docker Engine**.
* **Dockerfile** from the source repository is used to build an image.
* The image is run on a **host OS**, and pushed/pulled from the **Docker Registry**.

**Main components**:

* Docker Engine
* Container Images
* Registry (e.g., DockerHub)
* Host OS (Linux)

**Keywords**: build, run, registry, engine, OS, container

---

## 3. Docker Networks (Image: `docker-network.png`)

Three major networking types:

* **Bridge**: default, containers have separate IPs.
* **None**: no network access.
* **Host**: shares host network.

**Sample commands**:

```
docker run alpine                 # bridge

docker run --network=none alpine # isolated

docker run --network=host alpine # host
```

**Keywords**: bridge, isolation, port mapping, IP address, docker0

---

## 4. Docker Daemon and Registry (Image: `client-dockerhost-registry.png`)

* **Client** issues commands to Docker Host (daemon).
* Daemon manages **containers and images**.
* Pulls from or pushes to a remote **Registry** (e.g. DockerHub, private registries).

**Keywords**: docker daemon, client, registry, pull, push, container lifecycle

---

## 5. Storage & Mounts (Image: `tmpfs.png`)

Illustrates how Docker uses different types of **mounts**:

* **Volumes**: Managed by Docker.
* **Bind mounts**: Point to specific host paths.
* **tmpfs**: Stored in memory only, temporary.

**Keywords**: volume, bind mount, tmpfs, memory, container filesystem

---

## 6. Docker vs Virtual Machines (Image: `VM-docker.png`)

**Virtual Machines**:

* Emulate entire OS (Guest OS)
* Heavyweight: includes hypervisor

**Docker**:

* Shares host OS kernel
* Lightweight and portable

**Keywords**: VM, hypervisor, Docker Engine, guest OS, lightweight

---

## Summary of Concepts

| Component      | Description                               |
| -------------- | ----------------------------------------- |
| Docker Engine  | Core service that runs containers         |
| Container      | Lightweight, isolated process             |
| Registry       | Stores container images                   |
| tmpfs          | Temporary in-memory filesystem            |
| Volume         | Persistent storage managed by Docker      |
| Bridge network | Default isolated network for containers   |
| Host network   | Shares host IP and ports                  |
| Dockerfile     | Script to define image build instructions |
| udocker        | Rootless container runner                 |

---

## Why This Matters

This material connects directly with broader **infrastructure and cloud topics** like:

* **IaaS**: Docker/VMs on EC2 (in AWS)
* **PaaS**: Container orchestration with services like AWS ECS or Azure AKS
* **Edge Computing**: Containers deployed at the edge (lightweight)
* **Scientific Computing**: `udocker` for non-root container execution on shared HPC systems

---

## Best Use Cases

* Deploying microservices and reproducible environments
* Lightweight alternative to VMs
* Containerized scientific tools using `udocker`
* Understanding infrastructure flexibility (network, storage, runtime)

---

*This README contextualizes and explains each visual element stored in the `/images/container/` folder for Docker and container basics in the BDP1 course.*
