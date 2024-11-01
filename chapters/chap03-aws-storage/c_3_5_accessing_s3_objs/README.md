<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 3.5 Accessing S3 Objects
* Restricting and providing access to S3 objects to match your business requirements/security needs, requires understanding of how S3 objects are accessed

## 🟥 Access Control
* By default, S3 objects are fully accessible to your AWS account
* You can provide external access and access from other AWS accounts.
* You can open access to the whole bucket or individual files using Access Control Lists (`ACLS`), S3 bucket policies or IAM policies - alot of these overlap each other
* AWS recommends bucket/IAM policies over ACLs

* S3 bucket policies are attached to the S3 bucket. This is ideal for giving multiple external accounts/users
* IAM policies are for when you want to control the way individual users and roles access multiple resources.

* Here is an example of an S3 bucket policy which allows root user and user Steve access to `MyBucket` and its contents:
```json
{
   "Version": "2012-10-17",
   "Statement": [
      {
         "Effect": "Allow",
         "Principal": {
            "AWS": ["arn:aws:iam:xxxxxxxxxxx:root",
            "arn:aws:iam:xxxxxxxxxxx:user/Steve"]
         },
         "Action": "s3:*",
         "Resource": ["arn:aws:s3:::MyBucket",
                      "arn:aws:s3:::MyBucket/*"]
      }
   ]
}
```

* The following IAM policy achieves the same thhing when attached to an IAM entity:
```json
{
   "Version": "2012-10-17",
   "Statement":[{
      "Effect": "Allow",
      "Action": "s3:*",
      "Resource": ["arn:aws:s3:::MyBucket",
                   "arn:aws:s3:::MyBucket/*"]
   }]
}
```

* S3 access points is another way of controlling how users/services access objects in buckets. Access points enable clients to read/write data which you allow.
* You can spin up an access point using an AWS CLI command like:
```
aws s3control create-access-point --name my-vpc-ap \ 
--account-id 123456789012 --bucket my-bucket \
--vpc-configuration VpcId=vpc-2b9d3c
```
## 🟥 Presigned URLs
* A presigned URL grants temporary access to an S3 object which is private.
* The URL can be generated programmitcally in your code to give programatic access to S3 objects
* The following AWS CLI command will return a URL, along with an authentication string. The URL becomes invalid after the prescribed 10 minutes (the default is 3600 seconds):
   ```
   aws s3 presign s3://MyBucketName/PrivateObject --expires-in 600
   ```
* I completed [Exercise 3.3](../../../exercises/chap03/e_3_3/) which showed the above command is not out of date ⚠️ You must now include the `--region eu-west-2` parameter

## 🟥 Static Website Hosting
* You can host an entire static website in an S3 bucket.
* This is ideal for websites where all code is executed in the client's browser
* S3 bucket can be configured to returna root document (index.html) when user access's a link.
* To use a DNS domain name (like `shivs-is-cool.com`), you would use `Amazon Route S3` provided the domain name is same name as S3 bucket.
* You can get a free SSL/TLS certificate to encrypt your site by requesting a certificate from AWS Certificate Manager (ACM) and importing it into your CloudFront distribution which specifies your S3 bucket as origin. 

* I completed [Exercise 3.4](../../../exercises/chap03/e_3_4/) where I build my own static website