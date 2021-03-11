# Global Infrastructure

- **22 Geographic Regions** (_physical location with multiple Availabilty Zones_)
- **69 Availability Zones** (_one or more discrete data locations_)
- **Edge Locations** (_data center owned by trusted partner of aws_)

## Region

- A region is a cluster of data centers
- Names can be: us-east-1, eu-west-3, etc...
- Most AWS services are region-scoped
- Not all services are available in the all regions.
- US-EAST(North Virginia) is the largest AWS region and services almost always become available first in this region.
- US-EAST-1 is where you see your billing information.

## How to choose an AWS Region ?

- Proximity to customers (_reduced latency_)
- Available services within a Region (_new services and new features aren’t available in every Region_)
- Pricing (_varies region to region and is transparent in the service pricing page_)
- Compliance with data governance and legal requirements (_data never leaves a region without your explicit permission_)

## Availability Zone (AZ)

- Each Region has multiple AZs (usually 3, min is 2, max is 6)
  • ap-southeast-2a
  • ap-southeast-2b
  • ap-southeast-2c
- Each availability zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity
- They’re separate from each other, so that they’re isolated from disasters
- They’re connected with high bandwidth, ultra-low latency networking
- less than 10ms latency between AZs

## Edge Locations

- 216 Points of Presence (205 Edge Locations & 11 Regional Caches) in 84 cities across 42 countries
- These location serve requests for CloudFront and Route53. Requests going to either of these services will be routed to the nearest edge location automatically.
- S3 Transfer accelaration and API Gateway endpoint also use the AWS Edge Network.
- Content is delivered to end users with lower latency

## Gov Cloud

An AWS service that allows customers to host sensitive Controlled Unclassified Information or other types of workloads

- Only operated by US Citizens or on the US Soil.
- Should follow several compliance guidelines.
- [GovCloud](https://aws.amazon.com/govcloud-us/?whats-new-ess.sort-by=item.additionalFields.postDateTime&whats-new-ess.sort-order=desc)

## Shared Responsibility Model

- AWS = Responsability for the security **OF** the cloud
- Customer = Responsability for the security **IN** the cloud

## AWS Acceptable Use Policy

- No Illegal, Harmful, or Offensive Use or Content
- No Security Violations
- No Network Abuse
- No E-Mail or Other Message Abuse
- [aup](https://aws.amazon.com/aup)
