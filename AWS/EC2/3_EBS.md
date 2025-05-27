# EC2 Instance Storage Options

## What is EBS (Elastic Block Store)?

- **EBS** is a type of storage that works like a network hard drive for your EC2 instances.
- It lets your EC2 instances **keep data even after they stop or terminate**.
- You can **detach** an EBS volume from one instance and **attach** it to another, but only **one instance at a time**.
- EBS volumes are **specific to one Availability Zone (AZ)** — you can't directly attach them across AZs.
- Think of EBS as a **network-attached USB drive**.

---

## EBS Volume Details

- **Network Drive**: Communicates with your EC2 instance over the network, which can introduce a small delay (latency).
- **AZ Locked**:
  - You can't attach a volume in `us-east-1a` to an instance in `us-east-1b`.
  - To move a volume to a different AZ or region, create a **snapshot**, then restore it in the new AZ.
- **Provisioned Capacity**:
  - You define the size (in GB) and performance (IOPS).
  - You're billed for the full size you provision — whether you use it or not.
  - You can **increase** the size or IOPS of a volume later, but not decrease.
- **Quick Attach/Detach**: Volumes can be moved between instances within the same AZ without much downtime.

---

## Volume Lifecycle: Delete on Termination

- This setting controls whether the EBS volume is deleted when the EC2 instance is terminated.
- **Root volume** (the main drive) is usually **deleted by default**.
- **Additional volumes** are **kept by default**.
- You can change this setting via:
  - **AWS Console**
  - **AWS CLI**
- **Use case**: Keep important data (e.g., logs or databases) even after terminating the instance by disabling auto-delete.

---

## Snapshots (Optional but Important)

- Snapshots are **backups** of EBS volumes stored in **Amazon S3**.
- You can use snapshots to:
  - **Create a new volume**
  - **Move volumes across Availability Zones or Regions**
- Snapshots are **incremental**, so only changes are saved after the first full snapshot.
- Snapshots are a great way to **back up and restore data**.

---

## Volume Types (Overview)

EBS offers multiple types of volumes based on performance and use case:

- **gp3**: General-purpose SSD — good balance of price and performance.
- **io2/io1**: Provisioned IOPS SSD — high-performance for databases.
- **st1**: Throughput-optimized HDD — good for big data or log processing.
- **sc1**: Cold HDD — lowest cost, infrequent access.
- **standard (Magnetic)**: Older, rarely used.

---

## EBS Encryption (Security)

- EBS volumes can be **encrypted** to protect your data.
- Encryption can be enabled during volume creation (not after).
- Benefits of EBS encryption:
  - Data at rest is encrypted
  - Data in transit between instance and volume is encrypted
  - Snapshots and copies of encrypted volumes are also encrypted

---

## Summary

- EBS provides flexible, persistent storage for EC2.
- Volumes are easy to manage, but must stay in the same Availability Zone.
- You can use snapshots, encryption, and different volume types to match your performance or security needs.
