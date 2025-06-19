# 🏋️ Exercise 4.1 Create a VPC 🏋️

## ✏️ Description ✏️
* Create a VPC with the primary CIDR `172.16.0.0/16`
* To complete this exerxise using the AWS CLI, enter the following command:

```yaml
aws ec2 create-vpc
--cidr-block 172.16.0.0/16
```

* If the command succeeds, you should see output similar to the following:

```json
{
   "Vpc": {
   "CidrBlock": "172.16.0.0/16",
   "DhcpOptionsId": "dopt-21500a47",
   "State": "pending",
   "VpcId": "vpc-0d19e8153b4d142ed",
   "OwnerId": "158826777352",
   "InstanceTenancy": "default",
   "Ipv6CidrBlockAssociationSet": [],
   "CidrBlockAssociationSet": [
      {
      "AssociationId": "vpc-cidr-
      assoc-
      0a99f2470e29710b7",
      "CidrBlock": "172.16.0.0/16",
      "CidrBlockState": {
         "State": "associated"
         }
      }
   ],
   "IsDefault": false,
   "Tags": []
   }
}
```
   
## ✅ Solution ✅