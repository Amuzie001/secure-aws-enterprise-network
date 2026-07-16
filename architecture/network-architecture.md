# Secure AWS Network Architecture

```mermaid
flowchart TB
    Internet((Internet))
    IGW[Internet Gateway]

    subgraph VPC["saen-vpc-lab — 10.20.0.0/16"]
        subgraph AZA["Availability Zone A — eu-west-2a"]
            PubA["Public Subnet A<br/>10.20.0.0/24"]
            PrivA["Private Subnet A<br/>10.20.10.0/24"]
        end

        subgraph AZB["Availability Zone B — eu-west-2b"]
            PubB["Public Subnet B<br/>10.20.1.0/24"]
            PrivB["Private Subnet B<br/>10.20.11.0/24"]
        end

        PublicRT["Public Route Table<br/>0.0.0.0/0 → Internet Gateway"]
        PrivateRTA["Private Route Table A<br/>Local route only"]
        PrivateRTB["Private Route Table B<br/>Local route only"]
    end

    Internet --- IGW
    IGW --- PublicRT
    PublicRT --- PubA
    PublicRT --- PubB
    PrivateRTA --- PrivA
    PrivateRTB --- PrivB
