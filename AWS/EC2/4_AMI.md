# AMI (Amazon Machine Image)

## Overview

- AMI are a customization of an EC2 instance
  - You add your own software, configuration, operating system, monitoring...
  - Faster boot/configuration time because all your software is pre-packaged
- AMI are built on specific region (and can be copied across regions)
- You can launch EC2 instance from:
  - A public AMI: AWS Provided
  - Your own AMI: You make and maintain it
  - An AWS Marketplace AMI: An AMI someone else made (and potentially sells)

## AMI Process (from EC2 instance)

- Start an EC2 instance and customise it
- Stop the instance (for data integrity)
- Build an AMI (this will also create EBS Snapshots)
- Launch instances from other AMIs
