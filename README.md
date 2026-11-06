
# Project 5: AWS VPC - Secure Multi-Tier Network Architecture

## Project Overview

This project demonstrates how to design and build a secure, multi-tier network architecture using Amazon Virtual Private Cloud (VPC).

The objective is to create an isolated AWS network environment that separates public-facing resources from private internal resources while controlling network traffic through routing configurations and Security Groups.

The architecture simulates a real-world company environment where a web application is hosted on a public EC2 instance while internal servers remain in private subnets.

## Project Objectives

- Create and configure a custom Amazon VPC.
- Design public and private subnets.
- Configure Internet Gateway (IGW) and NAT Gateway.
- Create and configure route tables.
- Deploy EC2 instances in different subnets.
- Configure Security Groups.
- Test network connectivity and access restrictions.
- Understand AWS network segmentation and security.

## AWS Services Used

- Amazon VPC
- Amazon EC2
- Internet Gateway (IGW)
- NAT Gateway
- Route Tables
- Security Groups

## Business Scenario

A company wants to deploy a web application on AWS while maintaining secure access to its internal infrastructure.

The company requires:

1. A public-facing web server that can receive HTTP/HTTPS traffic from the internet.
2. Private EC2 instances that cannot be accessed directly from the internet.
3. A NAT Gateway to allow private instances to access the internet for outbound updates without allowing unsolicited inbound connections.
4. Network security controls to restrict unnecessary traffic between resources.

## Network Architecture

The project uses a multi-tier network design consisting of:

- **Public Subnet:** Hosts the web server and Bastion Host.
- **Private Subnet:** Hosts internal application resources.
- **Database Subnet:** Reserved for database resources with no direct internet access.
- **Internet Gateway:** Provides internet connectivity to resources with appropriate public routing and addressing.
- **NAT Gateway:** Allows outbound internet access from private subnets.

## Implementation Steps

### 1. Create a Custom VPC
- Create a VPC with a custom IPv4 CIDR block.

### 2. Configure Subnets
- Create public, private and database subnets.
- Assign appropriate CIDR ranges.
- Enable public IPv4 assignment only where required.

### 3. Configure Internet Gateway
- Create an Internet Gateway.
- Attach it to the custom VPC.
- Configure public route tables to route internet traffic through the IGW.

### 4. Configure NAT Gateway
- Allocate an Elastic IP.
- Deploy a NAT Gateway in the public subnet.
- Configure the private subnet route table for outbound internet access through NAT.

### 5. Deploy EC2 Instances
- Launch an internal EC2 instance in the private subnet.

### 6. Configure Network Security
- Configure Security Groups to allow only necessary traffic.
- Restrict SSH access to trusted sources.

### 7. Test Network Connectivity
- Verify public web server accessibility.
- Verify private EC2 instances cannot be accessed directly from the internet.
- Verify outbound internet access through the NAT Gateway.
- Test network traffic restrictions.

## Expected Results

- Public resources can communicate with the internet through the Internet Gateway.
- Private resources remain inaccessible through direct inbound internet connections.
- Private instances can access external resources through the NAT Gateway.
- Network traffic is restricted according to the configured security rules.

## Key Concepts Learned

- VPC and CIDR addressing.
- Public vs Private Subnets.
- Internet Gateway vs NAT Gateway.
- Route Tables and Routing.
- Security Groups vs Network ACLs.
- AWS Network Segmentation.
- Cloud Network Security.

## Conclusion

This project demonstrates the implementation of a secure multi-tier network architecture using AWS networking services.

Through this hands-on project, I gained practical experience in designing VPC infrastructure, configuring network connectivity, implementing access restrictions and troubleshooting communication between AWS resources.

## Cost Management

- Monitor AWS resource usage through AWS Billing.
- Delete NAT Gateway after completing the project.
- Release unused Elastic IP addresses.
- Terminate EC2 instances when they are no longer required.
- Delete unnecessary VPC resources after testing.
