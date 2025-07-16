# AMAZON WEB SERVICES

### 1. What is AWS?

Amazon Web Services (AWS) is a cloud computing platform that provides a wide range of infrastructure services on-demand, such as compute power, storage, networking, and databases.
AWS enables users to build scalable, secure, and high-availability applications without the need to manage physical servers.
It is a practical implementation of the cloud computing model, where users can access and manage IT resources via the Internet instead of maintaining physical hardware.
AWS enables users to build scalable, secure, and high-availability applications globally, while paying only for what they use.

It is part of the cloud computing paradigm, where physical infrastructure is abstracted and offered as services such as:

-Compute (e.g., EC2 virtual machines)

-Storage (e.g., S3 object storage, EBS block volumes)

-Databases (e.g., RDS, DynamoDB)

-Networking (e.g., VPC, Load Balancer)

-DevOps, Machine Learning, Analytics, and more.

AWS is a core example of Infrastructure as a Service (IaaS), with services extending into Platform as a Service (PaaS) and Software as a Service (SaaS).
It allows you to build, deploy, and scale applications globally without managing physical servers, making it essential for modern cloud-based architectures.
It enables individuals, startups, enterprises, and governments to build and manage scalable applications quickly and cost-effectively, without the need to maintain physical infrastructure.
With AWS, you can build applications without physical servers and scale them globally while paying only for what you use.

---

### 2. Core Components and Their Flow

All components in AWS are designed to interact seamlessly:

The user's request is routed via Route 53 to a Load Balancer (ELB).
The ELB distributes traffic to one or more EC2 instances inside a VPC.
These EC2s use EBS volumes for persistent storage.
If needed, they connect to a managed database via RDS.
Logs or static content are stored in S3, which can be delivered globally using CloudFront.
Security Groups and VPC rules ensure secure traffic flow between all these services.

Here’s how the main components work together in a typical deployment:

#### EC2 – Your virtual machine where the application runs. Part of IaaS.

#### EBS – A block storage disk attached to EC2, storing OS and data.

#### S3 – Used for storing static files (images, logs, backups). Can be served via CloudFront.

#### RDS – A managed database service. Connects to EC2 if your app needs structured data.

#### VPC – Your private network that hosts EC2, RDS, etc. Isolated and secure.

#### Security Group – A firewall that controls access to EC2/RDS (e.g. SSH on port 22).

#### Route 53 – Resolves domain names (e.g. example.com) to IPs of your resources.

#### ELB – Balances traffic across multiple EC2 instances.

#### CloudFront – A CDN to deliver content (from S3) quickly around the world.

All these components interact within the VPC, with EC2 as the central compute node.

---

Summary of Main Components

EC2 → Virtual server

EBS → Disk attached to EC2

S3 → Object storage for files

RDS → Managed database

VPC → Private cloud network

Route 53 → DNS service

ELB → Load balancer

CloudFront → Global content delivery

---

Each component connects as follows:

Route 53 resolves domain → points to ELB

ELB forwards traffic → to one or more EC2 instances

EC2 stores data on EBS, interacts with RDS if needed

Logs/media are sent to S3

CloudFront caches content from S3 or EC2

Security Groups and VPC manage all traffic

<img width="716" height="431" alt="image" src="https://github.com/user-attachments/assets/1b692068-e36a-4cd9-98a1-f7fbf574a0c3" />

---

### 3. How to Create a Virtual Machine (EC2) on AWS

Go to EC2 → Launch Instance

Select an AMI (e.g. Red Hat Linux)

Choose Instance Type (e.g. t2.micro)

Create a Key Pair (SSH) and download the .pem file

Choose a Subnet (part of your VPC)

Enable Public IP to connect via internet

Set a Security Group (open port 22)

Click Launch

---

Then connect via terminal (connect to EC2 via SSH):

<pre><code> ssh -i key.pem ec2-user@<Public-IP> </code></pre>


Inspect attached volumes (show all attached disks and partitions):

<pre><code> lsblk </code></pre>


Format and mount a new disk:

Create a new partitioning tool for the new volume
<pre><code> sudo fdisk /dev/xvdf </code></pre>

Format the partition as ext4
<pre><code> sudo mkfs.ext4 /dev/xvdf1 </code></pre>

Create a mount point
<pre><code> sudo mkdir /mnt/data </code></pre>

Mount the partition to the mount point
<pre><code> sudo mount /dev/xvdf1 /mnt/data </code></pre>

---

Each instance gets:

Private IP: static, used inside VPC

Public IP: dynamic, used to connect from outside

---

### 4. Why Study AWS and Comparison with INFN-CNAF

We study **AWS** because it represents a global standard in cloud computing and allows us to:

- Design and simulate a **modern data center** in an accessible and flexible way.
- Understand **cloud-native principles** such as IaaS/PaaS, scalability, availability, and security.
- Work with **modular and managed services** on distributed infrastructure.

AWS is also useful for comparing **different computing models**, such as **commercial cloud vs scientific infrastructures**.

### Comparison Table: AWS vs INFN-CNAF

| Feature              | **AWS (Public Cloud)**                        | **INFN-CNAF (Scientific HPC/HTC)**                   |
|----------------------|-----------------------------------------------|------------------------------------------------------|
| **Access**           | Self-service via Web/API                      | Controlled access (e.g., INFN login, VOMS)           |
| **Cost Model**       | Pay-as-you-go                                 | Free for research institutions                       |
| **Services Offered** | VMs, storage, AI, serverless, CDN             | Batch system, tape archive, scientific data storage  |
| **Flexibility**      | Very high, full customization                 | Lower, tailored to large scientific projects         |
| **Target Users**     | Enterprises, devs, startups, education        | LHC, physics experiments, long-term computation      |
| **Example Use Cases**| Web apps, containers, ML pipelines            | ATLAS jobs, backups, grid computing                  |

> This comparison highlights when to use a flexible commercial cloud like AWS versus a structured research-focused infrastructure like INFN-CNAF.

