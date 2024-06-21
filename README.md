# AWS
- Regions: Clusters of data centers, AWS is region-scoped
- How to choose and AWS Region: 
  - Compliance: legal requirements
  - Proximity: latency (reduce latency)
  - Available services: not all services are available in all regions
  - Pricing: different regions have different pricing
- Availability Zones: Each regions has multiple availability zones, each AZ is a data center (min 3, max 6)
  - AZs are isolated from each other, but connected with high-bandwidth, low-latency networking
  - Fault tolerance: if one AZ goes down, the other AZs are still operational
Points of presence (Edge Locations): CDN endpoints for CloudFront, used for caching content
Aws has Global Services: IAM,  Route 53, CloudFront, WAF
Most Aws are regional: S3, EC2, RDS, Redshift

- AWS Global Infrastructre: Check availability of services in different regions

### IAM
- Identity and Access Management
- Root Account: created when you create an AWS account, has full access to all AWS services
- IAM Users: can be created, each user can have its own password and permissions
- Groups: collection of users, each user in the group inherits the permissions of the group
- Group can not have groups inside but one user can be in multiple groups

- IAM Policies: JSON documents that define permissions
- Apply lest privilege principle: give only the permissions needed to perform a task

#### How to create an IAM User & Group