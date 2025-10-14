<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launching VPC Resources

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-ec2)

**Author:** PATRICK ADDAI  
**Email:** patrickaddai1689@gmail.com

---

## Launching VPC Resources

![Image](http://learn.nextwork.org/refreshed_amber_shy_cantaloupe/uploads/aws-networks-ec2_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amamzon VPC is AWCS's foundational networking service that helps us create our own networks and configure the security/traffic rules and connectivity with the internet.

### How I used Amazon VPC in this project

I used Amazon VPC to create my own VPC with different  resources/components (e.g. Security groups, network ACLs), private resources (e.g. a private subnet) and EC2 instances in both my public and private subnets.

### One thing I didn't expect in this project was...

i didn't expect the resources map to be so visual and interactive! Such a convenient and speedy way to set up an entire VPC architecture. 

### This project took me...

This project took me 2.5 hours to complete (including live demo time)

---

## Setting Up Direct VM Access

Directly accessing a virtual machine means establishing a connection to the instance's operating system to manage and interact with it as if it were a physical machine.

### SSH is a key method for directly accessing a VM

SSH, or Secure Shell, is the protocol we use for this secure access to a remote machine. When you connect to the instance, SSH verifies you possess the correct private key corresponding to the public key on the server, ensuring only authorized users can access the instance.

### To enable direct access, I set up key pairs

The key pair type determines the algorithm used for generating the key pair's cryptographic keys.

A private key's file format means the specific structure and encoding used to store a private key. My private key's file format was .pem

---

## Launching a public server

'I had to change my EC2 instance's networking settings by changing the VPC and the subnet my EC2 instance was going to be launched by updated both to y Nextwor VPC and my Public Subnet respectively. I also used my existing public security group.

![Image](http://learn.nextwork.org/refreshed_amber_shy_cantaloupe/uploads/aws-networks-ec2_88727bef)

---

## Launching a private server

My private server has its own dedicated security group because the nextwork public security group allows in all HTTP traffic which would leave my private server much more vulnerable to security attacks/risks.

My private server's security group's source is my Nextwork Public Securoty Group which which means only SSH traffic coming from resources associated with that security would be allowed.

![Image](http://learn.nextwork.org/refreshed_amber_shy_cantaloupe/uploads/aws-networks-ec2_4a9e8014)

---

## Speeding up VPC creation

I used an alternative way to set up an Amazon VPC! This time, I used the 'VPC and more' option , which gives me a VPC resource map to use when creating the VPC and all of its components e.g. security groups, route tables and internet gateways.

A VPC (Virtual Private Cloud) resource map is a visual representation of your VPC's network topology, displaying the relationships between resources like subnets, route tables, gateways, and other components within your VPC.

My new VPC has a CIDR block of 10.0.0.0/16 It is possible for my new VPC to have the same IPv4 CIDR block as my existing VPC because VPC are already isolated from each other. Still this is not the best practice if we need VPC peering.

![Image](http://learn.nextwork.org/refreshed_amber_shy_cantaloupe/uploads/aws-networks-ec2_1cbb1b88)

---

## Speeding up VPC creation

### Tips for using the VPC resource map

When determining the number of public subnets in my VPC, I only had two options: either none or one in each Availability Zone for my VPC. This was because it is best practice (improves redundancy and high availability) to have at least subnet/AZ

The set up page also offered to create NAT gateways, which are gconnectors/gateways that will let resources in my my private subnet get access to the internet (e.g. for security updates) whiles still blocking off incoming traffic from the internet.

![Image](http://learn.nextwork.org/refreshed_amber_shy_cantaloupe/uploads/aws-networks-ec2_8ee57662)

---

---
