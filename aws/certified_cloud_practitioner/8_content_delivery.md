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
