# 🏋️ Exercise 4.2 Create a New Subnet 🏋️

## ✏️ Description ✏️
* Create a subnet in the VPC you created earlier.
* Choose an availability zone and assign the CIDR block of `172.16.100.0/24`
* To complete this using the AWS Commmand-Line Interface commands, you'll need the resource ID of the VPC:

```sh
aws ec2 create-subnet
--vpc-id [vpc-id]
--cidr-block 172.16.100.0/24
--availability-zone us-east-1a
```

* Assyuming you're running the command from the matching region, you should see output similar to the following:

```json
{
   "Subnet": {
      "AvailabilityZone": "us-east-
      1a",
      "AvailabilityZoneId": "use1-az2",
      "AvailableIpAddressCount": 251,
      "CidrBlock": "172.16.100.0/24",
      "DefaultForAz": false,
      "MapPublicIpOnLaunch": false,
      "State": "pending",
      "SubnetId": "subnet-0e398e93c154e8757",
      "VpcId": "vpc-0d19e8153b4d142ed",
      "OwnerId": "158826777352",
      "AssignIpv6AddressOnCreation": false,
      "Ipv6CidrBlockAssociationSet": [],
      "SubnetArn": "arn:aws:ec2:us-east-1:158826777352:subnet/subnet-0e398e93c154e8757"
   }
}
```

* Wait a few moments, and then check the status of the subnet as follows:

```sh
aws ec2 describe-subnets --subnet-ids [subnet-id]
```

* You should see the subnet in an `available` state, like so:

```json
{
   "Subnets": [
      {
         "AvailabilityZone": "us-east-1a",
         "AvailabilityZoneId": "use1-az2",
         "AvailableIpAddressCount": 251,
         "CidrBlock": "172.16.100.0/24",
         "DefaultForAz": false,
         "MapPublicIpOnLaunch": false,
         "State": "available",
         "SubnetId": "subnet-0e398e93c154e8757",
         "VpcId": "vpc-0d19e8153b4d142ed",
         "OwnerId": "158826777352",
         "AssignIpv6AddressOnCreation": false,
         "Ipv6CidrBlockAssociationSet": [],
         "SubnetArn": "arn:aws:ec2:us-east-1:158826777352:subnet/subnet-0e398e93c154e8757"
      }
   ]
}
```


## ✅ Solution ✅