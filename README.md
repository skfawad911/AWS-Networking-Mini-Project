# AWS Networking Mini Project

## Overview

This mini project demonstrates the implementation of a networking setup in AWS. The setup includes a Virtual Private Cloud (VPC) with both public and private subnets, an Internet Gateway, and an EC2 instance.

## Project Structure

The Cloud Architecture comprises the following components:
<img src="Images/20.jpg" alt="Configure VPC">


### 1. Virtual Private Cloud (VPC)

- **Name:** test-vpc
- **IPv4 CIDR Block:** 12.0.0.0/16

### 2. Public Subnet

- **CIDR Block:** 12.0.1.0/24
- **Accessibility:** Publicly accessible on the internet
- **Resources:** EC2 instance for hosting websites or webpages

### 3. Private Subnet

- **CIDR Block:** 12.0.3.0/24
- **Accessibility:** Local access only, not publicly accessible
- **Resources:** Specific resources that shouldn't be accessible from the internet

### 4. Internet Gateway

- Enables internet access for resources in the public subnet.

### 5. Route Tables

#### Public Subnet Route Table

- Routes traffic to the Internet Gateway, providing internet access to resources in the public subnet.

#### Private Subnet Route Table

- Manages local traffic within the VPC, ensuring resources in the private subnet are not directly accessible from the internet.

## Step by Step Process

### 1. Creating a VPC
- And do the following Configuration
 <img src="Images/1.png" alt="Create VPC">
 <img src="Images/2.png" alt="Configure VPC">

### 2. Creating a Internet Gateway
- Creating a new Internet Gateway [select IG from VPC Dashboard]
<img src="Images/3.png" alt="Create VPC">
<img src="Images/4.png" alt="Configure VPC">
- Here, state would be detached, we need to attach it 
<img src="Images/5.png" alt="Create VPC">
<img src="Images/6.png" alt="Configure VPC">
 
### 3. Creating Subnets
- Creating a public subnet [select subnet from VPC Dashboard]
<img src="Images/7.png" alt="Create">
<img src="Images/8.png" alt="Configure">
<img src="Images/9.png" alt="Configure">
- Now click on Add new subnet and create a private subnet 
 <img src="Images/10.png" alt="Configure">

 ### 4. Create Route Tables
 - Create a public route table [select route table from VPC Dashboard]
<img src="Images/11.png" alt="Configure">
<img src="Images/12.png" alt="Configure">
- Now click on created route table and select Edit Routes
<img src="Images/13.png" alt="Configure">
- Select subnet associtions and edit
<img src="Images/14.png" alt="Configure">
- Now again create a new private route table
- no need to add 0.0.0.0/0 route for this one as it only need local access
<img src="Images/15.png" alt="Configure">
<img src="Images/16.png" alt="Configure">

### 5. Now launch EC2 in Public subnet
- Just launch new instance
- Name it test-ec2-public-subnet
- Select the key pair
- Now edit Network settings
<img src="Images/17.png" alt="Configure">
<img src="Images/18.png" alt="Configure">
- Connect from SSH client
<img src="Images/19.png" alt="Configure">
