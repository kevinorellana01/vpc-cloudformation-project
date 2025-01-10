# vpc-cloudformation-project

# AWS VPC Creation with CloudFormation

This repository contains an Infrastructure as Code (IaC) project to create a complete Virtual Private Cloud (VPC) on AWS using AWS CloudFormation. The project includes defining and provisioning VPC components like subnets, routing, an Internet Gateway, a bastion server, and EC2 instances. 

## Project Overview

This project demonstrates how to use AWS CloudFormation to create and manage a fully functional VPC environment. The architecture was designed and implemented as part of a hands-on learning experience in the Cloud Engineering Academy.

Key features of the VPC created in this project:
- **Public and Private Subnets** across multiple Availability Zones for high availability and fault tolerance.
- **Internet Gateway (IGW)** for enabling internet access to public subnets.
- **Routing Tables** for managing network traffic within the VPC.
- **Bastion Server** for secure access to resources in private subnets.
- **EC2 Instances** with appropriate security groups to host applications.

## Features and Highlights

- **Infrastructure as Code (IaC):** Leverages CloudFormation templates written in YAML to automate the deployment and management of AWS resources.
- **Scalability:** Ensures the architecture can scale seamlessly as application demands increase.
- **Modular Design:** Simplifies updates and modifications by organizing resources logically.
- **Debugging & Error Handling:** Provides solutions to common issues encountered during CloudFormation deployments.

## Prerequisites

Before using this project, ensure the following are installed and configured:

- **AWS CLI:** [Installation Guide](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- **Text Editor:** e.g., Visual Studio Code
- **GitHub Repository:** Clone this repository to your local machine.

## How to Use

### Step 1: Clone the Repository
Clone this repository to your local environment:
```bash
git clone https://github.com/your-username/vpc-cloudformation.git
cd vpc-cloudformation
```

### Step 2: Deploy the VPC
Run the following AWS CLI command to deploy the stack:
```bash
aws cloudformation create-stack --stack-name MyVPCStack --template-body file://vpc.yaml
```
Monitor the stack creation status:
```bash
aws cloudformation describe-stacks --stack-name MyVPCStack
```

### Step 3: Update the Stack
To make updates (e.g., add subnets or instances), modify the `vpc.yaml` file and run:
```bash
aws cloudformation update-stack --stack-name MyVPCStack --template-body file://vpc.yaml
```

### Step 4: Verify the Deployment
Check the AWS Management Console under **CloudFormation** to confirm the resources are created.

### Step 5: Access the Bastion Server
Use SSH to connect to the bastion server:
```bash
ssh -i bastionhost.pem ec2-user@<bastion-server-public-ip>
```

## Architecture Diagram

Here’s an overview of the architecture created in this project:

<img width="776" alt="Screen Shot 2025-01-10 at 9 11 54 AM" src="https://github.com/user-attachments/assets/fbeac745-8d65-4ae9-b00f-2b7b30530601" />

- **VPC:** Includes CIDR block, DNS support, and DNS hostnames enabled.
- **Subnets:** 1 public and 2 private subnets per Availability Zone.
- **Routing:** Public route table associated with public subnets, allowing internet access.
- **Internet Gateway:** Attached to the VPC for external connectivity.
- **Bastion Host:** Securely manages access to private subnets.
- **EC2 Instances:** Hosted in private subnets with appropriate security groups.

## Debugging Tips

- **Syntax Errors:** Use incremental updates and validate YAML templates for proper formatting.
- **Resource Dependencies:** Ensure resources like the IGW are referenced correctly.
- **Error Monitoring:** Use AWS Console's CloudFormation section to debug stack creation or update errors.

## Tools Used

- **AWS CloudFormation**
- **AWS CLI**
- **YAML**
- **GitHub**
- **Visual Studio Code**

## Key Learnings

- The power of Infrastructure as Code to simplify and automate AWS resource provisioning.
- Best practices for creating secure and scalable network architectures in AWS.
- Practical debugging techniques to handle common CloudFormation errors.

## Author

**Kevin Orellana**  
[LinkedIn](https://www.linkedin.com/in/kevin-orellana-6457aa252) 
[Medium](https://medium.com/@kevinn.orellana01/cloudformation-project-creating-an-aws-vpc-using-infrastructure-as-code-946ad0305f1c)


