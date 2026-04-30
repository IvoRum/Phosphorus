---
tags:
  - aws
---
Amazon virtual private could 
Provision a private part of the could and dose not make access to the internet.

### Amazon Virtual Private Cloud (Amazon VPC)
An Amazon VPC lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.
### Subnet
Subnets are used to organize your resources and can be made publicly or privately accessible. A private subnet is commonly used to contain resources like a database storing customer or transactional information. A public subnet is commonly used for resources like a customer-facing website.
![[Pasted image 20260427083544.png]]

Лична мрежа която вече може да вдигаш каквото си искаш в него и да споделяш ресурси спокойно към външни сервизи.

Това изолиране межди публични и лични сервизи се случва през Internet gateway или Virtual private gateway. Тази връска може да се усъществи и с нещо наречено [[AWS Direct Connect]]
![[Pasted image 20260427090008.png]]

> **Virtual private network**

A VPN encrypts your internet traffic, helping protect it from anyone who might try to intercept or monitor it.

![[Pasted image 20260427090843.png|150]]
> **AWS Client VPN**

AWS Client VPN is a networking service you can use to connect your remote workers and on-premises networks to the cloud. It is a fully managed, elastic VPN service that automatically scales up or down based on user demand. Because it is a cloud VPN solution, you don’t need to install and manage hardware or try to estimate how many remote users to support at one time.

**Benefits:** AWS Client VPN provides advanced authentication, remote access. It is elastic and fully managed.

**Use case:** It can be used to quickly scale remote-worker access.
![[Pasted image 20260427091108.png]]

Client VPN, a managed VPN service, provides secure access to AWS resources and on-premises networks from anywhere. It uses an OpenVPN-based client, and it works with global Regions by using the AWS global network.

> **AWS Site-to-Site VPN**

Site-to-Site VPN creates a secure connection between your data center or branch offices and your AWS Cloud resources.

**Benefits:** Site-to-Site VPN provides high availability, secure and private sessions, and accelerates applications.

**Use cases:** It can be used for application migration and secure communication between remote locations.
![[Pasted image 20260427091158.png]]


> **AWS PrivateLink**

AWS PrivateLink is a highly available, scalable technology that you can use to privately connect your VPC to services and resources as if they were in your VPC. You do not need to use an internet gateway, NAT device, public IP address, Direct Connect connection, or AWS Site-to-Site VPN connection to allow communication with AWS services or resources from your private subnets. Instead, you control the specific API endpoints, sites, services, and resources that are reachable from your VPC.

**Benefits:** AWS PrivateLink helps you secure your traffic and connect with simplified management rules.

**Use case:** It is used for connecting your clients in your VPC to resources, other VPCs, and endpoints.

> **AWS Direct Connect**

Direct Connect is a service that makes it possible for you to establish a dedicated private connection between your network and VPC in the AWS Cloud.

**Benefits:** AWS Direct Connect reduces network costs and increases amount of bandwidth.
![[Pasted image 20260427091417.png]]



# Additional gateway services

## AWS Transit Gateway

AWS Transit Gateway is used to connect your Amazon VPCs and on-premises networks through a central hub. As your cloud infrastructure expands globally, inter-Region peering connects transit gateways together using the AWS Global Infrastructure. To learn more, refer to [AWS Transit Gateways(opens in a new tab)](https://aws.amazon.com/transit-gateway/).

## Network Address Translation (NAT) Gateway

A NAT gateway is a NAT service. You can use a NAT gateway so that instances in a private subnet can connect to services outside your VPC but external services can't initiate a connection with those instances. To learn more, refer to [NAT gateway(opens in a new tab)](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)
## Amazon API Gateway

You learned about Application Programming Interface (API)s earlier. Quick refresher, an API defines how different software systems can interact and communicate with each other. The Amazon API Gateway is an AWS service for creating, publishing, maintaining, monitoring, and securing APIs at any scale. To learn more, refer to [Amazon API Gateway(opens in a new tab)](https://aws.amazon.com/api-gateway/).

