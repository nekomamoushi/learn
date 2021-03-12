# Snow Family

Highly-secure, portable devices to collect and process data at the edge, and migrate data into and out of AWS
If it takes more than a week to transfer over the network, use Snowball devices!

## Snowball Edge (for data transfers)

- Physical data transport solution (moveTBs or PBs of data in or out of AWS)
- Alternative to moving data over the network (and paying network fees)
- Pay per data transfer job
- Provide block storage and Amazon S3-compatible object storage
- Snowball Edge Storage Optimized
  - 80 TB of HDD capacity for block volume and S3 compatible object storage
- Snowball Edge Compute Optimized
  - 42 TB of HDD capacity for block volume and S3 compatible object storage
- Large data cloud migrations, DC decommission, Disaster Recovery

## Snowcone

- Small, portable computing, anywhere, rugged & secure, withstands harsh environments
- Light (4.5 pounds, 2.1 kg)
- Device used for edge computing, storage, and data transfer
- 8 TBs of usable storage
- Use Snowcone where Snowball does not fit (space-constrained environment)
- Must provide your own battery / cables
- Can be sent back to AWS offline, or connect it to internet and use AWS DataSync to send data

## Snowmobile

- Transfer exabytes of data (1 EB = 1,000 PB = 1,000,000 TBs)
- Each Snowmobile has 100 PB of capacity (use multiple in parallel)
- High security: temperature controlled, GPS, 24/7 video surveillance
- Better than Snowball if you transfer more than 10 PB

## Edge Computing

- Snowcone (smaller)

  - 2 CPUs, 4 GB of memory, wired or wireless access • USB-C power using a cord or the optional battery

- Snowball Edge – Compute Optimized

  - 52 vCPUs, 208 GiB of RAM
  - Optional GPU (useful for video processing or machine learning)
  - 42TBusablestorage

- Snowball Edge – Storage Optimized

  - Up to 40 vCPUs,80 GiB of RAM
  - Object storage clustering available

- All: Can run EC2 Instances & AWS Lambda functions (using AWS IoT Greengrass)
- Long-term deployment options: 1 and 3 years discounted pricing

## OpsHub

Manage your Snow Family Device.

- Unlocking and configuring single or clustered devices
- Transferring files
- Launching and managing instances running on Snow Family Devices
- Monitor device metrics (storage capacity, active instances on your device)
- Launch compatible AWS services on your devices (ex: Amazon EC2 instances, AWS DataSync, Network File System (NFS))
