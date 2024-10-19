# Important AWS Services

- VPC: networking service for creating own private isolated network in cloud. (subnets, route tables, internet gateway, nat gateway, etc.)
- EC2: service for creating virtual servers with required configurations. (load balancing, auto scaling group, security groups, keypairs, etc.)
- S3:
- Amazon RDS: managed service to setup own DBs. Supports most used DBs.
- IAM: user groups and rules

# CICD Services (fully managed)

- CodeCommit: github for AWS
- CodeBuild: compiles code, runs build steps(test, lint, etc.) and outputs software files ready to deploy
- CodeDeploy:
  - Automates software deployment on service like EC2, lambda, fargate.
  - Helps in automate deployments, reduce downtime, and ensure deployment consistency.
- CodePipeline: helps in automating deployment pipelines

# Networking Services

- VPC:
- Route 53:
  - DNS service
  - Can register domain names
  - Create and configure DNS records to route traffic to EC2, load balancers, S3 bucket, etc.
  - Setup health checks
  - Failover routing policies
- Elastic Load Balancer

# Database Services

- Amazon RDS: to create our own SQL databases
- Amazon DynamoDB: NoSQL, fast and scalable
- Amazon ElasticCache:
  - In memory DB for storing frequently accessed data
  - Reduces DB reads hence reducing load on DB

# IaC Services

- CloudFormation:
  - Lets you manage AWS services in the form of code
  - Supports 3rd party tools like Terraform

# Container Services

- Amazon ECR:
  - Store and deploy docker containers
  - DockerHub for AWS
- Amazon ECS:
  - Deploy and manage images from Amazon ECR
- Amazon EKS:
  - Fully managed kubernetes service

# Monitoring Services

- CloudWatch: collect and track metrics, log files, setup alert alarms for thresholds
- CloudTrail:
  - Helps in logging all API calls made in the AWS account
  - Monitor AWS resources and detect security incidents
  - Monitors creating, modifying and deleting of resources
  - Helps in tracking and troubleshooting issues and security breaches

# Automation Services

- Lambda:
  - Helps in running certain workflows/code when ever an event occurs
  - Events could be adding data to S3 bucket, creating other resources, etc.
- AWS Systems Manager:
  - Helps in automating patching, software deployment and collecting data for future reference
  - Manages infrastucture at scale
- ElasticBeanStalk:
  - Fully managed service
  - Push code and it automatically handles deployment, provisioning servers, load balancing, autoscaling, etc.

# Security Services

- KMS:
  - Key Management Service
  - Creates and controls encryption keys used to encrypt any data on AWS like S3 buckets, DB backups, EBS volumes, etc.
- Secrets Manager:
  - Storing passwords, DB credentials, API keys, etc.

# Additional Resources

- https://www.youtube.com/watch?v=IF1gMo6P7dk

---

# AWS Services:

- EC2 instances
- Elastic Load Balancer
- Launch Configurations
- Auto Scaling Groups
- Elastic IPs
- Security Groups
- EBS Volumes
- Key Pairs
- ECS environments (cluster, service, task def, ECR)
- Elastic Beanstalk applications & environments
- AWS Lambda functions
- S3 files & buckets
- RDS database
- DynamoDB tables & indexes
- ElastiCache cluster
- Route53
- API Gateway
- Kinesis Streams
- SNS Topics
- SQS Queues
- CodeCommit
- CodeBuild
- CodePipeline
- CloudWatch Logs
- CloudWatch Metrics
- CloudWatch Dashboards
- CloudWatch Alerts
- CloudWatch Rules
- CloudFormation Stacks
- SSM Parameter Store
- IAM User / Groups / Roles / Policies
