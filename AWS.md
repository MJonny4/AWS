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

## AWS Budget Setup
- Budgets: set budget limits for AWS services
- Billing and Cost Management Dashboard: set up budgets