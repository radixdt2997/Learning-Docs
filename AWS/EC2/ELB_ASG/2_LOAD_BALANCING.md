# Load Balancing

## What is Load Balancing ?

> Load Balancers are servers that forward the internet traffic to multiple servers (EC2 instances) downstream

## Why use a Load Balancer ?

- Spread Load across multiple downstream instances
- Expose a single point of access (DNS) to your application
- Seamlessly handle the faliures of downstream instances
- Do regular health checks to your instances
- Provide SSL termination (HTTPS) for your websites
- High availability accross zones

## Why use Elastic Load Balancer

- An ELB is a managed Load Balancer
  - AWS guarantees that it will be working
  - AWS takes care of upgrades, maintainence, high availability
  - AWS provides only a few configuration knobs
- It costs less to setup your own Load Balancer but it would be a lot more effort on your end (maintainence and integrations)
- 4 Kinds of Load Balancer offered by AWS:
  - Application Load Balancer (HTTP / HTTPS only) - Layer 7
  - Network Load Balancer (Ultra High Performance, allows for TCP) - Layer 4
  - Gateway Load Balancer - Layer 3
