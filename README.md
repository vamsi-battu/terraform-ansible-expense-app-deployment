#  End-to-End Expense Application Deployment using Terraform and Ansible

##  Project Overview
This project demonstrates an end-to-end DevOps workflow by integrating Terraform and Ansible to provision infrastructure and deploy a multi-tier Expense application.

Terraform is used to create cloud infrastructure, while Ansible (role-based architecture) is used for configuration management and application deployment.

This approach follows Infrastructure as Code (IaC) and Configuration Management best practices to ensure scalable, consistent, and automated deployments.

---

##  Objectives

- Provision infrastructure using Terraform
- Deploy application using Ansible roles
- Implement end-to-end automation
- Ensure reusable and modular design
- Simulate real-world DevOps workflow

---

##  Tech Stack

- Infrastructure as Code: Terraform
- Configuration Management: Ansible
- Language: HCL (Terraform), YAML (Ansible)
- Cloud Platform: AWS
- Application: Expense Application
- Version Control: Git

---

##  Architecture

### Infrastructure Layer (Terraform)
- VPC
- Subnets (public/private)
- EC2 instances
- Security Groups
- Internet Gateway

### Configuration & Deployment Layer (Ansible)
- Role-based automation:
  - frontend role (Nginx)
  - backend role (Node.js)
  - database role (MySQL)

Terraform provisions infrastructure and passes instance details to Ansible for further configuration.

---

##  Repository Structure
├── terraform/
│ ├── main.tf
│ ├── variables.tf
│ └── outputs.tf
├── ansible/
│ ├── roles/
│ │ ├── frontend/
│ │ ├── backend/
│ │ └── database/
│ ├── inventory
│ └── playbooks/
├── README.md


---

##  Workflow

1. Provision infrastructure using Terraform  
2. Terraform creates EC2 instances and networking components  
3. Extract instance details (IP addresses)  
4. Configure Ansible inventory dynamically or manually  
5. Execute Ansible playbooks  
6. Deploy application using role-based architecture  

---

##  Key Features

- End-to-end automation (infra + deployment)
- Role-based Ansible architecture
- Declarative infrastructure provisioning
- Modular and reusable design
- Scalable multi-tier deployment

---

##  Engineering Highlights

### Tool Integration
Combines Terraform (IaC) and Ansible (CM) for complete automation.

### Modularity
Uses Ansible roles for reusable and maintainable configuration.

### Scalability
Supports multi-tier architecture deployment.

### Consistency
Ensures identical infrastructure and configuration across runs.

---

##  Execution Steps

### Step 1: Provision Infrastructure
```bash
cd terraform
terraform init
terraform apply

Step 2: Configure Inventory
cd ansible
nano inventory
Step 3: Test Connectivity
ansible all -m ping -i inventory
Step 4: Deploy Application
ansible-playbook -i inventory playbooks/main.yml


Application Flow
User accesses frontend (Nginx)
Frontend routes requests to backend
Backend processes logic
Backend communicates with database
Response is returned to user


Challenges & Solutions
Challenge	Solution
Terraform to Ansible integration	Used outputs for inventory mapping
Managing multiple servers	Used role-based architecture
SSH connectivity issues	Configured key-based authentication
Deployment consistency	Used idempotent Ansible playbooks


Future Enhancements
Implement dynamic inventory using Terraform outputs
Add CI/CD pipeline integration (Jenkins)
Use remote backend (S3 + DynamoDB)
Add monitoring and logging setup
Implement multi-environment support


Key Learnings
Terraform and Ansible together enable complete automation
Role-based design improves scalability and maintainability
Infrastructure as Code ensures consistency
End-to-end automation reduces manual intervention
