# Auto Scaling Group (ASG)

## What is an Auto Scaling Group?

- In real life, the load on your website or application can increase or decrease based on traffic.
- In the cloud, you can quickly create or remove servers (EC2 instances) as needed.
- **Auto Scaling Group (ASG)** helps manage this automatically.

## Main Goals of ASG

- **Scale Out**: Add EC2 instances when demand increases.
- **Scale In**: Remove EC2 instances when demand decreases.
- Ensure a **minimum**, **maximum**, and **desired** number of EC2 instances are running.
- Maintain **high availability** and **performance** by adjusting capacity automatically.
- **Cost optimization**: Only use the resources you need, when you need them.

## Key Features of ASG

- **Automatic Scaling**:
  - Based on metrics like CPU usage, memory usage (with custom metrics), or network traffic.
  - You define scaling policies (e.g., "Add 1 instance if CPU > 70% for 5 minutes").
- **Health Checks**:
  - Automatically replaces unhealthy EC2 instances.
  - Can use EC2 status checks or ELB health checks.
- **Load Balancer Integration**:
  - New instances are automatically registered with a Load Balancer (like ELB).
- **Launch Templates / Configurations**:
  - ASG uses a launch template (or older launch configuration) to know how to create instances.
- **Lifecycle Hooks**:
  - You can perform custom actions when instances are launching or terminating (e.g., run scripts).

## Common Use Cases

- Applications with variable or unpredictable traffic.
- Cost-saving by reducing unused instances during low traffic periods.
- Automatically maintaining a fixed number of healthy EC2 instances.

## Terms to Know (for the exam)

| Term                  | Description                                                 |
| --------------------- | ----------------------------------------------------------- |
| **Min Size**          | Minimum number of EC2 instances to run                      |
| **Max Size**          | Maximum number of EC2 instances allowed                     |
| **Desired Capacity**  | Target number of instances ASG tries to maintain            |
| **Scaling Policy**    | Rule that defines when and how to scale in/out              |
| **Launch Template**   | Blueprint used to launch EC2 instances (AMI, instance type) |
| **Health Check Type** | Determines how instance health is checked (EC2 or ELB)      |

## Additional Notes (Good to Know for Exam)

- ASGs work only with EC2 instances.
- ASG is a **regional** service, but the instances are launched in **specific Availability Zones**.
- You can attach **notifications** (e.g., via SNS) to get alerts when scaling happens.
- Combining ASG with **Elastic Load Balancer (ELB)** improves fault tolerance and load distribution.

## Scaling Stratergies

- **Manual Scaling**
  - Update the size of ASG manually
- **Dynamic Scaling**
  - Simple / Step Scaling
    - When cloudwatch alarm is triggered (CPU > 70%), then add two units
    - When cloudwatch alarm is triggered (CPU < 30%), then remove one unit
  - Target Tracking Scaling
    - Ex: I want the average ASG CPU to stay around 40% always
  - Scheduled Scaling
    - Anticipate scaling based on known usage patterns
    - Ex: Increase the min capacity to 10 at 5PM on friday
- **Predictive Scaling**
  - Use machine learning to predict future traffic ahead of time
  - Automatically provision the right number of EC2 instance in advance
  - Useful when your load has predictable time-based pattern
