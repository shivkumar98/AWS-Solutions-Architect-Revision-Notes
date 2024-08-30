<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 2.9 AWS CLI Example
* The following example code shows how you can use an AWS CLI command to deploy an EC2 instance.
* The `images-id`, `security-group-ids` and `subnet-id` values are not real - these should be replace with the actual IDs which fit your account and region:
```r
aws ec2 run-instances --image-id ami-xxxxxxx --count 1 \
--instance-type t2.micro --key-name MyKeyPair \
--security-group-ids sg-xxxxxx --subnet-id subnet-xxxxxx \
--user-data file://my_script.sh \
--tag-specifications \
'ResourceType=instance,Tags=


```