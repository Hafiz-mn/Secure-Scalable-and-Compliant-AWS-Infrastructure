# Secure, Scalable, Cost-Optimized, and Compliant AWS Infrastructure


## Objective

Design and implement a multi-region AWS infrastructure that ensures:
* Security & Compliance (IAM, Encryption, WAF, CloudTrail).
* Scalability & High Availability (ALB, Auto Scaling, Multi-AZ).
* Cost Optimization (S3 lifecycle, NAT control, CloudWatch metrics).
* Observability (Logs, Metrics, GuardDuty, Security Hub)

  
### Step-1: Networking and Security
*VPC Setup: Created one VPC with 2 public and 2 private subnets across 2 Availability Zones.
<p align="center">
<img width="700" height="556" alt="VPC" src="https://github.com/user-attachments/assets/c0ec770f-97f2-4422-95d3-9a352a261b37" /><br>
</p>

* Gateways: Configured Internet Gateway (public) and NAT Gateway (private) for secure routing.

<p align="center">
<img width="700" height="459" alt="Internet Gateway" src="https://github.com/user-attachments/assets/73e62ecd-10cc-43d3-9251-d176bdfe0876" /><br>
</p>







<p align="center">
<img width="700" height="649" alt="NAT Gateway" src="https://github.com/user-attachments/assets/782aa34f-9af4-4f0b-8f73-17ca45240238" />
</p>

* Flow Logs: Enabled VPC Flow Logs and CloudWatch logging for auditing network traffic.
<p align="center">
<img width="700" height="804" alt="Flow LOG" src="https://github.com/user-attachments/assets/f085d45d-a6f9-43e0-987b-f79cb8a17490" />
</p>

* Access Control: Applied NACLs and Security Groups with least privilege principle.

<p align="center">
<img width="700" height="583" alt="NACL" src="https://github.com/user-attachments/assets/a18bce8e-2a5b-4f3e-b1ae-72de002ea229" /><br>


<img width="700" height="372" alt="part2" src="https://github.com/user-attachments/assets/e73cc4ce-3e76-48dc-b8f6-c8a4e6d43838" /><br>


<img width="700" height="336" alt="part3" src="https://github.com/user-attachments/assets/aec6368e-1b10-47ff-a161-0c23e4cca85d" /><br>
</p>

### Step-2: Identity & Access Management(IAM

* Users, Groups & Roles: Created IAM identities and roles based on function (Dev, Ops, Audit).
  
<p align="center">  
<img width="700" height="370" alt="Iam_groups" src="https://github.com/user-attachments/assets/92e6453d-135d-444a-92b5-13fcf16f4dab" />
<img width="700" height="578" alt="IAM USERS" src="https://github.com/user-attachments/assets/62c8686d-48b0-4311-9119-9227e0063330" />
</p>

* Enforced MFA, RBAC, and custom policies for privilege control.
 
  <img width="700" height="393" alt="MFA" src="https://github.com/user-attachments/assets/a415d872-ee47-4ddd-8ca6-a0711a28a56c" />

* Implemented role-based access control (RBAC) for developers, ops, and auditors.

<p align="center">
<img width="700" height="733" alt="Devloper_permission" src="https://github.com/user-attachments/assets/e57ee76b-2164-4170-93ca-669d4939c854" />

<img width="700" height="753" alt="DevOps_permission" src="https://github.com/user-attachments/assets/66935a1b-0c5f-4d57-9615-b7a9b47f616f" />

<img width="700" height="763" alt="auditor_permission" src="https://github.com/user-attachments/assets/507d7aa5-5df0-41e6-9aa2-994b469cd84b" />
</p>

### Step-3: Secure Application Deployment (EC2 + ALB)
* Deployed EC2 instances in multiple AZs behind an Application Load Balance
  
<p align="center">
<img width="700" height="749" alt="Instances" src="https://github.com/user-attachments/assets/4cccb397-8e7b-4aa8-8c16-9b13a5d05d83" />
 
<img width="1580" height="722" alt="Load Balan_1" src="https://github.com/user-attachments/assets/16041298-26ce-4a33-9a4b-d2495dc767c7" />
</p>

* Configured Auto Scaling Group (min=2, max=5) for elasticity.
<p align="center">
<img width="700" height="746" alt="Autoscaling" src="https://github.com/user-attachments/assets/60a3b68e-b546-4d7d-aa38-2fa336c49888" />
</p>

