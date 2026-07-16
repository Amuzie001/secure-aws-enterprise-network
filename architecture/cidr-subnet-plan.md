# CIDR and Subnet Allocation Plan

## VPC

| Resource | CIDR | Region | Purpose |
|---|---|---|---|
| saen-vpc-lab | 10.20.0.0/16 | us-east-1 | Secure AWS enterprise network lab |

## Active Subnets eu-west-2a

| Subnet | CIDR | Availability Zone | Tier | Route Table |
|---|---|---|---|---|
| saen-subnet-public-a | 10.20.0.0/24 | eu-west-2a | Public | saen-rt-public |
| saen-subnet-public-b | 10.20.1.0/24 | eu-west-2b | Public | saen-rt-public |
| saen-subnet-private-a | 10.20.10.0/24 | eu-west-2a | Private application | saen-rt-private-a |
| saen-subnet-private-b | 10.20.11.0/24 | eu-west-2b | Private application | saen-rt-private-b |

## Reserved Address Space

| CIDR range | Proposed purpose |
|---|---|
| 10.20.20.0/24 - 10.20.21.0/24 | Private database tier |
| 10.20.30.0/24 - 10.20.31.0/24 | Management tier |
| 10.20.40.0/24 - 10.20.41.0/24 | Container workloads |
| Remaining VPC ranges | Future expansion |

## Design Decisions

- Subnets are distributed across two Availability Zones.
- Public and private workloads use separate subnet ranges.
- Public subnets route internet traffic through the Internet Gateway.
- Private subnets currently have no default internet route.
- Every project subnet is explicitly associated with a custom route table.
- Public IPv4 auto-assignment remains disabled by default.
