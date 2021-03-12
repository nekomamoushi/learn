# Identity and Access Management

AWS IAM is a web service that helps you securely control access to AWS resources.
It's a Global service.

IAM manage:

- Users.
- Groups.
- Access policies.
- Roles.
- User credentials.
- User password policies.
- Multi-factor authentication (MFA).
- API keys for programmatic access (CLI).

### How can users access AWS ?

- AWS Management Console (_protected by password + MFA_)
- AWS Command Line Interface (_protected by access keys_)
- AWS Software Developer Kit (_protected by access keys_)
- Access Keys are generated through the AWS Console (_users manage their own access keys_)

## Users & Groups

- Root account created by default, shouldn’t be used or shared
- Users are people within your organization, and can be grouped
- Groups only contain users, not other groups
- Users don’t have to belong to a group, and user can belong to multiple groups
- Up to 5000 users per AWS account.

## Roles (for Services)

- Some AWS service will need to perform actions on your behalf
- To do so, we will assign permissions to AWS services with IAM Roles
- Common roles:
  - EC2 Instance Roles
  - Lambda Function Roles
  - Roles for CloudFormation

## Policies

- Users or Groups can be assigned JSON documents called policies.
- These policies define the permissions of the users.
- Documents that define permissions and can be applied to users, groups and roles.
- Written in JSON (key value pair that consists of an attribute and a value).
- All permissions are implicitly denied by default.
- The most restrictive policy is applied.

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "ec2:Describe*",
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": "elasticloadbalancing:Describe*",
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "cloudwatch:ListMetrics",
                "cloudwatch:GetMetricStatistics",
                "cloudwatch:Describe*"
            ],
            "Resource": "*"
        }
    ]
```

### Multi Factor Authentication (MFA)

- Users have access to your account and can possibly change configurations or delete resources in your AWS account
- You want to protect your Root Accounts and IAM users
- MFA = password you know + security device you own

MFA devices options in AWS

- Virtual MFA device
- Universal 2nd Factor (U2F) Security Key
- Hardware Key Fob MFA Device
- Hardware Key Fob MFA Device for AWS GovCloud (US)

### IAM Security Tools

**IAM Credentials Report (account-level)**

- a report that lists all your account's users and the status of their various
  credentials

**IAM Access Advisor (user-level)**

- Access advisor shows the service permissions granted to a user and when those services were last accessed.
- You can use this information to revise your policies.

### IAM Best Practices

- Don’t use the root account except for AWS account setup
- Assign users to groups and assign permissions to groups
- Create a strong password policy
- Use and enforce the use of Multi Factor Authentication (MFA)
- Create and use Roles for giving permissions to AWS services
- Use Access Keys for Programmatic Access (CLI / SDK)
- Audit permissions of your account with the IAM Credentials Report
- Never share IAM users & Access Keys
