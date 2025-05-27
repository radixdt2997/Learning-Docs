# Scalability & High Availability

## Scalability

- Scalability means that an application / system can handle greater loads by adapting
- There are two kinds of scalability:
  - **Vertical Scalability**
  - **Horizontal Scalability**
- Scalability is linked but different to high availability

### Vertical Scalability

- Means increasing the size of the instance
- Example: `t2.micro` -> `t2.large`
- Vertical Scalability is common for non-distributed systems like database
- There's usually a limit to how much we can scale vertically (Hardware Limit)

### Horizontal Scalability

- Means increasing the number of instances
- Horizontal scaling implies distributed systems
- This is very common for web applications / modern applications
- Its easy to horizontally scale due to cloud offerings such as Amazon EC2

## High Availability

- High Availability goes hand in hand with Horizontal Scaling
- High Availability means running your applicaions / systems in at least two AZ
- The goal of high availability is to survive a data center loss

### High Availability and Scaling for EC2

- **Vertical Scaling**: Increase instance size
- **Horizontal Scaling**: Increase number of instances
  - Auto Scaling Group
  - Load Balancer
- **High Availability**: Run instances for the same application across multi AZ
  - Auto Scaling Group multi AZ
  - Load Balancer multi AZ

## Scalability VS Elasticity VS (Agility)

- **Scalability**: Ability to accomodate a large load by making the hardware stronger (scale up) or by adding nodes (scale down)
- **Elasticity**: Once a system is scalable, elasticity means there will be some auto-scaling so that the system can scale based on the load. This is cloud friendly: pay per use, match demand, optimize costs
- **Agility**: _(not related to scalability: distractor)_: reduce time to make resources available to developers
