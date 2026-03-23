---
tags:
  - aws
---

Elastic compute cloud 2
Pay for what you use
Compute as a service
Virtual machines with other vm's creating multitenancy provider.

Configuration:
- OS
	- Windows
	- Linux
- What runs on it
	- Internal business apps
	- web apps
	- Databases
	- Third-party software
- Scaling
	- Vertically with more memory
- Network

# Types 
- General purpose
	- Balanced resources
	- Diverse workloads
	- Web servers
	- Code repositories
- Compute optimized
	- Compute-intenseve tasks
	- Gaming servers
	- High performance computing (HPC)
	- Scientific modeling
- Memory optimized
	- Memoty-intensive tasks
	- Batch request with a big payload that needs processing
	- Large datasets, data analytics, and databases.
- Accelerated computing
	- Floating point number calculations
	- Gothics processing
	- Data pattern matching
	- Hardware accelerators 
	- Machine learning.
- Storage optimized
	- High performance for locally stored data

# Crating
search "ec2" -> Launch instance -> Start set up

## Set up
1- Instance name
2- Select AMI with is a template of the desired instance. Eg. Amazon Linux withs is a general use image.
3- Instance type. This is what the specs of the machine are. What power dose it have. 
4- Key pair. How we access the vm.
5- Network setting. Click Allow HTTP traffic for web services hosting.
6- Storage. How many gb of storage and by what means. Eg. [[GP 3|gp3]].
7- Advanced details to se up the web server -> to user data -> this is the please where you can run a script for installing and preparing the machine for the web server. Its bash.

# Pricing
- On-Demand
	- Pay for how long it runs
	- Spin up test and stop 
	- To see how much usage will be required 
- Savings Plans
	- lower pricing but comes with a commitment for usage
	- Regardless of region, Az & tendency 
	- Applicable for [[AWS Lambda]] & [[AWS Fargate]]
- Reserved Instances
	- For study sate workflows and predictable usage
	- Up to 70% discount if you commit to one year or two year term. All upfront, partial upfront and no upfront.
- Spot Instance
	- Request space EC2 capacity for up to 90% savings
	- However AWS can reclama that instance if necessary.
	- 2 min warning to save
	- Work loads that can be interrupted 
- Dedicated host
	- Physical servers for full use over them.
	- Best for security


Yes, move the new logic and refactor the method to improve readability. Adding more logic now will only make it harder to maintain in the future. It's better to rework the method to avoid increasing its complexity.