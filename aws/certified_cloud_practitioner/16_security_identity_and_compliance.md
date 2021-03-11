# Security

## Responsability

**AWS responsibility** -> Security **OF** the Cloud

- Protecting infrastructure (hardware, software, facilities, and networking) that runs all the AWS services
- Managed services like S3, DynamoDB, RDS, etc.

**Customer responsibility** -> Security **IN** the Cloud

- For EC2 instance, customer is responsible for management of the guest OS (including security patches and updates), firewall & network configuration, IAM
- Encrypting application data

**Shared controls**

- Patch Management, Configuration Management, Awareness & Training

## Shield

A managed DDOS (Distributed Denial of Service) protection service that safeguards applications running on aws.

All AWS customers benefit from the automatic protections of AWS shield standard at no charge.

When you route your traffic through Route 53 or CloudFront you are using AWS Shield.

Protects you against attacks

- Layer 7 -> Application
- Layer 4 -> Transport
- Layer 3 -> Network

There's also a paid tier known as Shield Advance and that costs $3000/Year(upfront or Commitment).

It gives you extra protection with 24/7 support and its available on

- Amazon Route 53
- Amazon CloudFront
- ELB
- AWS Global Accelarator
- Elastic IP(Amazon Elastic Compute Cloud and Netword and Load Balancer).

## Web Application Firewall (WAF)

It allows you protect your web application against the most common exploits.

You can write your own rules that will allow the traffic based on the contents of HTTP requests.

You can use rule set from AWS trusted security partner. It can be either attached to CloudFront or Application Load Balance (ALB).

Most Common Attacks Include

- Injection
- Broken Authentication
- Sensitive Data Exposure
- XML External Entities XXE
- Broken Access Control
- Security Misconfigurations
- XSS Cross Site Scripting
- Insecure Deserialization
- Using Components with known Vulnerabilities
- Insufficient logging and Monitoring

## Penetration Testing

An authorized service that allows you simulate a cyber attack on a computer system, performed to evaluate the security of the system.

Permitted Services (Without approval)

- EC2 Instances, NAT Gateways, and ELB.
- RDS
- CloudFront
- Aurora
- API Gateways
- AWS Lambda and Lambda@Edge function
- LightSail resources.
- Elastic Beanstalk env

Prohibited Services

- DNS zone walking via Amazon Route 53 Hosted Zones.
- DoS (Denial Of Service), DDoS, Simulated DoS, Simulated DDoS.
- Port flooding
- Protocol flooding
- Request flooding

## Data -> at rest / in transit

At rest (_data stored or archived on a device_)

- On a hard disk, on a RDS instance, in S3 Glacier Deep Archive, etc.

In transit (_in motion, data being moved from one location to another_)

- Transfer from on-premises to AWS, EC2 to DynamoDB, etc.
- Means data transferred on the network

### Key Management Service (KMS)

- Anytime you hear “encryption” for an AWS service, it’s most likely KMS
- KMS = AWS manages the encryption keys for us
- Encryption Opt-in:
  - EBS volumes: encrypt volumes
  - S3 buckets: Server-side encryption of objects
  - Redshift database: encryption of data
  - RDS database: encryption of data
  - EFS drives: encryption of data
- Encryption Automatically enabled:
  - CloudTrail Logs
  - S3 Glacier
  - Storage Gateway

### CloudHSM

- KMS => AWS manages the software for encryption
- CloudHSM => AWS provisions encryption hardware
- Dedicated Hardware (HSM = Hardware Security Module)
- You manage your own encryption keys entirely (not AWS)

### Customer Master Keys (CMK)

- Customer Managed CMK:

  - Create, manage and used by the customer, can enable or disable
  - Possibility of rotation policy (new key generated every year, old key preserved)
  - Possibility to bring-your-own-key

- AWS managed CMK:

  - Created, managed and used on the customer’s behalf by AWS
  - Used by AWS services (aws/s3, aws/ebs, aws/redshift)

- AWS owned CMK:

  - Collection of CMKs that an AWS service owns and manages to use in multiple accounts
  - AWS can use those to protect resources in your account (but you can’t view the keys)

- CloudHSM Keys (custom keystore):
  - Keys generated from your own CloudHSM hardware device
  - Cryptographic operations are performed within the CloudHSM cluster

## Secrets Manager

- Storing secrets
- Capability to force rotation of secrets every X days
- Automate generation of secrets on rotation (uses Lambda)
- Integration with Amazon RDS (MySQL, PostgreSQL, Aurora)
- Secrets are encrypted using KMS
- Mostly meant for RDS integration

## Artifact

Portal that provides customers with on-demand access to AWS compliance documentation and AWS agreements
Can be used to support internal audit or compliance

## Inspector

- Automated Security Assessments for EC2 instances
- Analyze the running OS against known vulnerabilities
- Analyze against unintended network accessibility
- AWS Inspector Agent must be installed on OS in EC2 instances

## Guard Duty

Guard Duty is a threat detection service that continuously monitors for the malicious,suspicious activity and unauthorized behavior.
Uses Machine Learning algorithms, anomaly detection, 3rd party data

Analyze logs:

- CloudTrail Logs.
- VPC Flow Logs
- DNS logs.

