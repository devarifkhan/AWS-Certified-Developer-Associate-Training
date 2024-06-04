# create VPC

Name: MyVPC
IPv4 CIDR Block: 10.0.0.0/16

# Create Public Subnets

NAME: Public-1A
Availability Zone: us-east-1a
IPv4 CIDR Block: 10.0.0.0/24

NAME: Public-1B
Availability Zone: us-east-1b
IPv4 CIDR Block: 10.0.0.0/24

NAME: Private-1A
Availability Zone: us-east-1a
IPv4 CIDR Block: 10.0.3.0/24

NAME: Private-1B
Availability Zone: us-east-1b
IPv4 CIDR Block: 10.0.4.0/24

# Create Private Route Table

Name: Private-RT
VPC: MyVPC
Subnet association: Private-1A, Private-1B

# Create Internet Gateway

Name: MyIGW
VPC: MyVPC
