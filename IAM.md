## IAM
- Identity and Access Management
- Root Account: created when you create an AWS account, has full access to all AWS services
- IAM Users: can be created, each user can have its own password and permissions
- Groups: collection of users, each user in the group inherits the permissions of the group
- Group can not have groups inside but one user can be in multiple groups

- IAM Policies: JSON documents that define permissions
- Apply lest privilege principle: give only the permissions needed to perform a task

### How to create an IAM User & Group

- Policies attached to group or inline attached to user
  - Version: "2012-10-17"
  - Id: "Policy123" (optional)
  - Statement: 
    - Effect: "Allow" or "Deny"
    - Action: "s3:*"
    - Resource: "*" (all resources)
    - Condition: {"IpAddress": {"aws:SourceIp": "
    - Principal: {"AWS": "arn:aws:iam::123456789012:user/username"}

- Specific Policies
- Password Policy: set password requirements
  - Virtual MFA: use Google Authenticator or Authy (phone only)
  - Universal 2nd Factor (U2F) Security Key: physical key
  - Hardware Key Fob MFA: physical key

- How to access AWS:
  - AWS Management Console: web-based user interface
  - AWS Command Line Interface (CLI): command line tool protected by access keys
  - AWS Software Development Kits (SDKs): libraries for programming languages
- ACCESS KEY ID ~= USERNAME
- SECRET ACCESS KEY ~= PASSWORD

- IAM Roles: used to delegate permissions to entities that you trust
  - Cross-account access: allow access to resources in another account
  - Service roles: used by AWS services to perform actions on your behalf
  - Identity providers: allow federated users to assume roles

- IAM Security Tools:
  - IAM Credentials Report: report that lists all your account's users and the status of their various credentials
  - IAM Access Advisor: shows the service permissions granted to a user and when those services were last accessed
  - IAM Access Analyzer: analyzes resource policies to help administrators and security teams identify resources that can be accessed from outside an AWS account 
  
#### Summary
- Users: individual accounts for people
- Groups: collection of users
- Policies: permissions attached to users or groups
- Roles: used to delegate permissions to entities that you trust
- Security: enable MFA, password policies, and monitor access
- AWS CLI: command line tool protected by access keys
- AWS SDKs: libraries for programming languages
- Access Keys: access AWS programmatically
- Audit: IAM Credentials Report, IAM Access Advisor, IAM Access Analyzer