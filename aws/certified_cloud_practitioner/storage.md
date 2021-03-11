# Storage

## Elastic Block Store (EBS)

- An EBS Volume is a network drive you can attach to your instances while they run
- It allows your instances to persist data, even after their termination
- Can only be mounted to one instance at a time (at the CCP level)
- Bound to a specific AZ
- Free tier: 30 GB of free EBS storage of type General Purpose (SSD) or Magnetic per month

- It’s a network drive (i.e. not a physical drive)
  - It uses the network to communicate the instance, which means there might be a bit of latency
  - It can be detached from an EC2 instance and attached to another one quickly
- It’s locked to an Availability Zone (AZ)
  - An EBS Volume in us-east-1a cannot be attached to us-east-1b
  - To move a volume across, you first need to snapshot it
- Have a provisioned capacity (size in GBs, and IOPS)
  - You get billed for all the provisioned capacity
  - You can increase the capacity of the drive over time

## EBS Snapshots

- Make a backup (snapshot) of your EBS volume at a point in time
- Stored on S3
- Not necessary to detach volume to do snapshot, but recommended
- Can copy snapshots across AZ or Region

## EC2 Instance Store

- If you need a high-performance hardware disk, use EC2 Instance Store
- Better I/O performance
- EC2 Instance Store lose their storage if they’re stopped (ephemeral)
- Good for buffer / cache / scratch data / temporary content
- Risk of data loss if hardware fails
- Backups and Replication are your responsibility

## Elastic File System (EFS)

- Managed NFS (network file system) that can be mounted on 100s of EC2
- Pay for what you use
- EFS works with Linux EC2 instances (1 to 1000) in multi-AZ
- Highly available, scalable, expensive (3x gp2), pay per use, no capacity planning
- Good for big data and analytics, media processing workflows, content management, web serving, home directories, etc...
