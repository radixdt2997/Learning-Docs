# 🌩️ Amazon S3 (Simple Storage Service)

Amazon S3 is one of the core services of AWS. It's designed for **infinite scalability**, allowing users to store and retrieve any amount of data, at any time, from anywhere on the web.

---

## 📝 Description

- Core building block of AWS cloud services.
- Marketed as "**Infinite Scaling Storage**".
- Ideal for storing any kind of data (structured or unstructured).

---

## 🚀 Common Use Cases

1. Backup and long-term storage
2. Disaster recovery solutions
3. Archiving old or infrequently accessed data
4. Hybrid cloud storage (on-prem + cloud)
5. Hosting application assets (e.g., images, scripts)
6. Media content hosting (videos, audio)
7. Data lakes and big data analytics
8. Software distribution (e.g., install packages, binaries)
9. Hosting static websites

---

## 🪣 Buckets in S3

Buckets are containers used to store objects (files) in S3.

### Bucket Characteristics

- Must have a **globally unique name** (across all AWS accounts and regions).
- Buckets are created in a **specific region**.
- While S3 appears global, data is stored **regionally**.

### Bucket Naming Rules

- Lowercase letters, numbers, and hyphens only.
- Length: 3 to 63 characters.
- Cannot resemble an IP address (e.g., `192.168.1.1`).
- Cannot start with prefix `xn--`.
- Cannot end with suffix `-s3alias`.

🚫 Examples of invalid names:

- `My_Bucket` ❌ (uppercase + underscore)
- `xn--example` ❌ (reserved prefix)

✅ Valid Example:

- `my-awesome-bucket-123`

---

## 📦 Objects in S3

An object is the fundamental entity stored in S3. It consists of:

- **Key**: The unique identifier (full path) within a bucket.
- **Value**: The content/data of the object (up to 5TB).
- **Metadata**: Additional information stored with the object.
- **Tags**: Optional key/value pairs for management, security, or lifecycle rules.
- **Version ID**: Unique identifier if versioning is enabled.

### Object Key Examples

```text
s3://my-bucket/my_file.txt
s3://my-bucket/folder1/folder2/my_file.txt
```

### Object Size Limits

- Max size: 5TB (via multi-part upload).
- For uploads > 5GB, use multi-part upload to ensure reliability and performance.

## 🧠 Tips

- Use tags (up to 10 per object) for better management (e.g., cost tracking, access control).
- Use versioning to protect data from overwrites or accidental deletions.
