## Virtual Private Cloud (VPC)

- VPC: private network to deploy your resources (regional resource)
- Subnets: allow you to partition your network inside your VPC (Availability Zone resource)
- Public subnet: accessible from the internet
- Private subnet: not accessible from the internet
- Route Tables: determine where network traffic from your subnets are directed.
- Internet Gateway:Enables access to the internet.
- NAT Gateways (AWS-managed) & NAT Instances (self-managed): allow your instances in your Private Subnets to access the internet while remaining private

## NACLs and Security Groups

- NACL (Network ACL)

  - A firewall which controls traffic from and to subnet
  - Can have ALLOW and DENY rules
  - Are attached at the Subnet level
  - Rules only include IP addresses

- Security Groups
  - A firewall that controls traffic to and from an ENI / an EC2 Instance
  - Can have only ALLOW rules
  - Rules include IP addresses and other security groups

## VPC Flow Logs

- Capture information about IP traffic going into your interfaces:
  - VPC Flow Logs
  - Subnet Flow Logs
  - Elastic Network Interface Flow Logs
- Helps to monitor & troubleshoot connectivity issues. Example:
  - Subnets to internet
  - Subnets to subnets
  - Internet to subnets
- Captures network information from AWS managed interfaces too: Elastic Load Balancers, ElastiCache, RDS, Aurora, etc...
- VPC Flow logs data can go to S3 / CloudWatch Logs

## VPC Peering

- Connect two VPC, privately using AWS’ network
- Make them behave as if they were in the same network
- Must not have overlapping CIDR (IP address range)
- VPC Peering connection is not transitive (must be established for each VPC that need to communicate with one another)

## VPC Endpoints

- Endpoints allow you to connect to AWS Services using a private network instead of the public www network
- This gives you enhanced security and lower latency to access AWS services
- VPC Endpoint Gateway: S3 & DynamoDB
- VPC Endpoint Interface: the rest

## Site to Site VPN & Direct Connect

Site to Site VPN

- Connect an on-premises VPN to AWS
- The connection is automatically encr ypted
- Goes over the public internet

- On-premises: must use a Customer Gateway (CGW)
- AWS: must use a Virtual Private Gateway (VGW)

Direct Connect (DX)

- Establish a physical connection between on-premises and AWS
- The connection is private, secure and fast
- Goes over a private network
- Takes at least a month to establish

## Transit Gateway

- For having transitive peering between thousands of VPC and on-premises, hub-and-spoke (star) connection
- One single Gateway to provide this functionality
- Works with Direct Connect Gateway, VPN connections

## Global Infrastructure

- A global application is an application deployed in multiple geographies
- On AWS: this could be Regions and / or Edge Locations
- Decreased Latency
- Disaster Recovery (DR)
- Attack protection

## Route 53

Route53 is a Managed DNS (Domain Name System)

Route 53 performs three main functions

- Domain registration – Route 53 allows you to register domain names.
- Domain Name Service (DNS) – Route 53 translates name to IP addresses using a global network of authoritative DNS servers.
- Health checking – Route 53 sends automated requests to your application to verify that it’s reachable, available and functional.

Routing Policies

- Simple Routing
- Weighted Routing
- Latency Routing
- Failover Routing

## CloudFront

- Content Delivery Network (CDN)
- Improves read performance, content is cached at the edge
- Improves users experience
- 216 Point of Presence globally
- DDoS protection (because worldwide), integration with Shield, AWS Web Application Firewall

Origins

An origin is the origin of the files that the CDN will distribute.

- S3 bucket

  - For distributing files and caching them at the edge
  - Enhanced security with CloudFront Origin Access Identity (OAI)
  - CloudFront can be used as an ingress (to upload files to S3)

- Custom Origin (HTTP)
  - Application Load Balancer
  - EC2 instance
  - S3 website (must first enable the bucket as a static S3 website)
  - Any HTTP backend you want

## S3 Transfer Acceleration

- Increase transfer speed by transferring file to an AWS edge location which will forward the data to the S3 bucket in the target region

## Global Accelerator

- Improve global application availability and performance using the AWS global network
- Leverage the AWS internal network to optimize the route to your application (60% improvement)
- 2 Anycast IP are created for your application and traffic is sent through Edge Locations
- The Edge locations send the traffic to your application
