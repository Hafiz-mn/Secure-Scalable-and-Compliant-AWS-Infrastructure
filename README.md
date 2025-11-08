# Secure, Scalable, Cost-Optimized, and Compliant AWS Infrastructure


## Objective

To design and implement a multi-region AWS infrastructure that ensures security, scalability, compliance, and cost-efficiency while maintaining full observability.


### Step-1   Networking and Security
* Create VPC with public and private subnets across 2 AZs.For this VPC 2 public and 2 private subnets were created
<p align="center">
<img width="700" height="556" alt="VPC" src="https://github.com/user-attachments/assets/c0ec770f-97f2-4422-95d3-9a352a261b37" /><br>
</p>

* Attach Internet Gateway (public) and NAT Gateway (private).<br>

<p align="center">
<img width="700" height="459" alt="Internet Gateway" src="https://github.com/user-attachments/assets/73e62ecd-10cc-43d3-9251-d176bdfe0876" /><br>
</p>








<img width="700" height="649" alt="NAT Gateway" src="https://github.com/user-attachments/assets/782aa34f-9af4-4f0b-8f73-17ca45240238" />

### 

* Enable VPC Flow Logs and CloudWatch logging for audits in the VPC settings.<br>

<img width="700" height="804" alt="Flow LOG" src="https://github.com/user-attachments/assets/f085d45d-a6f9-43e0-987b-f79cb8a17490" />

###

* Apply NACLs and Security Groups with least privilege.<br>


<img width="700" height="583" alt="NACL" src="https://github.com/user-attachments/assets/a18bce8e-2a5b-4f3e-b1ae-72de002ea229" /><br>


<img width="700" height="372" alt="part2" src="https://github.com/user-attachments/assets/e73cc4ce-3e76-48dc-b8f6-c8a4e6d43838" /><br>


<img width="700" height="336" alt="part3" src="https://github.com/user-attachments/assets/aec6368e-1b10-47ff-a161-0c23e4cca85d" /><br>

### Step-2   Identity & Access Management
 Here we implement secure identity and access practices for compliance.

* Created IAM users, groups, and roles following the least privilege principle.
  ###
<p align="center">  
<img width="700" height="370" alt="Iam_groups" src="https://github.com/user-attachments/assets/92e6453d-135d-444a-92b5-13fcf16f4dab" />
<img width="700" height="578" alt="IAM USERS" src="https://github.com/user-attachments/assets/62c8686d-48b0-4311-9119-9227e0063330" />
</p>

* Then enforced MFA for IAM users for extra security.
  ###
  <img width="700" height="393" alt="MFA" src="https://github.com/user-attachments/assets/a415d872-ee47-4ddd-8ca6-a0711a28a56c" />

* Implemented role-based access control (RBAC) for developers, ops, and auditors.



