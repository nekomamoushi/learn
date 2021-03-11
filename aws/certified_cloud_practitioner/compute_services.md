# Compute Services

## Elastic Container Service (ECS)

It provides a highly scalable, high performance container management service that supports Docker containers and allows you to easily run applications on a managed cluster of Amazon EC2 instances.

Amazon ECS eliminates the need for you to install, operate, and scale your own cluster management infrastructure.

- You must provision & maintain the infrastructure (EC2 instances)
- AWS takes care of starting / stopping containers
- Has integrations with the Application Load Balancer

## Fargate

- Serverless compute engine for containers
- Deploy and manage applications, not infrastructure (no EC2 to manage)
- AWS just runs containers for you based on the CPU / RAM you need
- Secure isolation by design
- Pricing based on the vCPU and memory resources used from the time you start to download your container image until ECS Task or EKS Pod terminates, rounded up to the nearest second.

## Elastic Kubernetes Service (EKS)

EKS gives you the flexibility to start, run, and scale Kubernetes applications in the AWS cloud or on-premises. Amazon EKS helps you provide highly-available and secure clusters and automates key tasks such as patching, node provisioning, and updates.

## Elastic Container Registry (ECR)

- Private Docker Registry on AWS
- This is where you store your Docker images so they can be run by ECS or Fargate

### Lambda

- Virtual functions (no servers to manage)
- Short executions (up to 15 minutes)
- Run on-demand
- Scaling is automated

Pricing:

- Pay per request and compute time
- Free tier:
  - 1,000,000 AWS Lambda requests
  - 400,000 GBs of compute time
- $0.20 per 1 million requests thereafter (calls)
- After that $1.00 for 600,000 GB-seconds (duration)

Supported Language:

- Node.js
- Python
- Java (Java 8 compatible)
- C# (.NET Core)
- Golang
- C# / Powershell
- Ruby
- Custom Runtime API
- Lambda Container Image
  - The container image must implement the Lambda Runtime API
  - ECS / Fargate is preferred for running arbitrary Docker images
