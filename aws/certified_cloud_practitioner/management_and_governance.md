# Management and Governance

## CloudFormation

- CloudFormation is a declarative way of outlining your AWS Infrastructure, for any resources.
- Within a CloudFormation template:
  - I want a security group
  - I want two EC2 instances using this security group
  - I want an S3 bucket
  - I want a load balancer (ELB) in front of these machines
- Then CloudFormation creates those for you, in the right order, with the exact configuration that you specify

Infrastructure as code

- No resources are manually created, which is excellent for control
- Changes to the infrastructure are reviewed through code

Cost

- Each resources within the stack is tagged with an identifier so you can easily see how much a stack costs you
- You can estimate the costs of your resources using the CloudFormation template
- Savings strategy: In Dev, you could automation deletion of templates at 5 PM and recreated at 8 AM, safely

Productivity

- Ability to destroy and re-create an infrastructure on the cloud on the fly
- Automated generation of Diagram for your templates!
- Declarative programming (no need to figure out ordering and orchestration)

Don’t re-invent the wheel

- Leverage existing templates on the web!
- Leverage the documentation

## Systems Manager (SSM)

- Helps you manage your EC2 and On-Premises systems at scale
- Hybrid AWS service
- Get operational insights about the state of your infrastructure
- Suite of 10+ products
- Most important features are:
  - Patching automation for enhanced compliance
  - Run commands across an entire fleet of servers
  - Store parameter configuration with the SSM Parameter Store
- Works for both Windows and Linux OS

- You need to install the SSM agent onto the systems we control
- Installed by default on Amazon Linux AMI & some Ubuntu AMI

## OpsWorks

- Chef & Puppet help you perform server configuration automatically, or repetitive actions
- They work great with EC2 & On-PremisesVM
- AWS OpsWorks = Managed Chef & Puppet
- It’s an alternative to AWS SSM
- Only provision standard AWS resources: EC2 Instances, Databases, Load Balancers, EBS volumes...

## Control Tower

- Easy way to set up and govern a secure and compliant multi-account AWS environment based on best practices
- Benefits:
  - Automate the set up of your environment in a few clicks
  - Automate ongoing policy management using guardrails • Detect policy violations and remediate them
  - Monitor compliance through an interactive dashboard
- AWS Control Tower runs on top of AWS Organizations:
  - It automatically sets up AWS Organizations to organize accounts and implement SCPs (Service Control Policies)

## Trusted Advisor

Analyze your AWS accounts and provides recommendation::

- Cost Optimization:
  - low utilization EC2 instances, idle load balancers, under-utilized EBS volumes...
  - Reserved instances & savings plans optimizations,
- Performance:
  - High utilization EC2 instances, CloudFront CDN optimizations
  - EC2 to EBS throughput optimizations, Alias records recommendations
- Security:
  - MFA enabled on Root Account, IAM key rotation, exposed Access Keys
  - S3 Bucket Permissions for public access, security groups with unrestricted ports
- Fault Tolerance:
  - EBSsnapshotsage, Availability Zone Balance
  - ASGMulti-AZ, RDSMulti-AZ, ELBconfiguration...
- Service Limits

FREE has 7 trusted Advisor Checks
Enterprise and Business - All trusted advisor checks
