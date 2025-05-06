
# AWS Interview Question

#### =============

**What is EC2?**

EC2 (Elastic Compute Cloud) is a service that lets you run virtual machines (servers) in the cloud.

**Example:**
If you're building a web app, you can launch an EC2 instance (like a Linux server), install Node.js on it, and deploy your app there.

#### =============

**What is S3?**

S3 (Simple Storage Service) is a storage service where you can store and retrieve any amount of data anytime.

**Example:**
You can use S3 to store images, videos, or backups of your application. Many websites use S3 to store and deliver static files.

#### =============

**What is an Elastic IP?**

An Elastic IP is a static (unchanging) public IP address that you can assign to EC2 instances.

**Example:**
If your EC2 server crashes and you replace it with a new one, you can move the same Elastic IP to the new instance so users can still reach your service at the same IP.

#### =============

**What is IAM in AWS?**

IAM (Identity and Access Management) lets you control who can do what in your AWS account.

**Example:**
You can create a user "developer" and only allow them to access S3, while the "admin" can access all services.

#### =============

**What is the difference between Security Group and NACL?**

**Security Group:** Works like a firewall at the instance level (attached to EC2).

**NACL (Network ACL):** Works like a firewall at the subnet level.

**Example:**
Security Group can say: “Allow incoming traffic on port 80.”

NACL can say: “Block traffic from IP 1.2.3.4 to this subnet.”

#### =============

**What is Auto Scaling?**

Auto Scaling automatically increases or decreases the number of EC2 instances based on demand.

**Example:**
If 100 users visit your app at once, AWS can automatically launch more EC2 instances to handle traffic. When traffic drops, it removes extra instances to save cost.

#### =============

**What is CloudWatch?**

CloudWatch is a monitoring service that tracks metrics like CPU usage, memory, or logs.

**Example:**
You can use CloudWatch to trigger an alarm if your EC2 instance CPU goes above 80% for more than 5 minutes.

#### =============

**What is Route 53?**

Route 53 is AWS’s DNS (Domain Name System) service used to manage domain names and route traffic.

**Example:**
If you buy a domain like myapp.com, you can use Route 53 to point that domain to your EC2 instance’s IP address.

#### =============

**What is a Load Balancer in AWS?**

A Load Balancer (ELB - Elastic Load Balancer) automatically distributes incoming traffic to multiple servers (EC2 instances) to ensure no server is overloaded.

**Example:**
If you have 3 EC2 servers running a website, a load balancer can send each visitor to a different server based on availability and performance.

#### =============

**What is the difference between EBS(Elastic Block Store) and S3?**

EBS (Elastic Block Store) is a hard drive for EC2 – used for system or app storage.

S3 is object storage – used for storing files like images, videos, or backups.

**Example:**
Use EBS for running a database or OS.

Use S3 to store profile pictures or logs.

#### =============

**What is AWS Lambda?**

Lambda lets you run code without provisioning or managing servers — just upload your code and it runs.

**Example:**
You can trigger a Lambda function when a new file is uploaded to S3 to process or resize the image.

#### =============

**What is S3 Versioning?**

S3 Versioning keeps multiple versions of an object (file) in a bucket, so you can restore old versions if needed.

**Example:**
If you upload a file named report.pdf and later upload a new version, versioning keeps both versions safe.

#### =============

**What is AWS CloudTrail?**

CloudTrail records every API call or action taken in your AWS account, like who created an EC2 instance or who deleted a file.

**Example:**
If someone accidentally deletes an S3 bucket, CloudTrail can show you which user did it and when.

#### =============

**What is the difference between AWS CloudTrail and CloudWatch?**

**CloudTrail:** Logs who did what (auditing and API activity).

**CloudWatch:** Monitors performance and logs (metrics, alarms).

**Example:**
Use CloudWatch to monitor CPU usage; use CloudTrail to trace which user stopped an instance.

#### =============

**What is Elastic Beanstalk?**

Elastic Beanstalk automatically deploys and manages your application — you just upload your code and it handles the rest (EC2, Load Balancer, Auto Scaling, etc.).

**Example:**
Upload a Node.js app and Beanstalk will automatically create the required EC2, security groups, and environment.

#### =============

**What is S3 Lifecycle Policy?**

A Lifecycle Policy automates the movement or deletion of objects in S3 over time.

**Example:**
Move files to cheaper storage (like Glacier) after 30 days, and delete after 1 year to save costs.

#### =============

**What is AWS CloudFront?**

CloudFront is a Content Delivery Network (CDN) that delivers your content faster by caching it at edge locations around the world.

**Example:**
If your S3 bucket has images, CloudFront can deliver them quickly to users in India, US, Europe, etc., from nearby servers.

#### =============

**What is the difference between Scaling Up and Scaling Out?**

**Scaling Up:** Increase resources of a single instance (e.g., more RAM or CPU).

**Scaling Out:** Add more instances to handle load.

**Example:**
Scaling up is upgrading an EC2 instance from t2.medium to t2.large. Scaling out is adding 2 more t2.medium instances.

#### =============

**What is AWS Step Functions?**

Step Functions lets you coordinate multiple AWS services in a workflow, with logic like conditions, retries, and parallel tasks.

**Example:**
A user signs up → trigger Lambda → store data in DynamoDB → send welcome email via SNS — all steps are managed using Step Functions.

#### =============

**What is AWS Secrets Manager?**

Secrets Manager stores and rotates sensitive information like database passwords, API keys, or tokens securely.

**Example:**
Instead of hardcoding DB passwords, you can store them in Secrets Manager and let your app retrieve them securely at runtime.

#### =============

**What is an AWS Service Control Policy (SCP)?**

SCPs are used in AWS Organizations to set permission limits on AWS accounts — even root users can be restricted.

#### =============
