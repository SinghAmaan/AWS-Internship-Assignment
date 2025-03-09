# AWS-Internship-Assignment
# VPC Configuration Documentation

## VPC Details

- **Region:** United States (N. Virginia) - `us-east-1`
- **VPC Name:** `BATCH3-ALB-VPC`
- **IPv4 CIDR:** `10.0.0.0/16`

## Availability Zones & Subnets

| Availability Zone | Identifier | Subnet Name     | Subnet CIDR     |
| ----------------- | ---------- | --------------- | --------------- |
| `us-east-1a`      | A          | `BATCH3--SUB01` | `10.0.101.0/24` |
| `us-east-1b`      | B          | `BATCH3--SUB02` | `10.0.102.0/24` |
| `us-east-1c`      | C          | `BATCH3--SUB03` | `10.0.103.0/24` |

## Internet Connectivity

- The VPC `BATCH3-ALB-VPC` is connected to an **Internet Gateway**:
  - **Internet Gateway Name:** `BATCH3-ALB-IGW`
- This allows public internet access for designated resources.

## Routing Table

- **Routing Table Name:** `BATCH3-ALB-ROUTE-TABLE`
- **Subnet Associations:**
  - `BATCH3--SUB01` (`us-east-1a`)
  - `BATCH3--SUB02` (`us-east-1b`)
  - `BATCH3--SUB03` (`us-east-1c`)
- **Route Configuration:**
  - **Destination:** `0.0.0.0/0` (All external traffic)
  - **Target:** `BATCH3-ALB-IGW` (Internet Gateway)

## Server Details

| Server Name          | Private IP     | Public IP        | Availability Zone |
| -------------------- | -------------- | ---------------- | ----------------- |
| **Interview Server** | `10.0.103.207` | `98.84.181.87`   | `us-east-1c`      |
| **Server 1**         | `10.0.101.66`  | `3.235.15.224`   | `us-east-1a`      |
| **Server 2**         | `10.0.102.174` | `18.208.107.126` | `us-east-1b`      |

## Summary

- The `BATCH3-ALB-VPC` spans three availability zones in `us-east-1`.
- Each subnet is associated with a single availability zone.
- Internet access is provided through `BATCH3-ALB-IGW`.
- The `BATCH3-ALB-ROUTE-TABLE` routes external traffic through the Internet Gateway.
- Three servers are hosted across different availability zones, and private and public IPs are assigned.

