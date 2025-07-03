# 🧠 4.3 Subnets
* A subnet is a logical container within a VPC that holds VPC resources, including EC2 instances.
* Subnets let you isolate instances, control how instances communicate, and organises by function.
* E.g. a subnet can allow internet access for public web servers, and another subnet could be used for database servers that should only be accessible to web instances.
* Conceptually, subnets are akin to LANS in a traditional network.
* A common phrase is `launch an instance into a subnet` - because every instance MUST exist within a subnet.
* You can not move an instance after it is allocated into a subnet.
* By extension, you also can not move an instance from a AZ, or a VPC to another AZ/VPC.
* You can still terminate and create an instance in another subnet. If you wish to preserve the data from the instance, you can snapshot the EBS volume, create an AMI and utilise the EBS colume to create another instance in a different subnet.

## 🟥 Subnet CIDR Blocks
* From the VPC CIDR block, you extract out a smaller CIDR block for each subnet.
* E.g., you could have a CIDR of `172.16.0.0/16`, then your subnet CIDR could be `172.16.100.0/24` (172.16.100.0 - 172.16.100.255)
* AWS reserves the first four and last IP addresses in every subnet. 
   * E.g. if you have a subnet CIDR is `172.16.100.0/24`, then the following IP addresses are reseved:
     * `172.16.100.0`
     * `172.16.100.1` - implied router
     * `172.16.100.2` - Amazon-provided DNS server
     * `172.16.100.3` - Reserved
     * `172.16.100.255`
* The restrictions on prefix lengths for a subnet CIDR are the same as VPC CIDRs. Subnet CIDR blocks in a single VPC cannot overlap with each other. And once you assign an IP prefix to a subnet, you can't change it.

* It's possible for a subnet and VPC to share the same CIDR.
  * E.g. you can assign the CIDR `192.168.0.0/16` to both a VPC and a subnet within the VPC.
  * This is uncommon and would prevent you from forming additional subnets. Which effectively limits the VPC to one AZ
* More commonly, each subnet's prefix will be longer than the VPC's CIDR block to allow for multiple subnets within the same VPC
  * E.g. if you assign `192.168.0.0/16` to the VPC, you might assign the CIDR `192.168.3.0/24` to a subnet within that VPC, allowing room for additional subnets.

* A subnet can't have multiple CIDRs like VPC can with a secondary CIDR.
* However a subnet CIDR can be derived from both the primary and secondary of the VPC CIDR
   * E.g. if your VPC hgas a primary CIDR of `172.16.0.0/16` and a secondary CIDR of `17.17.0.0/16`, a subnet of `172.17.12.0/24` is permissable as it is derived from the secondary CIDR.

## 🟥 Availability Zones

## 🟥 IPv6 CIDR Blocks