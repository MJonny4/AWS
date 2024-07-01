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

