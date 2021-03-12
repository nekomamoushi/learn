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
