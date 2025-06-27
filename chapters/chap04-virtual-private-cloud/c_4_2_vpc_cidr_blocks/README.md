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
* E.g. if the VPC's PRIMARY CIDR is `172.16.0.0/16`, you may specify a secondary CIDR of `172.17.0.0/16` because it resides in the `172.16.0.0/12` range (`172.16.0.0-172.31.255.255`)
* 