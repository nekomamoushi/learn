# Development

## CodeCommit

- Public offering is GitHub, AWS product is CodeCommit
- Source control service that hosts Git-based repositories
- The code changes are automatically versioned

Benefits:

- Fully managed
- Scalable & highly available
- Private, Secured, Integrated with AWS

## CodeBuild

- Code building service in the cloud
- Compiles source code, run tests, and produces packages that are ready to be deployed

Benefits:

- Fully managed, serverless
- Continuously scalable & highly available
- Secure
- Pay-as-you-go pricing (only pay for the build time)

## CodeDeploy

- We want to deploy our application automatically
- Works with EC2 Instances and On-Premises Servers
- Hybrid service
- Servers / Instances must be provisioned and configured ahead of time with the CodeDeploy Agent

## CodePipeline

- Orchestrate the different steps to have the code automatically pushed to production
  - Code => Build => Test => Provision => Deploy
  - Basis for CICD (Continuous Integration & Continuous Delivery)
    Benefits:
- Fullymanaged, compatible with CodeCommit, CodeBuild, CodeDeploy, ElasticBeanstalk, CloudFormation, GitHub, 3rd-party services (GitHub...) & custom plugins...
- Fast delivery & rapid updates

## CodeArtifact

- Software packages depend on each other to be built (also called code dependencies), and new ones are created
- Storing and retrieving these dependencies is called artifact management
- Traditionally you need to setup your own artifact management system
- CodeArtifact is a secure, scalable, and cost-effective artifact management for software development
- Works with common dependency management tools such as Maven, Gradle, npm, yarn, twine, pip, and NuGet
- Developers and CodeBuild can then retrieve dependencies straight from CodeArtifact

## CodeStar

- Unified UI to easily manage software development activities in one place
- “Quick way” to get started to correctly set-up CodeCommit, CodePipeline, CodeBuild, CodeDeploy, Elastic Beanstalk, EC2, etc...
- Can edit the code ”in-the-cloud” using AWS Cloud9

## Cloud9

- AWS Cloud9 is a cloud IDE (Integrated Development Environment) for writing, running and debugging code
- AWS Cloud9 also allows for code collaboration in real-time (pair programming)

## X-Ray

Debugging in Production

- Troubleshooting performance (bottlenecks)
- Understand dependencies in a microservice architecture
- Pinpoint service issues
- Review request behavior
- Find errors and exceptions
- Are we meeting time SLA?
- Where I am throttled?
- Identify users that are impacted
