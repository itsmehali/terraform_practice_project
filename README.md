﻿# Terraform Practice Project
 
 
This is a Terraform configuration file that sets up an Amazon Web Services (AWS) Virtual Private Cloud (VPC) and various resources within that VPC.

The first section configures the AWS provider, specifying the region and the access and secret keys for authentication.
The second section creates a VPC with a CIDR block of 10.0.0.0/16 and assigns it the tag "production".
The third section creates an internet gateway and associates it with the VPC created in the second section.
The fourth section creates a route table for the VPC and assigns it the tag "Prod", it also creates two routes, one for IPv4 and one for IPv6 traffic, both routes point to the internet gateway created earlier.
The fifth section creates a subnet within the VPC with a CIDR block of 10.0.1.0/24, and assigns it the availability zone us-east-1a and the tag "prod-subnet"
The sixth section associates the subnet created in the fifth section with the route table created in the fourth section.
The seventh section creates a security group that allows incoming traffic on ports 22, 80 and 443, and allows all outgoing traffic.
The eighth section creates a network interface in the subnet created earlier and associates the security group created in the seventh section to it, with a private IP address of 10.0.1.50
The last section creates an Elastic IP and assigns it to the network interface created in the eighth section, and makes sure it is associated with the private IP of 10.0.1.50.
