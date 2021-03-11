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
