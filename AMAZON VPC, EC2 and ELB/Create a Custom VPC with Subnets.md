# AWS Infrastructure Configuration

This document outlines the configuration for the AWS infrastructure.

# VPC CIDR Block and Subnets

| Subnet Name | IPV4 CIDR BLOCK | Availability Zone | Route Table | Auto-Assign Public IPV4 |
|-------------|-----------------|-------------------|-------------|-------------------------|
| private-1a  | 10.0.4.3/24     | ap-south-1a       | Private-RT  | No                      |
| private-1b  | 10.0.4.0/24     | ap-south-1b       | Private-RT  | No                      |
| public-1a   | 10.0.1.0/24     | ap-south-1a       | MAIN        | Yes                     |
| public-1b   | 10.0.2.0/24     | ap-south-1b       | MAIN        | Yes                     |

## VPC

- **Name:** MyVPC
- **IPv4 CIDR Block:** 10.0.0.0/16

## Subnets

### Public Subnets

1. **Name:** Public-1A
    - **Availability Zone:** ap-south-1a
    - **IPv4 CIDR Block:** 10.0.1.0/24

2. **Name:** Public-1B
    - **Availability Zone:** ap-south-1b
    - **IPv4 CIDR Block:** 10.0.2.0/24

### Private Subnets

1. **Name:** Private-1A
    - **Availability Zone:** ap-south-1a
    - **IPv4 CIDR Block:** 10.0.3.0/24

2. **Name:** Private-1B
    - **Availability Zone:** ap-south-1b
    - **IPv4 CIDR Block:** 10.0.4.0/24

## Route Tables

- **Name:** Private-RT
    - **VPC:** MyVPC
    - **Subnet association:** Private-1A, Private-1B

## Internet Gateway

- **Name:** MyIGW
- **VPC:** MyVPC

# Lanuch EC2 Instance in Public 1A

aws ec2 run-instances --image-id ami-00fa32593b478ad6e --instance-type t2.micro --security-group-ids
sg-0284958e7f3442466 --subnet-id subnet-0275631932e79e113 --key-name MyVPCKEY --user-data file://user-data-subnet-id.txt

# Lanuch EC2 Instance in Public 1B

aws ec2 run-instances --image-id ami-00fa32593b478ad6e --instance-type t2.micro --security-group-ids
sg-0284958e7f3442466 --subnet-id subnet-07d42116806b32531 --key-name MyVPCKEY --user-data file://user-data-subnet-id.txt

# Lanuch EC2 Instance in Private 1B

aws ec2 run-instances --image-id ami-00fa32593b478ad6e --instance-type t2.micro --security-group-ids
sg-0284958e7f3442466 --subnet-id subnet-0cd22b0fbdaa98c20 --key-name MyVPCKEY --user-data file://user-data-subnet-id.txt