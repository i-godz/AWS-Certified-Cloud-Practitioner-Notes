# Security and Compliance Index 
- [Identity Access & Management (IAM)](#1--identity-access--management-iam)
    - [AWS Account Overview](#11--aws-account-overview)
    - [What is IAM?](#12--what-is-iam)
	- [IAM Users & Groups](#13--iam-users--groups)
	- [IAM Permissions](#14--iam-permissions)
	- [IAM Policies Inheritance & Structure](#15--iam-policies-inheritance--structure)
# 1- Identity Access & Management (IAM)

### 1.1- AWS Account Overview 
![](https://i.imgur.com/9fPwt5W.png)
### 1.2- What is IAM?
- A <mark style="background: #D2B3FFA6;">global</mark> web service for securely controlling access to AWS resources.
- Allows you to manage users, groups, roles and policies.
- Can be managed in AWS management console, AWS CLI and AWS SDK's.
- Creates a root account by default and shouldn't be shared. 
### 1.3- IAM Users & Groups
- **Users**: Represent individual identities that interact with AWS services. Users have unique credentials (username, password, access keys).
- **Groups**: Logical grouping of users to simplify permission management. 
- Flexibility in User Management in IAM, users do not have to belong to a group (not a best practice), and a user can belong to multiple groups. This allows user to manage access permissions in a granular and efficient manner. For example, a user could belong to both the “Operations" group and the “Developers” group, inheriting permissions from both.
![](https://i.imgur.com/Njrat83.png)

### 1.4- IAM Permissions
- Permissions are defined using policies.
- Policies specify what actions are allowed or denied on specific resources.
- Policies can be attached to users, groups and roles.
### 1.5- IAM Policies Inheritance & Structure
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
    . "Sid": "1",
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
