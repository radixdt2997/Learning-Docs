# AWS S3: Versioning, and Replication

---

## 📄 Versioning in S3

Versioning allows you to preserve, retrieve, and restore every version of every object stored in your S3 bucket.

### Key Points

- **Enabled at the bucket level** — you must turn it on for each bucket.
- When you upload a file with the same name (key), S3 automatically stores it as a new version.
- Versions are tracked (e.g., v1, v2, v3...) and can be restored if needed.

### Why Use Versioning?

- ✅ Protects against accidental deletes or overwrites.
- 🔁 Allows you to roll back to a previous version of a file.

### Important Notes

- Files uploaded **before versioning was enabled** are given a **`null` version ID**.
- **Suspending** versioning stops new versions from being created but **does not delete** existing versions.

---

## 🔁 S3 Replication

Replication lets you automatically copy objects across S3 buckets, either in the same region or different regions/accounts.

### Requirements

- **Versioning must be enabled** on both the source and destination buckets.
- Replication is **asynchronous** – objects are not copied instantly.
- You must configure the correct **IAM permissions** to allow S3 to replicate files.

### Types of Replication

| Type                               | Description                                           |
| ---------------------------------- | ----------------------------------------------------- |
| **CRR** (Cross-Region Replication) | Copies objects to a bucket in a different AWS region. |
| **SRR** (Same-Region Replication)  | Copies objects to a bucket in the same AWS region.    |

### Common Use Cases

- **Cross-Region Replication (CRR)**:

  - Improve compliance and disaster recovery
  - Provide low-latency access in multiple regions
  - Replicate data across different AWS accounts

- **Same-Region Replication (SRR)**:
  - Aggregate logs into one location
  - Sync data between production and test environments

---

## ✅ Summary

- Enable **versioning** to protect data from loss or overwrite.
- Use **replication** to duplicate data for resilience, compliance, or testing.
- Ensure correct **IAM roles and permissions** are in place for replication to work.

---
