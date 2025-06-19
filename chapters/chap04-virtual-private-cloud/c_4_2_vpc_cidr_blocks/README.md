# 🧠 4.2 VPC CIDR Blocks
* Like a traditional network, a VPC vonsists of at least one range of contiguous IP addresses
* This address range is represented as a `Classless Inter-Domain Routing` (CIDR) block.
* The CIDR block determines which IP addresses may be assigned to instances and other resources within the VPC.
* When creating a VPC, you must assign a primary CIDR block.
* After creating a VPCS, you divide the primary VPC CIDR block into subnets that hold your AWS resourcers.
* There are different ways to reperesent the range of IP addresses.
* The simplest/shortest was is to use `slash notation` or CIDR notation:
  * The CIDR Range `172.16.0.0/16` include all addresses from `172.16.0.0` to `172.15.255.255`
* You will also hear an CIDR block being referred