It will alert you of the findings which you can automate an incident response via CloudWatch Events or 3rd Party Software.

## Config

- Helps with auditing and recording compliance of your AWS resources
- Helps record configurations and changes over time
- Possibility of storing the configuration data into S3 (analyzed by Athena)
- Questions that can be solved by AWS Config:
  - Is there unrestricted SSH access to my security groups?
  - Do my buckets have any public access?
  - How has my ALB configuration changed over time?
- You can receive alerts (SNS notifications) for any changes • AWS Config is a per-region service
- Can be aggregated across regions and accounts

## Macie

Macie is fully managed service that continuously monitors S3 data access activity for anomalies and generates detailed alerts when it detects risk of unqthorized access or inadvertent data leaks.

It uses machine learning to analyze CloudTrail logs.

It provides you with following alerts.

- Anonymized Access.
- Config Compliance
- Credential loss
- Data Compliance
- File Hosting
- Identity Enumeration
- Information Loss
- Location Anomaly
- Open Permisson
- Privilege Escalation
- Ransomware
- Service Disruption
- Suspiscious Activity

## Security Hub

AWS Security Hub gives you a comprehensive view of your security alerts and security posture across your AWS accounts.

With Security Hub, you now have a single place that aggregates, organizes, and prioritizes your security alerts, or findings, from multiple AWS services, such as:

- Amazon GuardDuty
- Amazon Inspector
- Amazon Macie
- AWS Identity and Access Management (IAM) Access Analyzer
- AWS Systems Manager
- AWS Firewall Manager
- AWS Partner Network (APN) solution

## Detective

- Amazon Detective analyzes, investigates, and quickly identifies the root cause of security issues or suspicious activities (using ML and graphs)
- Automatically collects and processes events from VPC Flow Logs, CloudTrail, GuardDuty and create a unified view
- Produces visualizations with details and context to get to the root cause

## Abuse

- Report suspected AWS resources used for abusive or illegal purposes
- Abusive & prohibited behaviors are:
  - Spam – receving undesired emails from AWS-owned IP address, websites & forums spammed by AWS resources
  - Port scanning – sending packets to your ports to discover the unsecured ones
  - DoS or DDoS attacks – AWS-owned IP addresses attempting to overwhlem or crash
  - Intrusion attempts – logging in on your resources
  - Hosting objectionable or copyrighted content – distributing illegal or copyrighted content without consent
  - Distributing malware – AWS resources distributing softwares to harm computers or machines
- Contact the AWS Abuse team: AWS abuse form, or abuse@amazonaws.com

## Single Sign-On (SSO)

- Centrally manage Single Sign- On to access multiple accounts and 3rd-party business applications.
- Integrated with AWS Organizations
- Supports SAML 2.0 markup
- Integration with on-premise Active Directory

## Directory Services

- AWS Managed Microsoft AD
  - Create your own AD in AWS, manage users
  - Establish “trust” connections with your on-premise AD
- AD Connector
  - Directory Gateway (proxy) to redirect to on-premise AD
  - Users are managed on the on-premise AD
- Simple AD
  - AD-compatible managed directory on AWS
  - Cannot be joined with on-premise AD

## Organizations

- Global service
- Allows to manage multiple AWS accounts
- The main account is the master account
- Cost Benefits:
  - Consolidated Billing across all accounts - single payment method
  - Pricing benefits from aggregated usage (volume discount for EC2, S3...)
  - Pooling of Reserved EC2 instances for optimal savings
- API is available to automate AWS account creation
- Restrict account privileges using Service Control Policies (SCP)

### Multi Account Strategies

- Create accounts per department, per cost center, per dev / test / prod, based on regulatory restrictions (using SCP), for better resource isolation (ex:VPC), to have separate per-account service limits, isolated account for logging
- Multi Account vs One Account Multi VPC
- Use tagging standards for billing purposes
- Enable CloudTrail on all accounts, send logs to central S3 account
- Send CloudWatch Logs to central logging account

### Service Control Policies (SCP)

- Whitelist or blacklist IAM actions
- Applied at the OU or Account level
- Does not apply to the Master Account
- SCP is applied to all the Users and Roles of the Account, including Root user
- The SCP does not affect service-linked roles
  - Service-linked roles enable other AWS services to integrate with AWS Organizations
    and can't be restricted by SCPs.
- SCP must have an explicit Allow (does not allow anything by default)
- Use cases:
  - Restrict access to certain services (for example: can’t use EMR)
  - Enforce PCI compliance by explicitly disabling services

### Consolidated billing

- One bill
  - One bill for multiple accounts
- Easy tracking
  - You can track the charges across multiple accounts and download the combined cost and usage data.
- Combined usage
  - You can combine the usage across all accounts in the organization to share the volume pricing discounts and Reserved Instance discounts. This can result in a lower charge for your project, department, or company than with individual standalone accounts.
- No extra fee
  - Consolidated billing is offered at no additional cost.
- Easy to track charges and allocate costs.
- Volume pricing discounts can be applied to resources.
- Consolidated billing allows you to get volume discounts on all of your accounts.
- Unused reserved instances (RIs) for EC2 are applied across the group.
