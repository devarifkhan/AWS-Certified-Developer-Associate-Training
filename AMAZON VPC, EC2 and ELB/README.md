# AWS Infrastructure Configuration

This document outlines the configuration for the AWS infrastructure.

## VPC

- **Name:** MyVPC
- **IPv4 CIDR Block:** 10.0.0.0/16

## Subnets

### Public Subnets

1. **Name:** Public-1A
   - **Availability Zone:** us-east-1a
   - **IPv4 CIDR Block:** 10.0.0.0/24

2. **Name:** Public-1B
   - **Availability Zone:** us-east-1b
   - **IPv4 CIDR Block:** 10.0.1.0/24

### Private Subnets

1. **Name:** Private-1A
   - **Availability Zone:** us-east-1a
   - **IPv4 CIDR Block:** 10.0.3.0/24

2. **Name:** Private-1B
   - **Availability Zone:** us-east-1b
   - **IPv4 CIDR Block:** 10.0.4.0/24

## Route Tables

- **Name:** Private-RT
  - **VPC:** MyVPC
  - **Subnet association:** Private-1A, Private-1B

## Internet Gateway

- **Name:** MyIGW
- **VPC:** MyVPC