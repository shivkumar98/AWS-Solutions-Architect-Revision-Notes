# 🧠 4.2 VPC CIDR Blocks
* Like a traditional network, a VPC vonsists of at least one range of contiguous IP addresses
* This address range is represented as a `Classless Inter-Domain Routing` (CIDR) block.
* The CIDR block determines which IP addresses may be assigned to instances and other resources within the VPC.
* When creating a VPC, you must assign a primary CIDR block.
* After creating a VPCS, you divide the primary VPC CIDR block into subnets that hold your AWS resourcers.
* There are different ways to reperesent the range of IP addresses.
* The simplest/shortest was is to use `slash notation` or CIDR notation:
  * The CIDR Range `172.16.0.0/16` include all addresses from `172.16.0.0` to `172.15.255.255`
* You will also hear an CIDR block being referred as an `IP prefix`
* The `/16` part is the `prefix length` - which refers to the length of the submet mask which for VPC CIDR can ranged from `/16` to `/28`
* The prefix length and number of IP addresses in the CIDR are inversely proportional - `/28` prefix length gives 16 possibe addresses, and `/16` gives you 65,536 possible addresses.
* The acronym IP refers to Internet Protocol version 4 (IPv4).
* Valid IPv4 prefix lengths range from /0 to /32.
* While it is possible to have any valid IP range for VPC CIDR, it's bst to use one in the following RFC 1918 to avoid conflicts with public Internet addresses:
   - `10.0.0.0 - 10.255.255.55.55` (10.0.0.0/8)
   - `172.16.0.0 - 172.31.255.255` (172.16.0.0/12)
   - `192.168.0.0 - 192.168.255.255` (192.168.0.0/16)
* If you plan to connect your VPC to another network, there shouldn't be any overlap fo rused IP addresses

## 🟥 Secondary CIDR Blocks
* A secondary CIDR block can be specified for a VPC after you've created it.
* These blocks must come from either the same RFC 1918 address range as the primary OR publicly routable range, but must not overlap with the primary or other secondary blocks
* E.g. if the VPC's PRIMARY CIDR is `172.16.0.0/16`, you may specify a secondary CIDR of `172.17.0.0/16` because it resides in the `172.16.0.0/12` range (`172.16.0.0-172.31.255.255`) - and you may not specify `192.168.0.0/16` as a secondary CIDR.
* If you think you might ever need a secondary CIDR, be careful about your choice of primary CIDR
* If you use `19.168.0.0/16` as primary, it can't be used as secondary CIDR using any of the other RFC 1918 ranges ⚠️

## 🟥 IPv6 CIDR Blocks
* You can allow AWS to assign an `IPv6 CIDR` to your VPC
* However you can not choose an arbritary IPv6, AWS assigns one of their choice upon request
* This `IPv6 CIDR` will be a publicly routable prefix from the global unicast IPv6 address space, so all IPv6 addresses are reachable from the internet.

* E.g., AWS may assign you the `CIDR 2600`: `1f18:2551:8900/56`
* Note the prefix length is always `/56`
* You can assing your own public IPv6 CIDR block to your VPC via BYOIP (bring your own IP address) feature.
* If you want your `IPv6` addresses to be reachable via the Internet, you can advertise a prefix length as small as `/48` - otherwise smallest prefix length is `/56`

* I complete [exericse 4.1 to create my own VPC](../../../exercises/chap04/e_4_1/) 