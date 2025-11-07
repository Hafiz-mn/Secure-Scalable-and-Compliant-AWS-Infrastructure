# Secure, Scalable, Cost-Optimized, and Compliant AWS Infrastructure


## Objective

To design and implement a multi-region AWS infrastructure that ensures security, scalability, compliance, and cost-efficiency while maintaining full observability.


### Step-1   Networking and Security
* Create VPC with public and private subnets across 2 AZs.
  
<img width="1532" height="556" alt="VPC" src="https://github.com/user-attachments/assets/c0ec770f-97f2-4422-95d3-9a352a261b37" />




* Attach Internet Gateway (public) and NAT Gateway (private).
<img width="1612" height="459" alt="Internet Gateway" src="https://github.com/user-attachments/assets/73e62ecd-10cc-43d3-9251-d176bdfe0876" />



<img width="1594" height="649" alt="NAT Gateway" src="https://github.com/user-attachments/assets/782aa34f-9af4-4f0b-8f73-17ca45240238" />

* Enable VPC Flow Logs and CloudWatch logging for audits.

* Apply NACLs and Security Groups with least privilege.




