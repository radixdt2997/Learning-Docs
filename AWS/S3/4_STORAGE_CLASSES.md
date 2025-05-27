# 🗂️ Amazon S3 Storage Classes

Amazon S3 offers multiple **storage classes** to help you optimize **cost**, **performance**, and **availability** depending on how often and quickly you need to access your data.

---

## 🧠 What is a Storage Class?

A **storage class** in S3 defines the **cost**, **durability**, **availability**, and **retrieval time** for stored objects.

You choose the right storage class based on:

- How **frequently** you need the data
- How **fast** you need to access it
- How long you'll **store** it
- Your **budget**

---

## 📦 List of S3 Storage Classes

Here’s a simple breakdown of all S3 storage classes and when to use them:

---

### 1. **S3 Standard**

- 🟢 **General-purpose** storage
- Ideal for **frequently accessed** data
- High availability and low latency
- Default class if you don’t choose one

✅ **Use for**: websites, mobile apps, user content, general workloads

---

### 2. **S3 Intelligent-Tiering**

- 🧠 Automatically moves data between frequent and infrequent tiers based on usage
- No impact on performance
- Small monitoring fee per object

✅ **Use for**: data with **unknown or changing access patterns**

---

### 3. **S3 Standard-IA** (Infrequent Access)

- 💰 Lower cost than Standard
- Same high durability and performance
- Charged for **retrievals** and **minimum 30-day storage**

✅ **Use for**: backups, disaster recovery, and infrequently accessed files

---

### 4. **S3 One Zone-IA**

- 📍 Stores data in a **single availability zone** (not multiple like others)
- Lower cost than Standard-IA
- Not recommended for critical data

✅ **Use for**: secondary backups, easily re-creatable data

---

### 5. **S3 Glacier Instant Retrieval**

- 🧊 For data accessed **rarely**, but **needs millisecond access**
- Cheaper than Standard-IA
- Charged per retrieval

✅ **Use for**: image hosting, archives with fast access needs

---

### 6. **S3 Glacier Flexible Retrieval**

(formerly Glacier)

- 🐢 Low-cost archival storage
- Retrieval time: **minutes to hours**
- Use lifecycle policies to move data here

✅ **Use for**: long-term archives, compliance storage

---

### 7. **S3 Glacier Deep Archive**

- 💸 **Lowest-cost** storage class
- Retrieval time: **12–48 hours**
- Minimum storage duration: **180 days**

✅ **Use for**: legal archives, historical data, long-term backups

---

## 🛠️ Summary Table

| Storage Class              | Access Frequency  | Retrieval Time   | Min Storage Duration  | Use Case                       |
| -------------------------- | ----------------- | ---------------- | --------------------- | ------------------------------ |
| S3 Standard                | Frequent          | Milliseconds     | None                  | General-purpose                |
| S3 Intelligent-Tiering     | Unknown/Changing  | Milliseconds     | 30 or 90 days (tiers) | Dynamic access patterns        |
| S3 Standard-IA             | Infrequent        | Milliseconds     | 30 days               | Backups, DR                    |
| S3 One Zone-IA             | Infrequent (1 AZ) | Milliseconds     | 30 days               | Non-critical, recreatable data |
| Glacier Instant Retrieval  | Rare              | Milliseconds     | 90 days               | Archives with fast access      |
| Glacier Flexible Retrieval | Rare              | Minutes to Hours | 90 days               | Long-term archive, compliance  |
| Glacier Deep Archive       | Very Rare         | 12–48 Hours      | 180 days              | Historical/legal archives      |

---

## 🧩 How to Use Storage Classes

- You can set storage class when uploading a file.
- You can use **S3 Lifecycle Rules** to move data to cheaper classes over time.
- Some tools like AWS CLI, SDKs, or the S3 console support changing storage class.

---

## 💡 Best Practices

- Use **S3 Standard** for active files.
- Use **Intelligent-Tiering** if access patterns are unclear.
- Move old data to **Glacier** or **Deep Archive** to save cost.
- Use **Lifecycle policies** to automate transitions.

---
