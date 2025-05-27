# AWS IAM

- ## Global service

- ## IAM Users & Groups

  - Users are people within our organization that can be grouped
  - Groups can only contain users and not other groups
  - Users don't have to belong to a group, and it can also belong to multiple groups

- ## IAM Permissions

  - Users and groups are assigned policies _(JSON)_ for access and permission control
  - Always apply principle of _least priviledge principle_ : Don't give more permission than a user needs

- ## IAM Policies

  - User can be assigned IAM polices in two ways:
    - **Inline Policy** : Defined directly within a user, group or role
    - **Managed Policy** : Pre defined polices created by AWS or customers, and can be attached to users, groups or roles

- ## IAM Policy Structure

  - **Consists of** :
    - Version (required): Policy language version
    - Id (optional): Identifier for the policy
    - Statement (required): One or more individual statements
  - **Statement Consists of**:
    - Sid (optional): Identifier for the statement
    - Effect: Whether the statement allows or denies the access (Allow, Deny)
    - Principal: Account/User/Role to which this policy will be applied to
    - Action: List of action this policy allows or denies
    - Resources: List of resources to which the action is applies to
  - **Example** :

    ```json
        "Version": "2012-10-17",
        "Id": "S3-Account-Permissions",
        "Statement": [
            {
                "Sid": "1",
                "Effect": "Allow",
                "Principal": {
                    "AWS": ["arn:aws:iam::123456789012:root"]
                },
                "Action": [
                    "s3:GetObject"
                    "s3:PutObject"
                ],
                "Resource": ["arn:aws:s3::mybucket/*"]
            }
        ]
    ```

- ## IAM Password Policy

  - ### Simple Credentals

    - Strong password ensures secure account
    - Password Policy:
      1. Minimum Password Length
      2. Include Uppercase, Lowercase, Numbers, Non-alphanumeric characters
    - Allow IAM Users to change their own passwords
    - Implement Password expiration after a certain period of time
    - Prevent password reuse

  - ### MFA (Multi Factor Authentication)

    - MFA is combination of password that we know and a security device that we own
    - Benefit of MFA: If account is stolen or hacked, the account won't be compromised
    - MFA Device options :
      1. Authenticator App:
         - Google Authenticator: (Phone)
         - Authy: (Phone)
      2. Security Key: (Physical Device)
      3. Hardware TOTP (Time-based One-Time Password) Token

- ## AWS Access Keys, CLI and SDK

  - ### Ways to access AWS

    - **AWS Management Console**: Protected by Password and MFA
    - **AWS Command Line Interface (CLI)**: Protected by Access Keys
    - **AWS Software Development Kit (SDK)**: (For Code) Protected by Access Keys

  - ### Access keys are generated through AWS console

    - Access Key ID === username
    - Secret Access Key === password

- ## AWS CloudShell

  - CloudShell is terminal in the clould of AWS
  - Works without credential
  - Assign users to group
  - We can upload or download a file form AWS CloudShell

- ## IAM Roles for services

  - Some AWS Services will need to perform actions on your behalf
  - To do so, we will assign permission to Services with `IAM Role`
  - Common Roles:
    - EC2 Instance Roles
    - Lambda Function Roles
    - Roles for Cloud Formation

- ## IAM Security Tools

  - **IAM Credentials Report**: _(account-level)_
    - A Report that lists all your account users and the status of their various credentials
  - **IAM Access Advisor**: _(user-level)_
    - Access advisor shows the services permissions granted to a user and when those services were last accessed.
    - You can use this information to revise the policies

- ## IAM Guidelines & Best Practices

  - Don't use root account except for AWS account setup
  - One physical User = One AWS User
  - Assign users to groups and assign permission to groups
  - Create strong password policy
  - Use and enforce the MFA
  - Create and use Roles for giving permission to AWS Services
  - Use access keys for programmatic access (CLI/SDK)
  - Audit permission of your account using `IAM Credentials Report` and `IAM Trusted Advisors`
  - Never share IAM Users & Access Key

- ## Shared Reponsibity Model

  - ### AWS

    - Infrastructure (global network security)
    - Configuration and vulneralbitiy analysis
    - Compliance validation

  - ### You

    - Users, Groups, Roles, Policies management and montoring
    - Enable MFA on all accounts
    - Rotate all the keys often
    - Use IAM tools to apply appropriate permissions
    - Analyze access patterns and review permissions

- ## IAM - Summary

  - **Users**: Mapped to a physical user, has a password for AWS Console
  - **Groups**: Contains users only
  - **Policies**: JSON Document that outlines permissions for users or groups
  - **Roles**: For EC2 Instances or AWS Services
  - **Security**: MFA + Password Poilcy
  - **AWS CLI**: Manage AWS Services using Command-Line
  - **AWS SDK**: Manage AWS Services using Programming Language
  - **Access Keys**: Access AWS using CLI or SDK
  - **Audit**: IAM Credentials Report & AWS Access Advisor
