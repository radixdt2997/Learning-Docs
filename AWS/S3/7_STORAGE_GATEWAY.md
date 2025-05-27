# 🌉 AWS Storage Gateway

**AWS Storage Gateway** is a hybrid cloud storage service that connects your **on-premises infrastructure** to **AWS cloud storage**, enabling seamless data transfer, backup, and tiering.

---

## ☁️ What is Hybrid Cloud?

**Hybrid Cloud** means part of your IT infrastructure runs **on-premises** and part in the **cloud**.

### Why Hybrid Cloud?

Organizations may use a hybrid approach due to:

- 🔄 **Ongoing cloud migration**
- 🔐 **Security policies**
- 📋 **Compliance requirements**
- 🧩 **IT strategy decisions**

Since **Amazon S3** is a **proprietary object storage** (unlike common file systems like NFS), AWS created **Storage Gateway** to make S3 usable by on-premises systems.

---

## 🧭 AWS Native Storage Services (Cloud-only)

| Type       | Services                       |
| ---------- | ------------------------------ |
| **Block**  | Amazon EBS, EC2 Instance Store |
| **File**   | Amazon EFS                     |
| **Object** | Amazon S3, Amazon Glacier      |

These services are primarily designed for use **within the AWS cloud**.

---

## 🔗 What is AWS Storage Gateway?

AWS Storage Gateway acts as a **bridge between your local (on-prem) systems and AWS cloud storage**.

### Key Features

- Hybrid storage access to AWS S3
- Allows your on-prem applications to use cloud storage **without rewriting code**
- Integrates with **S3**, **Glacier**, and **EBS Snapshots**
- **Encrypted**, **durable**, and **scalable**

### Common Use Cases

- ✅ Backup and restore
- ✅ Disaster recovery
- ✅ On-prem to cloud file sharing
- ✅ Storage tiering (move cold data to the cloud)

---

## 📦 Types of Storage Gateway

| Type               | Description                                                                 |
| ------------------ | --------------------------------------------------------------------------- |
| **File Gateway**   | Provides access to S3 using standard file protocols like **NFS** or **SMB** |
| **Volume Gateway** | Exposes block storage volumes backed by **EBS snapshots and S3**            |
| **Tape Gateway**   | Virtual tape library compatible with existing backup software               |

---

## 📌 Summary

- AWS Storage Gateway helps **extend your on-premises storage** to the cloud.
- It enables you to use **S3 and Glacier** for file, volume, and tape storage needs.
- Designed for **hybrid cloud scenarios** where direct integration with S3 is required.

---
