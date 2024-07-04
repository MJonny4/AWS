# EC2 = Elastic Compute Cloud = Infrastructure as a Service (IaaS)
- Renting virtual machines (EC2 instances) in the cloud
- Storing data on virtual drives (EBS)
- Distributing load across machines (ELB)
- Scaling the services using an auto-scaling group (ASG)

## EC2 Instances
- OS: Windows, Linux, Mac OS
- CPU: How much compute power and how many cores
- RAM: How much memory
- Storage: How much disk space
  - network-attached (EBS)
  - hardware (instance store)
- Network: How much network bandwidth
- Firewall rules: security groups
- Bootstrapping: running commands when the machine starts

### EC2 User Data
- Bootstrapping: running commands when the machine starts
  - Install software
#!/bin/bash
# Use this for your user data (script)
# install httpd (Linux 2 version)
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html

### EC2 Instance Types
https://instances.vantage.sh/

### Security Groups
- Virtual firewall that controls traffic to your EC2 instances
- All inbound traffic is blocked by default
- All outbound traffic is allowed
- Changes to security groups take effect immediately
- You can have many security groups attached to EC2 instances
- Security groups are stateful: if you allow inbound, the response is automatically allowed
- You can specify allow rules, but not deny rules
- It is a good practice to maintain one separate security group for SSH access
- One instance with 1 security can attach other security groups and allow different instances to communicate


### Placement Groups
- Cluster: low network latency, high network throughput
- Spread: can span across availability zones, critical instances
- Partition: large distributed and replicated workloads

### Elastic Network Interfaces (ENI)
- Logical component in a VPC that represents a virtual network card 
- You can attach multiple ENIs to instances
- Bound to a specific subnet
- Primary ENI is created with an instance

### Elastic Block Store (EBS)
- Network drive you can attach to your instances while they run
- Analogy: network-attached USB stick
- Locked to an AZ
- size in GBs, provisioned IOPS (input/output operations per second), type of EBS volume

### Amazon EFS (Elastic File System)
- Managed NFS (Network File System) that can be mounted on many EC2 instances

### Vertical Scaling
- Increase the size of the instance
- From: t2.micro -> t2.small -> t2.medium -> t2.large

### Horizontal Scaling
- Increase the number of instances/systems handling the load

### High Availability
- Running your application in at least 2 data centers (availability zones)
- Multi-AZ: for databases

### Load Balancer
- Distribute incoming network traffic across multiple servers
- Health checks: check the health of the instances

### Network Load Balancer (NLB)
- High-throughput, low-latency
- Handle millions of requests per second
- Forward TCP traffic to your instances

### Application Load Balancer (ALB)
- Best suited for load balancing of HTTP and HTTPS traffic
- Operates at the request level (layer 7)
- Intelligent routing decisions based on different factors

### Cross-Zone Load Balancing
- Distribute incoming requests evenly across all instances in all AZs