# AWS Certified Cloud Practitioner CLF-C02

The AWS Certified Cloud Practitioner certification is one of the most popular certifications in cloud computing today. Cloud adoption is growing at an ever increasing rate and a shortage of skilled staff is driving up the value of cloud certifications. It’s important for personnel in many areas of the business to understand the cloud value proposition and how it can drive business value.

## Shared Responsibility Model

The AWS shared responsibility model defines customer/AWS responsibilities.

![Shared Responsibility Model](assets/shared-responsability-model.jpeg)

- AWS are responsible for “Security of the Cloud”
  - AWS is responsible for protecting the infrastructure that runs all of the services offered in the AWS Cloud
  - This infrastructure is composed of the hardware, software, networking, and facilities that run AWS Cloud services
- Customers are responsible for “Security in the Cloud”
  - For EC2 this includes network level security, operating system patches and updates, IAM user access management, and client and server-side data encryption

[Docs Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)

## AWS Pricing

### Pay-as-you-go

With AWS you only pay for what use, helping your organization remain agile, responsive and always able to meet scale demands.

Pay-as-you-go pricing allows you to easily adapt to changing business needs without overcommitting budgets and improving your responsiveness to changes.

### Flat rate

Flat-rate plans combine multiple AWS services into one price with no overage charges, giving you the reliability and security of AWS with simple monthly billing. As your needs grow, you can easily upgrade to plans with more capabilities and larger usage allowances.

### Save when you commit

For AWS Compute and AWS Machine Learning, Savings Plans offer savings over On-Demand in exchange for a commitment to use a specific amount (measured in $/hour) of an AWS service or a category of services, for a one- or three-year period.

### Pay less by using more

With AWS, you can get volume based discounts and realize important savings as your usage increases. For services such as S3 and data transfer OUT from EC2, pricing is tiered, meaning the more you use, the less you pay per GB. In addition, data transfer IN is always free of charge. As a result, as your AWS usage needs increase, you benefit from the economies of scale that allow you to increase adoption and keep costs under control.

[Docs Pricing](https://aws.amazon.com/pricing/)

## Identity and Access Management (IAM)

AWS Identity and Access Management (IAM) is a web service for securely controlling access to AWS services. With IAM, you can centrally manage users, security credentials such as access keys, and permissions that control which AWS resources users and applications can access.

- **Identities**

When you create an AWS account, you begin with one sign-in identity called the AWS account root user that has complete access to all AWS services and resources. AWS strongly recommend that you don't use the root user for everyday tasks.

- **Access management**

After a user is set up in IAM, they use their sign-in credentials to authenticate with AWS. Authentication is provided by matching the sign-in credentials to a principal (an IAM user, AWS STS federated principal, IAM role, or application) trusted by the AWS account.

### AWS Security Token Service (STS)

AWS provides AWS Security Token Service (AWS STS) as a web service that enables you to request temporary, limited-privilege credentials for users. This guide describes the AWS STS API. For more information, see [Temporary Security Credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html) in the IAM User Guide.

#### IAM Users

An IAM user is an identity within your AWS account that has specific permissions for a single person or application. For more information, see [IAM users](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users.html).

#### IAM Groups

An IAM user group is an identity that specifies a collection of IAM users. For more information, see [User groups](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html).

#### IAM Roles

An IAM role is an identity within your AWS account that has specific permissions. It's similar to an IAM user, but isn't associated with a specific person. For more information, see [IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html).

#### IAM Policies

IAM policies define permissions for an action regardless of the method that you use to perform the operation. For example, if a policy allows the `GetUser` action, then a user with that policy can get user information from the AWS Management Console, the AWS CLI, or the AWS API.

##### Policy types

The following policy types, listed in order from most frequently used to less frequently used, are available for use in AWS.

- **Identity-based policies** – Attach *managed* and *inline* policies to IAM identities (users, groups to which users belong, or roles). Identity-based policies grant permissions to an identity.
- **Resource-based policies** – Attach inline policies to resources. The most common examples of resource-based policies are Amazon S3 bucket policies and IAM role trust policies. Resource-based policies grant permissions to the principal that is specified in the policy. Principals can be in the same account as the resource or in other accounts.
- **Permissions boundaries** – Use a managed policy as the permissions boundary for an IAM entity (user or role). That policy defines the maximum permissions that the identity-based policies can grant to an entity, but does not grant permissions. Permissions boundaries do not define the maximum permissions that a resource-based policy can grant to an entity.
- **AWS Organizations SCPs** – Use an AWS Organizations service control policy (SCP) to define the maximum permissions for IAM users and IAM roles within accounts in your organization or organizational unit (OU). SCPs limit permissions that identity-based policies or resource-based policies grant to IAM users or IAM roles within the account. SCPs do not grant permissions.
- **AWS Organizations RCPs** – Use an AWS Organizations resource control policy (RCP) to define the maximum permissions for resources within accounts in your organization or organizational unit (OU). RCPs limit permissions that identity-based and resource-based policies can grant to resources in accounts within your organization. RCPs do not grant permissions.
- **Access control lists (ACLs)** – Use ACLs to control which principals in other accounts can access the resource to which the ACL is attached. ACLs are similar to resource-based policies, although they are the only policy type that does not use the JSON policy document structure. ACLs are cross-account permissions policies that grant permissions to the specified principal. ACLs cannot grant permissions to entities within the same account.
- **Session policies** – Pass advanced session policies when you use the AWS CLI or AWS API to assume a role or a federated user. Session policies limit the permissions that the role or user's identity-based policies grant to the session. Session policies limit permissions for a created session, but do not grant permissions.

#### Security best practices in IAM

- Require human users to use federation with an identity provider to access AWS using temporary credentials
- Require workloads to use temporary credentials with IAM roles to access AWS
- Require multi-factor authentication (MFA)
- Update access keys when needed for use cases that require long-term credentials
- Follow best practices to protect your root user credentials
- Apply least-privilege permissions
- Get started with AWS managed policies and move toward least-privilege permissions
- Use IAM Access Analyzer to generate least-privilege policies based on access activity
- Regularly review and remove unused users, roles, permissions, policies, and credentials
- Use conditions in IAM policies to further restrict access
- Verify public and cross-account access to resources with IAM Access Analyzer
- Use IAM Access Analyzer to validate your IAM policies to ensure secure and functional permissions
- Establish permissions guardrails across multiple accounts
- Use permissions boundaries to delegate permissions management within an account

The Access key is associated with an IAM accout. The access key will use the **permission** assigned to the IAM account.
