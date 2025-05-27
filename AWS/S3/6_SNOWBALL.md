# 📦 AWS Snowball

**AWS Snowball** is a secure, portable device used to **transfer large amounts of data** in and out of AWS, and to **process data at the edge** where connectivity is limited.

---

## 🚛 What is AWS Snowball?

- A **rugged, secure, physical device** for transferring up to **petabytes** of data.
- Designed for environments with:
  - **Limited bandwidth**
  - **High network costs**
  - **Unstable internet**
- Snowball helps you **migrate data faster** than over traditional network transfer.

> 📝 **Tip**: If transferring your data over the network takes **more than a week**, consider using Snowball.

---

## 🧱 Types of Snowball Edge Devices

| Device Type                         | Compute   | Memory | SSD Storage | Use Case                          |
| ----------------------------------- | --------- | ------ | ----------- | --------------------------------- |
| **Snowball Edge Storage Optimized** | 104 vCPUs | 416 GB | **210 TB**  | Bulk data transfer, local storage |
| **Snowball Edge Compute Optimized** | 104 vCPUs | 416 GB | **28 TB**   | Edge computing, local processing  |

Both devices support **running EC2 instances or Lambda functions** locally.

---

## 🧭 Why Use Snowball?

Snowball is ideal when you're dealing with:

1. **Limited Internet Connectivity**
2. **Low Bandwidth**
3. **High Network Transfer Costs**
4. **Shared Bandwidth Constraints**
5. **Unreliable Connections**

---

## 🌐 Edge Computing with Snowball

**Edge computing** allows you to process data locally before uploading it to AWS.

### Common Scenarios

- In the field: trucks, ships, remote mining stations
- Locations without reliable cloud access

### Features

- Deploy **Snowball Edge** devices at edge locations
- Run **EC2 instances** or **Lambda functions** locally
- Perform tasks like:
  - Preprocessing raw data
  - Running machine learning inference
  - Media transcoding

✅ **Benefits**: Reduces data size before transfer, improves response time, supports offline operations

---

## 💵 Snowball Edge Pricing

You pay for:

- **Device usage**
- **Data transfer out of AWS**

> 🚚 **Data transfer into S3 is free**

### On-Demand Pricing

- One-time **service fee per job**
- Includes **10 to 15 days** of usage (shipping time not counted)
- Pay **daily** for additional time

### Committed Pricing (Edge Computing)

- Pay upfront for:
  - Monthly
  - 1-Year
  - 3-Year usage terms
- Up to **62% discount** for long-term commitments

---

## ✅ Summary

- Use **Snowball** when you can’t rely on fast, stable internet.
- Choose the right **device type** based on your need: **storage** or **compute**.
- Supports **secure, scalable data transfer** and **local edge processing**.
- Ideal for **large-scale migrations** and **offline environments**.

---
