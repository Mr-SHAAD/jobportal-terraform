# 🏗️ JobPortal — Infrastructure as Code

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=7B42BC&center=true&vCenter=true&width=600&lines=Infrastructure+as+Code+with+Terraform;Complete+AWS+Setup+in+One+Command;VPC+%2B+EC2+%2B+S3+%2B+Subnets;Production-Grade+Cloud+Architecture" alt="Typing SVG" />

<br/>

![Terraform](https://img.shields.io/badge/Terraform-v1.5-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-Cloud-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![EC2](https://img.shields.io/badge/EC2-t3.micro-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white)
![S3](https://img.shields.io/badge/S3-Storage-569A31?style=for-the-badge&logo=amazons3&logoColor=white)
![Status](https://img.shields.io/badge/Status-Production%20Ready-success?style=for-the-badge)

<br/>

> **Complete AWS infrastructure provisioned as code — `terraform apply` and everything builds itself**

</div>

---

## 🏛️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                        AWS Cloud                            │
│                                                             │
│  ┌──────────────────────────────────────────────────────┐   │
│  │                VPC  (10.0.0.0/16)                    │   │
│  │                                                      │   │
│  │  ┌──────────────────┐   ┌──────────────────┐         │   │
│  │  │  Public Subnet 1 │   │  Public Subnet 2 │         │   │
│  │  │   us-east-1a     │   │   us-east-1b     │         │   │
│  │  │  10.0.1.0/24     │   │  10.0.2.0/24     │         │   │
│  │  │  ┌────────────┐  │   └──────────────────┘         │   │
│  │  │  │    EC2     │  │                                │   │
│  │  │  │  t3.micro  │  │  ┌──────────────────┐          │   │
│  │  │  └────────────┘  │  │ Private Subnet 1 │          │   │
│  │  └──────────────────┘  │  us-east-1a      │          │   │
│  │                        │  10.0.3.0/24     │          │   │
│  │  ┌──────────────────┐  └──────────────────┘          │   │
│  │  │ Private Subnet 2 │                                │   │
│  │  │  us-east-1b      │  ┌──────────────────┐          │   │
│  │  │  10.0.4.0/24     │  │ Internet Gateway │          │   │
│  │  └──────────────────┘  └──────────────────┘          │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                             │
│  ┌─────────────────┐        ┌─────────────────┐            │
│  │   S3 Bucket     │        │  Security Group │            │
│  │  File Storage   │        │  HTTP + SSH     │            │
│  └─────────────────┘        └─────────────────┘            │
└─────────────────────────────────────────────────────────────┘
```

---

## 📦 Resources Created (10+ AWS Resources)

| # | Resource | Type | Details |
|---|----------|------|---------|
| 1 | VPC | `aws_vpc` | 10.0.0.0/16 |
| 2 | Public Subnet 1 | `aws_subnet` | us-east-1a |
| 3 | Public Subnet 2 | `aws_subnet` | us-east-1b |
| 4 | Private Subnet 1 | `aws_subnet` | us-east-1a |
| 5 | Private Subnet 2 | `aws_subnet` | us-east-1b |
| 6 | Internet Gateway | `aws_internet_gateway` | Public access |
| 7 | Security Group | `aws_security_group` | HTTP + SSH |
| 8 | EC2 Instance | `aws_instance` | t3.micro |
| 9 | S3 Bucket | `aws_s3_bucket` | File storage |
| 10 | Random ID | `random_id` | Unique naming |

---

## 🚀 Quick Start

### Prerequisites
- Terraform v1.0+
- AWS CLI configured
- AWS account with permissions

### Deploy Everything

```bash
# Clone
git clone https://github.com/Mr-SHAAD/jobportal-terraform
cd jobportal-terraform

# Initialize
terraform init

# Preview changes
terraform plan

# Deploy (builds all 10+ resources)
terraform apply -auto-approve
```

### Destroy Everything (Zero Bill)

```bash
terraform destroy -auto-approve
```

---

## 📁 Project Structure

```
jobportal-terraform/
├── 📄 main.tf          # All AWS resources
├── 📄 variables.tf     # Configuration variables
├── 📄 outputs.tf       # Output values (IPs, IDs)
├── 📄 .gitignore       # Ignores tfstate & .terraform
└── 📄 README.md
```

---

## ⚙️ Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `aws_region` | `us-east-1` | AWS deployment region |
| `project_name` | `jobportal` | Used for resource naming |
| `db_password` | `jobportal123!` | Database password |

---

## 📤 Outputs

After `terraform apply`, you get:

```bash
ec2_public_ip  = "x.x.x.x"        # EC2 server IP
s3_bucket_name = "jobportal-xxxx"  # S3 bucket name
vpc_id         = "vpc-xxxxxxxx"    # VPC identifier
```

---

## 💡 Key Concepts Demonstrated

- ✅ **Infrastructure as Code** — entire AWS setup in `.tf` files
- ✅ **Multi-AZ Design** — subnets across 2 availability zones
- ✅ **Network Isolation** — public & private subnet separation
- ✅ **Security** — security groups with minimal access
- ✅ **Reproducible** — same infra every time, zero manual clicks
- ✅ **Cost Control** — `terraform destroy` = zero bill

---

## 👨‍💻 Author

**Mohammad Shaad**

[![GitHub](https://img.shields.io/badge/GitHub-Mr--SHAAD-181717?style=flat&logo=github)](https://github.com/Mr-SHAAD)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mohammad%20Shaad-0077B5?style=flat&logo=linkedin)](https://linkedin.com/in/mohammadshaad)

---

<div align="center">

**⭐ Star this repo if it helped you!**

<sub>Built with ❤️ — Terraform • AWS • VPC • EC2 • S3</sub>

</div>
