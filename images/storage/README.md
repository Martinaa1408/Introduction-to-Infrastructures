# Storage Systems – Images & Concepts
This folder contains illustrative diagrams related to data storage systems used in modern infrastructure. The images are organized around core concepts and highlight the architectural, topological, and functional differences between various storage models.

## Images and Descriptions

`1. filesystem.png – File System Hierarchy`
A tree-based representation of a classic file system showing folders and files. Each node illustrates how directories and files are connected hierarchically. Useful to understand how data is logically structured on disk and accessed via paths.

Concepts: File system, hierarchy, directory, path, data organization.


`2. LAN-WAN-FARM.png – Storage Topology in HPC Environments`
A detailed schematic of an HPC (High Performance Computing) infrastructure that integrates LANs, WANs, and compute node farms (WNs) with IB SAN, FC SAN, SSDs, and tape libraries. It highlights high-bandwidth connections and the data flow through metadata servers, GridFTP, and various storage subsystems.

Concepts: SAN (Storage Area Network), FC (Fibre Channel), IB (InfiniBand), GridFTP, SSD, tape, throughput, multi-tier architecture.


`3. DAS.png – Direct Attached Storage (DAS)`
This image shows a DAS setup, where a server is directly connected to a JBOD (Just a Bunch Of Disks) using SAS cables and an HBA (Host Bus Adapter). It demonstrates a local, non-networked storage system.

Concepts: DAS, JBOD, HBA, SAS cable, local storage, direct connection.


## Cross-Image Connections
DAS vs SAN: While `DAS.png` shows a direct and isolated storage model, `LAN-WAN-FARM.png` demonstrates shared, scalable networked storage (SAN) suitable for large-scale environments.

`filesystem.png` illustrates the logical layer of storage, which applies to any physical architecture (DAS, SAN, NAS).

`LAN-WAN-FARM.png` presents a high-performance, multi-tiered infrastructure, whereas DAS.png focuses on simplicity and locality.

## Section Purpose
This folder visually supports the understanding of:

-Data management and storage models.

-Differences between direct and networked storage.

-Real-world architectures used in datacenters and HPC infrastructures.


