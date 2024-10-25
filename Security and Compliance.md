# Security and Compliance Index 
- [Shared Responsibility Model](#1--shared-responsibility-model) 
	  - [What is the Shared Responsibility Model?](#11--what-is-the-shared-responsibility-model) 
	  - [AWS Responsibilities: Security of the Cloud](#12--aws-responsibilities-security-of-the-cloud) 
	  - [Customer Responsibilities: Security in the Cloud](#13--customer-responsibilities-security-in-the-cloud)
- [Identity Access & Management (IAM)](#2--identity-access--management-iam)
	  - [AWS Account Overview](#21--aws-account-overview)
	  - [What is IAM?](#22--what-is-iam)
	  - [IAM Users & Groups](#23--iam-users--groups)
	  - [IAM Permissions](#24--iam-permissions)
	  - [IAM Policies Inheritance & Structure](#25--iam-policies-inheritance--structure)
# 1- Shared Responsibility Model
### 1.1- What is the Shared Responsibility Model?
- AWS and the customer share responsibility for security and compliance.
- Divides security tasks based on AWS as the provider and customer as the user of cloud services.
  ![](https://i.imgur.com/ZQU9ZoZ.png)
### 1.2- AWS Responsibilities: Security of the Cloud
- AWS is responsible for protecting the infrastructure that runs all services offered in the AWS Cloud.
- Includes hardware, software, networking, and facilities:
    - **Physical security** of data centers (e.g., access control, environmental controls).
    - **Infrastructure** security, such as maintaining hypervisors, host operating systems, and network infrastructure.
    - **Global network** operations, such as DDoS protection and monitoring.
##### Example Responsibilities for Different AWS Services

| Service Type     | AWS Responsibility                                         | Customer Responsibility                                                |
| ---------------- | ---------------------------------------------------------- | ---------------------------------------------------------------------- |
| IaaS (e.g., EC2) | Securing physical infrastructure, hypervisor, and network. | Configure and secure OS, patch management, data, and network settings. |
| PaaS (e.g., RDS) | Managing the database engine, backups, and patching.       | Secure data at rest and in transit, manage DB access, and IAM roles.   |
| SaaS (e.g., S3)  | Protecting the service's underlying infrastructure.        | Manage permissions, bucket policies, and data lifecycle rules.         |
### 1.3- Customer Responsibilities: Security in the Cloud
- Customers are responsible for managing and securing what they put in the cloud.
- Includes:
    - **Data protection**: Encrypt data in transit and at rest.
    - **IAM**: Control access through Identity and Access Management (IAM) roles, users, and policies.
    - **OS and application configurations**: Maintain security of guest operating systems, applications, and firewall configurations.
    - **Network settings**: Manage security group rules and network access control lists (NACLs).
    - **Compliance**: Ensure compliance with regulations and standards based on data storage and usage.
# 2- Identity Access & Management (IAM)
### 2.1- AWS Account Overview 
![](https://i.imgur.com/9fPwt5W.png)
### 2.2- What is IAM?
- A <mark style="background: #D2B3FFA6;">global</mark> web service for securely controlling access to AWS resources.
- Allows you to manage users, groups, roles and policies.
- Can be managed in AWS management console, AWS CLI and AWS SDK's.
- Creates a root account by default and shouldn't be shared. 
### 2.3- IAM Users & Groups
- **Users**: Represent individual identities that interact with AWS services. Users have unique credentials (username, password, access keys).
- **Groups**: Logical grouping of users to simplify permission management. 
- Flexibility in User Management in IAM, users do not have to belong to a group (not a best practice), and a user can belong to multiple groups. This allows user to manage access permissions in a granular and efficient manner. For example, a user could belong to both the “Operations" group and the “Developers” group, inheriting permissions from both.
![](https://i.imgur.com/Njrat83.png)

### 2.4- IAM Permissions
- Permissions are defined using policies.
- Policies specify what actions are allowed or denied on specific resources.
- Policies can be attached to users, groups and roles.
### 2.5- IAM Policies Inheritance & Structure
- Policies are JSON documents that define permissions.
- Key elements of a policy:
    1. **Version**: Policy language version (e.g., `2012-10-17`).
    2. **ID**: Identifier for the policy (optional).
    3. **Statement**: Contains one or more permissions (allow or deny).
- Key elements of a statement:
    1. **Sid**: Identifier for the statement (optional).
    2. **Action**: Specifies which AWS service actions are allowed or denied.
    3. **Resource**: Specifies the AWS resources to which the actions apply.
    4. **Effect**: Either `Allow` or `Deny`.
    5. **Principle**: The account, user, or role to which the policy will be applied to.
    6. **Condition**: Conditions for when this policy is in effect (optional).
#### Example IAM Policy Structure 

```json
{
  "Version": "2012-10-17",
  "Id": "S3-Account-Permissions",
  "Statement": [
    {
   	"Sid": "1",
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Principal": { "AWS": ["arn:aws:iam::123456789012:root"] },
      "Resource": "arn:aws:s3:::example-bucket"
    }
  ]
}
```
#### IAM Policy Inheritance 
![](https://i.imgur.com/MSfQFxn.png)
