# 🏋️ Exercise 1.1 Use the AWS CLI 🏋️

## ✏️ Description ✏️
* Install (if necessary) and configure the AWS CLI on your local system and demonstrate
it’s running properly by listing the buckets that currently exist in your account. For extra
practice, create an S3 bucket and then copy a simple file or document from your machine
to your new bucket. From the browser console, confirm that the file reached its target.

## ✅ Solution ✅
* I configured the AWS CLI in the command prompt using `aws configure`
* I am asked to provide the following:
```
AWS Access Key ID 
AWS Secret Access Key
Default region name
Default output format  
```
* I go to the IAM console in the broweser, I select my own user,
* Under `Security Credentials`, I create a new Access Key
* I provide these details
* I list my existing buckets:
```
aws s3 ls
```

* I create a new bucket:
```
C:\Users\Shiv>aws s3 mb s3://shivs-bucket
make_bucket: shivs-bucket
```
* I then copy a file to this bucket
```
C:\Users\Shiv>aws s3 cp text.txt s3://shivs-bucket
upload: .\text.txt to s3://shivs-bucket/text.txt
```