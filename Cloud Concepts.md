# Cloud Computing Index
- [What is Cloud Computing?](#what-is-cloud-computing)
    - [Why Cloud Computing?](#why-cloud-computing)
    - [Deployment Models of the Cloud](#deployment-models-of-the-cloud)
    - [Characteristics of the Cloud Computing](#characteristics-of-the-cloud-computing)
    - [Advantages of Cloud Computing](#advantages-of-cloud-computing)
    - [Cloud Service Models](#cloud-service-models)
    - [AWS Pricing Models](#aws-pricing-models)
- [AWS Global Infrastructure](#aws-global-infrastructure)
    - [AWS Regions](#aws-regions)
    - [How to choose an AWS region???](#how-to-choose-an-aws-region)
    - [AWS Availability Zones](#aws-availability-zones)
    - [AWS Edge Locations / Points of Presence](#aws-edge-locations--points-of-presence)
- [Shared Responsibility Model](#shared-responsibility-model)
    - [What is the Shared Responsibility Model?](#what-is-the-shared-responsibility-model)
    - [AWS Responsibilities: Security of the Cloud](#aws-responsibilities-security-of-the-cloud)
    - [Customer Responsibilities: Security in the Cloud](#customer-responsibilities-security-in-the-cloud)

# What is Cloud Computing?
 - The <mark style="background: #D2B3FFA6;">on-demand</mark> delivery of the compute power, database storage, applications, and other IT resources over the internet.
 - Through a cloud service platform with <mark style="background: #D2B3FFA6;">pay-as-you-go</mark> pricing.
 - You can <mark style="background: #D2B3FFA6;">provision exactly the right type</mark> and <mark style="background: #D2B3FFA6;">size of computing resources</mark> you need.
 - You can access as many resources as you need,<mark style="background: #D2B3FFA6;"> almost instantly</mark>.
 - Simply way to access <mark style="background: #D2B3FFA6;">servers, storage, database</mark> and a set of <mark style="background: #D2B3FFA6;">applications services</mark>.
## Why Cloud Computing?
- There are many problems with the traditional IT approach
    - Covering the costs of data center rental.
    - Covering expenses for power supply, cooling, and maintenance.
    - Time required for hardware additions and replacements.
    - Cannot scale as flexibly as you would like…
    - Employing a 24/7 team for infrastructure monitoring.
    - Addressing disaster preparedness concerns such as earthquakes, power shutdowns, and fires.
    - Overall, inflexible and inconvenient for our rapidly changing world.
## Deployment Models of the Cloud
| Private Cloud                                                            | Public Cloud                                                                                             | Hybrid Cloud                                                                 |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Cloud services used by a single organization, not exposed to the public. | Cloud resources owned and operated by a third-party cloud service provider, delivered over the Internet. | Keep some servers on-premises and extend some capabilities to the cloud.     |
| Complete control over data, security, and compliance.                    | Cost-effective as infrastructure is shared among multiple users.                                         | Allows data and applications to be shared between private and public clouds. |
| Security for sensitive applications, ideal for critical workloads.       | Suitable for less sensitive workloads that require high scalability and availability.                    | Offers flexibility, security, and scalability for different use cases.       |
| Meet specific business needs and compliance requirements.                | No maintenance required as the cloud provider manages the infrastructure.                                | Provides business continuity, disaster recovery, and data backup solutions.  |
## Characteristics of the Cloud Computing 
### Agility / On-demand self service.
- Users can provision resources and use them without human interaction from the service provider.
### High Availability / Broad network access.
- Resources are available over the network, and can be accessed by diverse client platforms.
### Fault Tolerance / Multi-tenancy and Resource Pooling
- Multiple customers can share the same infrastructure and applications with security and privacy.
- Multiple customers are serviced form the same physical resource.
### Rapid Elasticity and Scalability
- Automatically and quickly acquire and dispose resources when needed.
- Quickly and easily scale based on demand.
#### Scalability Types 
|                Vertical Scaling (scale up/down)                 |                           Horizontal Scaling (scale out/in)                            |
| :-------------------------------------------------------------: | :------------------------------------------------------------------------------------: |
| Involves increasing the capacity of a single server or machine. |      Involves adding more servers or machines to a system to distribute the load.      |
| Upgrades the system's resources, such as CPU, RAM, or storage.  | Expands capacity by increasing the number of nodes rather than upgrading a single one. |
### Measured Service 
- Usage of resources is measured, and users are charged accurately based on their consumption, ensuring cost efficiency.
## Advantages of Cloud Computing 
**Cost Savings**: Pay only for the computing power, storage, and other resources you use.
**Speed and Agility**: Quickly deploy services and resources.
**Scalability**: Easily scale resources up or down as needed.
**High Availability**: Highly available architecture for business continuity.
**Global Reach**: Access services from any geographical region.
**Security**: AWS provides robust security capabilities to protect your data.
## Cloud Service Models 
![](https://i.imgur.com/ubuwOIp.png)

| Infrastructure as a Service (IaaS)                                              | Platform as a Service (PaaS)                                                      | Software as a Service (SaaS)                                                     |
| ------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Offers virtualized computing resources over the internet.                       | Offer a platform for developing, deploying, and managing applications.            | Offers cloud-based product that is run and managed by the service provider.      |
| Offers maximum control over the infrastructure.                                 | Focus on deploying applications without managing underlying infrastructure.       | Accessible over the internet, usually via a web browser.                         |
| Suitable for developers needing control over OS, middleware, and runtime.       | Ideal for developers who want to focus on application development                 | Suitable for users needing access to software without infrastructure management. |
| Examples include Amazon EC2, Azure Virtual Machines, and Google Compute Engine. | Examples include AWS Elastic Beanstalk, Azure App Service, and Google App Engine. | Examples include Google Workspace, Microsoft Office 365, and Salesforce.         |
## AWS Pricing Models
AWS follows three fundamental pricing principles based on the pay-as-you-go pricing model:

| Fundamental       | Description                                                                                                                                                          |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Compute           | Pay for the compute time you consume. Examples include EC2 instance hours or Lambda invocation duration.                                                             |
| Storage           | Pay for the amount of data stored in the cloud. Examples include S3 storage space and EBS volume usage.                                                              |
| Data Transfer OUT | Pay for data transfer out of the cloud. Data transfer IN is free. This pricing structure solves the issue of expensive data transfer fees in traditional IT systems. |
# AWS Global Infrastructure
### AWS Regions
- All around the world.
- Clusters of data centers.
- Most AWS services are region-scoped. 
### How to choose an AWS region???
When deploying to AWS, there are multiple factors to consider:
- **Compliance:** Ensure the region meets data residency and compliance requirements.
- **Latency:** Choose a region closest to your customers for lower latency.
- **Services Available**: Check which AWS services are offered in each region.
- **Pricing**: Prices vary by region, so choose a region that fits your cost requirements.
### AWS Availability Zones
- Each region has many multiple availability zones (min is 3, max is 6).
- Each availability zones has independent redundant power, networking and connectivity.
- They are separate from each other so that they are isolated from disasters.
- They are connected with high bandwidth , ulta-low latency networking.
### AWS Edge Locations / Points of Presence
- Content is delivered to end users with lower latency as amazon has 400+ points of presence in 90+ cities across 40+ countries.
# Shared Responsibility Model
## What is the Shared Responsibility Model?
- AWS and the customer share responsibility for security and compliance.
- Divides security tasks based on AWS as the provider and customer as the user of cloud services.
  ![](https://i.imgur.com/ZQU9ZoZ.png)
### AWS Responsibilities: Security of the Cloud
- AWS is responsible for protecting the infrastructure that runs all services offered in the AWS Cloud.
- Includes hardware, software, networking, and facilities:
    - **Physical security** of data centers (e.g., access control, environmental controls).
    - **Infrastructure** security, such as maintaining hypervisors, host operating systems, and network infrastructure.
    - **Global network** operations, such as DDoS protection and monitoring.
#### Example Responsibilities for Different AWS Services

| Service Type     | AWS Responsibility                                         | Customer Responsibility                                                |
| ---------------- | ---------------------------------------------------------- | ---------------------------------------------------------------------- |
| IaaS (e.g., EC2) | Securing physical infrastructure, hypervisor, and network. | Configure and secure OS, patch management, data, and network settings. |
| PaaS (e.g., RDS) | Managing the database engine, backups, and patching.       | Secure data at rest and in transit, manage DB access, and IAM roles.   |
| SaaS (e.g., S3)  | Protecting the service's underlying infrastructure.        | Manage permissions, bucket policies, and data lifecycle rules.         |
### Customer Responsibilities: Security in the Cloud
- Customers are responsible for managing and securing what they put in the cloud.
- Includes:
    - **Data protection**: Encrypt data in transit and at rest.
    - **IAM**: Control access through Identity and Access Management (IAM) roles, users, and policies.
    - **OS and application configurations**: Maintain security of guest operating systems, applications, and firewall configurations.
    - **Network settings**: Manage security group rules and network access control lists (NACLs).
    - **Compliance**: Ensure compliance with regulations and standards based on data storage and usage.