* Enabled CloudWatch Alarms for CPU and latency metrics.
<p align="center">
<img width="700" height="600" alt="Error_Connection" src="https://github.com/user-attachments/assets/830b7009-6f41-4495-836d-ec9464dacbe6" />
<img width="700" height="593" alt="cpu alarm" src="https://github.com/user-attachments/assets/59e8bf8d-7a30-494c-850a-5c10c9e0b39a" />
<img width="700" height="599" alt="cpu alaram part 2" src="https://github.com/user-attachments/assets/342757ed-0502-45fc-b496-0bf45873543e" />
<img width="700" height="540" alt="Alarms" src="https://github.com/user-attachments/assets/0b37cbe0-4b4f-477b-a787-57fd066d87fa" />
</p>

* Applied IAM roles and EBS volume encryption with KMS keys.
<p align="center">
<img width="700" height="804" alt="Encrypted volume" src="https://github.com/user-attachments/assets/b1ec19fc-fe20-41db-a9ad-b2cef1b91707" />

<img width="700" height="809" alt="KMS" src="https://github.com/user-attachments/assets/db58e303-3da3-4966-ae91-cc9dba454ec3" />


<img width="700" height="747" alt="kms policy" src="https://github.com/user-attachments/assets/21a8f475-b675-4430-9190-6df53ee66061" />
</p>
### Step-4: S3 & Storage Compliance
Here We configure Amazon S3 to securely store application static assets and backups while ensuring compliance with data protection standards.

* Created S3 buckets with:
    * SSE-KMS encryption
    * Versioning & lifecycle policies
    * Strict bucket policies (EC2-only access)  
* Enabled CloudTrail and Macie for auditing and sensitive data detection.
  
<p align="center">
<img width="700" height="818" alt="part3" src="https://github.com/user-attachments/assets/795817bd-b36d-4a59-aefd-1e2197f18414" />
<img width="700" height="816" alt="part2" src="https://github.com/user-attachments/assets/5262cb9d-34ce-417a-8e94-89eeb7f53c5f" />
<img width="700" height="621" alt="part 1" src="https://github.com/user-attachments/assets/a30cf9ae-ce8e-4b0f-8290-7cb50258dca7" />
<img width="700" height="804" alt="part4" src="https://github.com/user-attachments/assets/3d140f51-0025-424c-b4df-710ec60306dc" />
</p>

### Step-5: Global Traffic & High Availability
* Deployed across us-east-1 and eu-north-1 for cross-region redundancy.
  
* Configured Route 53 latency-based routing + failover policy for intelligent DNS response.
<p align="center">
<img width="700" height="747" alt="latency record 1" src="https://github.com/user-attachments/assets/7016fe32-ccb6-4796-89aa-da97220593a4" />
<img width="700" height="808" alt="hosted zone" src="https://github.com/user-attachments/assets/d422c533-2c72-43e8-8011-964313f68659" />
<img width="700" height="681" alt="latency record 2" src="https://github.com/user-attachments/assets/04005929-8722-4546-8c1b-f44c1b3a3139" />
</p>

* Integrated CloudFront CDN + AWS WAF for security and global caching.
<p align="center">
<img width="700" height="375" alt="cloudfront" src="https://github.com/user-attachments/assets/44455855-73db-4808-ad07-1563e602c625" />

<img width="700" height="535" alt="waf" src="https://github.com/user-attachments/assets/28bcd9f1-9dc5-4b6c-a9ce-aa19710899e6" />
</p>

### Step-6: Monitoring, Logging & Audit Trails
* Enabled AWS CloudTrail, GuardDuty, and Security Hub for centralized threat visibility.
* Integrated logs with CloudWatch Metrics and custom alerts
<p align="center">
<img width="700" height="796" alt="Guardduty" src="https://github.com/user-attachments/assets/d0fc3210-eb7c-4cd5-a810-b20cf9fd664e" />

<img width="700" height="654" alt="cloudtrail events" src="https://github.com/user-attachments/assets/33276163-52bb-48c9-bb03-c933be5a989f" />
<img width="700" height="496" alt="cloudtrail" src="https://github.com/user-attachments/assets/f248641b-659a-4ee0-ac5a-f19798eded5d" />
</p>

