# AWS Access Analyzer and Shared Responsibility Model

## Access Analyzer

- Ensures that only intented people have access to your S3 buckets.
- Example: Publicly accessible bucket, bucket shared with other AWS account
- Evaluates S3 bucket policies, S3 ACLs, S3 Access Point Policies
- Powered by IAM Analyzer

## Shared Responsibility Model

| USER                                   | AWS                                      |
| -------------------------------------- | ---------------------------------------- |
| S3 Versioning                          | Infrastructure                           |
| S3 Bucket Policies                     | Configuration and vulnerability analysis |
| S3 Replication Setup                   | Compliance validation                    |
| Logging and Monitoring                 |                                          |
| S3 Storage Class                       |                                          |
| Data encryption at rest and in transit |                                          |
