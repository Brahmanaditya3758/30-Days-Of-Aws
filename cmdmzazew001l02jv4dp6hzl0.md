---
title: "(Day 03) Task : VPC Explained :-"
datePublished: Mon Jul 28 2025 10:42:15 GMT+0000 (Coordinated Universal Time)
cuid: cmdmzazew001l02jv4dp6hzl0
slug: day-3-task-vpc-explained
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1753698674862/529cede6-1ca7-4ea5-87dd-74c4779967d8.png
tags: aws, vpc, 2articles1week, day3, abhishek-veeramalla

---

## **What is a VPC?**

A Virtual Private Cloud (VPC) is a logically isolated section of AWS Cloud where you can launch AWS resources (like EC2, RDS, etc.) in a virtual network that you define.

Think of a VPC as your own private data center on the cloud. You decide its size, subnets, routing, security, and control how resources connect internally and with the internet.

**In DevOps and production systems, VPC ensures secure, scalable, and controlled networking.**

## Company Use Case: Why We Use VPC?

Let’s imagine a gaming company — "CloudGaming Ltd." — wants to host their online multiplayer game on AWS. They want it to be fast, secure, scalable, and globally accessible.

***<mark>Without VPC:</mark>***

* All services would be deployed in a shared, public environment.
    
* Security breaches are more likely.
    
* No granular control over who accesses what and how.
    

***<mark>With VPC:</mark>***

* The company gets a custom private network in AWS.
    
* Resources are isolated and controlled via firewalls, routing, and access controls.
    
* Even if a hacker compromises one part, the rest stays protected using layered security like NACLs and Security Groups.
    

## Components of a VPC

Below are the key building blocks of a VPC, and how we use them in the real-world project setup:

1. ### **CIDR Block (IP Range) :**
    

* Defines the IP address range of your VPC.
    
* Example: `10.0.0.0/16` gives you 65,536 IP addresses.
    
* You split this into smaller subnets
    

2. ### **Subnets :**
    

* Sub-networks inside your VPC.
    
* ***Two types:***
    
    * **Public Subnet** — for internet-facing services (e.g., Load Balancers, Bastion Hosts).
        
    * **Private Subnet** — for internal services (e.g., Databases, App Servers).
        

3. ### **Internet Gateway (IGW) :**
    

* Allows internet access for resources in public subnet.
    
* Must be attached to the VPC and associated via Route Table.
    

4. ### **Route Table :**
    

* Controls how traffic flows within subnets and to the internet.
    
* Public subnet route table:
    
    * Routes to Internet Gateway
        
* Private subnet route table:
    
    * Routes through NAT Gateway
        

5. ### **NAT Gateway :**
    

* Allows private subnet resources to access the internet without exposing them.
    
* Example: App server downloads software updates from internet without being public.
    

6. ### **Security Group :**
    

* Acts as a virtual firewall for your EC2 instances.
    
* Stateful: If you allow inbound, the corresponding outbound is allowed automatically.
    

7. ### **Network ACL (NACL) :**
    

* An optional stateless firewall for subnets.
    
* You define inbound and outbound rules separately.
    
* Useful for additional subnet-level security.
    

8. ### **Elastic Load Balancer (ELB) :**
    

* Distributes traffic across multiple instances.
    
* Deployed in public subnet.
    
* Sends traffic to app servers in private subnet.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1753699316698/a1b89738-1a51-4865-9228-12ca15c4dbd1.png align="center")

## Coming Up Next :-

Stay tuned for Day 4, where we’ll dive into Security Groups vs NACLs with practical comparisons and case-based configuration.