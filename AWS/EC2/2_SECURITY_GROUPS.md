# Introduction to Security Groups

- Security Groups are a core part of **network security** in AWS.
- They act as **virtual firewalls** for your EC2 instances, controlling how traffic is allowed **in and out**.
- Security Groups use **allow-only rules**—you can’t explicitly deny traffic.
- Rules can allow access based on **IP addresses**, **IP ranges**, or **other security groups**.

## How Security Groups Work

- Each Security Group is attached to an **EC2 instance**, and it filters:
  - **Inbound traffic** – network requests **coming to** your instance
  - **Outbound traffic** – network requests **leaving from** your instance
- Think of Security Groups as a first line of defense that defines what traffic is permitted before it even reaches your instance.
- All rules are **stateful**:
  - If you allow inbound traffic from an IP, the **response traffic is automatically allowed** back out, and vice versa.

## Key Characteristics

- You can assign the **same Security Group to multiple EC2 instances**.
- Security Groups are specific to a **region and VPC** (Virtual Private Cloud).
- They exist **outside of the EC2 instance**, meaning:
  - If a request is blocked, the instance will not receive it or be aware of it.
- By default:
  - **All inbound traffic is denied**
  - **All outbound traffic is allowed**

## Best Practices

- **Use separate Security Groups for different access levels.**
  - Example: Create a dedicated group that only allows **SSH (port 22)** for administrative access.
- **Restrict access to known IPs whenever possible**, especially for sensitive ports like SSH and RDP.
- If an application **times out**, it's likely a **Security Group issue** (blocked by rules).
- If an application returns **“connection refused”**, it likely means:
  - The app is not running, or
  - It is not listening on the expected port.

## Common Ports to Know

| Port | Protocol | Description                                           |
| ---- | -------- | ----------------------------------------------------- |
| 22   | SSH      | Secure Shell – Remote access to Linux instances       |
| 21   | FTP      | File Transfer Protocol – Upload/download files        |
| 22   | SFTP     | Secure FTP over SSH – Secure file transfers           |
| 80   | HTTP     | Unencrypted web traffic (websites)                    |
| 443  | HTTPS    | Secure web traffic (encrypted websites)               |
| 3389 | RDP      | Remote Desktop Protocol – Access to Windows instances |

## Additional Notes

- **You can’t set "deny" rules** in Security Groups—only allow what is explicitly needed.
- For **more granular control** (like blacklisting IPs), consider using **Network ACLs (Access Control Lists)** alongside Security Groups.
- Changes to Security Groups are applied **immediately**, making them powerful and flexible for real-time configuration.

---

> 🛡️ Security Groups are essential for protecting your cloud infrastructure. Understanding and configuring them properly is key to keeping your applications and data secure.
