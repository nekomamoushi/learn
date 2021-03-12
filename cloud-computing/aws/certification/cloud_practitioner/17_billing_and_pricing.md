# Billing and Pricing

## AWS Free Services

- IAM (Identity Access Management) --> used for creating user roles.
- Auto Scaling
- CloudFormation
- Elastic Bean
- Opswork
- Amplify
- AppSync
- CodeStar
- AWS Cost Explorer

NOTE: Services in bold are free but they can provision AWS Services to cost money.

## Savings Plan

- Commit a certain $ amount per hour for 1 or 3 years
- Easiest way to setup long-term commitments on AWS
- Setup from the AWS Cost Explorer console

**EC2 Savings Plan**

- Up to 72% discount compared to On-Demand
- Commit to usage of individual instance families in a region (e.g. C5 or M5)
- Regardless of AZ, size (m5.xl to m5.4xl), OS (Linux/Windows) or tenancy
- All upfront, par tial upfront, no upfront

**Compute Savings Plan**

- Up to 66% discount compared to On-Demand
- RegardlessofFamily,Region,size,OS,tenancy,computeoptions
- ComputeOptions:EC2,Fargate,Lambda

## Billing and Costing Tools

Estimating costs in the cloud:

- TCO Calculator
- Simple Monthly Calculator / Pricing Calculator

Tracking costs in the cloud:

- Billing Dashboard
- CostAllocationTags
- Cost and Usage Reports
- Cost Explorer

Monitoring against costs plans:

- Billing Alarms
- Budgets

## Total Cost of Ownership (TCO) Calculators

- AWS helps you reduce Total Cost of Ownership (TCO) by reducing the need to invest in large capital expenditures and providing a pay-as-you-go model
- The TCO calculators allow you to estimate the cost savings when using AWS and provide a detailed set of reports that can be used in executive presentations.
- Compare the cost of your applications in an on-premises or traditional hosting environment to AWS: Server, Storage, Network, IT Labor
- https://awstcocalculator.com/

## Simple Monthly Calculator

- Replaced by AWS Pricing Calculator https://calculator.aws/
- Estimate the cost for your architecture solution.

## Cost Allocation Tags

- Use cost allocation tags to track your AWS costs on a detailed level
- AWS generated tags
  - Automatically applied to the resource you create
  - Starts with Prefix aws: (e.g. aws: createdBy)
- User-defined tags
  - Defined by the user
  - Starts with Prefix user:

## Tagging and Resource Groups

- Tags are used for organizing resources:
  - EC2: instances, images, load balancers, security groups...
  - RDS,VPC resources, Route 53, IAM users, etc...
  - Resources created by CloudFormation are all tagged the same way
- Free naming, common tags are: Name, Environment,Team ...
- Tags can be used to create Resource Groups
  - Create, maintain, and view a collection of resources that share common tags
  - Manage these tags using the Tag Editor

## Cost and Usage Reports

- Dive deeper into your AWS costs and usage
- The AWS Cost & Usage Report contains the most comprehensive set of AWS cost and usage data available, including additional metadata about AWS services, pricing, and reservations (e.g., Amazon EC2 Reserved Instances (RIs)).
- The AWS Cost & Usage Report lists AWS usage for each service category used by an account and its IAM users in hourly or daily line items, as well as any tags that you have activated for cost allocation purposes.
- Can be integrated with Athena, Redshift or QuickSight

## Cost Explorer

- Visualize, understand, and manage your AWS costs and usage over time
- Create custom reports that analyze cost and usage data.
- Analyze your data at a high level: total costs and usage across all accounts
- Or Monthly, hourly, resource level granularity
- Choose an optimal Savings Plan (to lower prices on your bill)
- Forecast usage up to 12 months based on previous usage

## Billing Alarms

- Billing data metric is stored in CloudWatch us-east-1
- Billing data are for overall worldwide AWS costs
- It’s for actual cost, not for projected costs

## Budgets

- Create budget and send alarms when costs exceeds the budget
- 3 types of budgets: Usage, Cost, Reservation
- For Reserved Instances (RI)
  - Track utilization
  - Supports EC2, ElastiCache, RDS, Redshift
- Up to 5 SNS notifications per budget
- Can filter by: Service, Linked Account,Tag, Purchase Option, Instance Type, Region, Availability Zone, API Operation, etc...
- Same options as AWS Cost Explorer!
- 2 budgets are free, then $0.02/day/budget

## AWS Support Plan

Basic

- $0/month
- 24x7 access to customer service, documentation, whitepapers, and support forums.
- Access to the 7 core Trusted Advisor checks and guidance to provision your resources following best practices to increase performance and improve security.
- A personalized view of the health of AWS services, and alerts when your resources are impacted

Developer

- $29/month
- Business hours email access to Cloud Support Associates
- Unlimited cases / 1 primary contact
- Case severity / response times:
  - General guidance: < 24 business hours
  - System impaired: < 12 business hours

Business

- $100/month
- Intended to be used if you have production workloads
- Trusted Advisor – Full set of checks + API access
- 24x7 phone, email, and chat access to Cloud Support Engineers
- Unlimited cases / unlimited contacts
- Access to Infrastructure Event Management for additional fee.
- Case severity / response times:
  - General guidance: < 24 business hours
  - System impaired: < 12 business hours
  - Production system impaired: < 4 hours
  - Production system down: < 1 hour

Enterprise

- $15000/month
- Intended to be used if you have mission critical workloads
- All of Business Support Plan +
- Access to a Technical Account Manager (TAM)
- Concierge SupportTeam (for billing and account best practices)
- Infrastructure Event Management,Well-Architected & Operations Reviews
- Case severity / response times:
  - Production system impaired: < 4 hours
  - Production system down: < 1 hour
  - Business-critical system down: < 15 minutes
