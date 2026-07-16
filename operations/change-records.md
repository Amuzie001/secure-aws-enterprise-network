# AWS Infrastructure Change Records

## CHG-AWS-002 — Create VPC Network Foundation

| Field | Details |
|---|---|
| Change ID | CHG-AWS-002 |
| Project | Secure AWS Enterprise Network |
| Change type | Standard infrastructure change |
| Description | Create a custom VPC, four subnets, an Internet Gateway and three custom route tables |
| Business justification | Establish a segmented, multi-Availability Zone AWS network for public and private workloads |
| Planned VPC CIDR | 10.20.0.0/16 |
| Risk level | Medium |
| Primary risk | Incorrect CIDR allocation or route-table association could cause connectivity problems |
| Implementation method | AWS Management Console |
| Validation | Review subnet CIDRs, Availability Zones, routes and explicit subnet associations |
| Rollback plan | Disassociate and delete route tables, detach and delete the Internet Gateway, delete subnets and delete the VPC |
| Status | In progress |
