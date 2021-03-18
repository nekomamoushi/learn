# Elastic Compute Cloud (EC2)

- Infrastructure as a Service
- It mainly consists in the capability of :
  - Renting virtual machines (EC2)
  - Storing data on virtual drives (EBS)
  - Distributing load across machines (ELB)
  - Scaling the services using an auto-scaling group (ASG)

## Sizing & Configuration options

- Operating System (OS): Linux or Windows
- How much: CPU, RAM, Storage
- Network-attached (EBS & EFS)
- Hardware (EC2 Instance Store)
- Network card: speed of the card, Public IP address
- Firewall rules: security group
- Bootstrap script (configure at first launch): EC2 User Data

## Instance Types

1. **General Purpose**
   - Great for a diversity of workloads such as web servers or code repositories
   - Balance between: Compute, Memory, Networking
2. **Compute Optimized**
   - Great for compute-intensive tasks that require high performance processors
     - Batch processing workloads
     - Media transcoding
     - High performance web servers
     - High performance computing (HPC)
     - Scientific modeling & machine learning
     - Dedicated gaming servers
3. **Memory Optimized**
   - Fast performance for workloads that process large data sets in memory
     - Floating point number calculations
     - Graphic processing
     - Data pattern matching
4. **Storage Optimized**
   - Great for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage
     - High frequency online transaction processing (OLTP) systems
     - Relational & NoSQL databases
     - Cache for in-memory databases (for example, Redis)
     - Data warehousing applications
     - Distributed file systems

### Instances Pricing Model

- **On-Demand**

  - Good for first apps or prototypes.
  - Short workload
  - Predictable pricing
  - No upfront payment.

- **Reserved** (min 1 year)

  - Up to 72% discount compared to On-demand
  - Reservation period: 1 year (discount) - 3 years(more discount)
  - Purchasing options: no upfront, partial upfront, all upfront
  - Reserve a specific instance type
  - Recommended for steady-state usage applications (think database)
  - RI's can be shared between multiple accounts.
  - You can even sell your unused instances.

- **Convertible Reserved**

  - can change the EC2 instance type
  - Up to 45% discount

- **Scheduled Reserved**

  - launch within time window you reserve
  - When you require a fraction of day / week / month
  - Commitment for 1 year only

- **Spot**

  - short workloads, cheap, can lose instances (less reliable)
  - up to 90% discount compared to On-demand
  - Instances that you can “lose” at any point of time if your max price is less than the current spot price
  - If you instance gets terminated you dont get charged for partial hour of usuage.
  - If you terminate an instance you will be charged for any hour that it ran.
  - The MOST cost-efficient instances in AWS
  - Useful for workloads that are resilient to failure
    - Batch jobs
    - Data analysis
    - Image processing
    - Any distributed workloads
    - Workloads with a flexible start and end time
    - Not suitable for critical jobs or databases

- **Dedicated Hosts**

  - book an entire physical server, control instance placement
  - Allocated for your account for a 3-year period reservation
  - More expensive
  - Useful for software that have complicated licensing model (Bring Your Own License)
  - Or for companies that have strong regulatory or compliance needs

- **Dedicated Instances**

  - Instances running on hardware that’s dedicated to you
  - May share hardware with other instances in same account
  - No control over instance placement (can move hardware after Stop / Start)

## Amazon Machine Image (AMI)

Customization of an EC2 instance:

- You add your own software, configuration, operating system, monitoring...
- Faster boot / configuration time because all your software is pre-packaged
- AMI are built for a specific region (and can be copied across regions)

You can launch EC2 instances from:

- A Public AMI: AWS provided
- Your own AMI: you make and maintain them yourself
- An AWS Marketplace AMI: an AMI someone else made (and potentially sells)

AMI Process (from an EC2 instance)

- Start an EC2 instance and customize it
- Stop the instance (for data integrity)
- Build an AMI (this will also create EBS snapshots)
- Launch instances from other AMIs

### Security Groups

- They control how traffic is allowed into or out of our EC2 Instances
- They only contain ALLOW rules
- Their rules can reference by IP or by security group

They're like a firewall.
