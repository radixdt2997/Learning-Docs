# AWS EC2

- ## EC2 = Elastic Compute Cloud

- ## Helps with AWS's `Infrastructure As A Service`

- ## EC2 Capabilites

  - **Renting virtual machines (EC2)** -> Elastic Compute Cloud
  - **Storing data on virtual drives (EBS)** -> Elastic BeanStalk
  - **Distributing load across machines (ELB)** -> Elastic LoadBalancer
  - **Scaling the services using an auto-scaling group (ASG)** -> Auto-Scaling Group

- ## EC2 Configuraion

  - **Operating System (OS)**: Linux, Windows, MAC...
  - **How much compute power & cores**: CPU
  - **How much RAM**
  - **How much storage space**:
    - Network attached (EBS & EFS)
    - Hardware (EC2 Instance Store)
  - **Network card**: Speed of the card, public IP adderss
  - **Firewall rules**: Security Groups
  - **Bootstrap script**: Runs on first launch
    - Installing updates
    - Installing software
    - Download common files from internet
    - Runs with only **root user**, so all the command will start from **pseudo**

- ## EC2 Instance Types

  - **General Purpose**: `m` : Balance between `Compute`, `Memory` and `Networking`
    - Great for diversity of workloads such as web servers or code repositories
  - **Compute Optimized**: `c` : Good for compute-intensive tasks that require high performance
    - Batch Processing Workloads
    - Media Transcoding
    - High Performance Web Servers
    - High Performance Computing (HPC)
    - Scientific Modelling and Machine Learning
    - Dedicated Gaming Servers
  - **Memory Optimized**: `r` : Fast performance for workloads that process large data sets in memory
    - High Performance Relational/Non-Relational Databases
    - Distributed web scale cache stores
    - In-memory databases optimized for BI (Business Intelligence)
    - Application performing real time processing of big unstructired data
  - **Storage Optimized**: `i|d|h` : Good for storage intensive tasks that require high, sequential read and write access to large data sets on local storage
    - High frequency online transaction processing (OLTP) systems
    - Relational & NoSQL databases
    - Cache for in-memory databases (eg. Redis)
    - Data warehousing application
    - Distributed File System
  - **Accelerated Computing**
  - **HPC Optimized**

- ## Instance Naming Convention

  - ### Example `m5.2xlarge`

    - **m**: Instance class
    - **5**: Generation (AWS Improves)
    - **2xlarge**: Size
