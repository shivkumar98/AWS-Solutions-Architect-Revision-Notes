<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 3.7 Other Storage-Related Services
* We shall become aware of other storage-related AWS services that, though perhaps not as common as the others you've seen, can make a big difference for the right deployment.

## 🟥 Amazon Elastic File System
* Amazon's Elastic File System (EFS) is a scalable and shareable file storage which can be accessed from Linux instances.
* EFS files are designed to be accessed within a VPC via NFS (Network File System) mounts on EC2 Linux instance
* This is designed for low-latency, secured and durable file storage amongst multiple instances

## 🟥 Amazon FSx
* Amazon FSx comes in four flavors:
  1. FSx for Lustre
  2. Fsx for Windows File Server
  3. FSx for OpenZFS
  4. FSx for NetApp ONTAP.
* Lustre is an open sourced file distribution system built to give clusters of Linux servers access to high-performance filesystems for compute-intensive operations
* FSx for Wildows File Server integrates SMG, NTFS and Microsoft Active Directory

## 🟥 AWS Storage Gateway
* AWS Storage Gateway offers software gateway appliances to integrate backup and acrchiving requirements of local operations with cloud.
* Local devices can connect to the appliance like its a physical device while the data is persisted to AWS platforms.
* Data can be maintaind in a local cache so its available offline too

## 🟥 AWS Snow Family
* Migrating data sets over a normal internet connection uses up too much bandwidth to be practical.
* Uploading petabytes of data makes AWS Snow device an essential option
* Upon request, AWS will ship a physical device which you can transfer data to, ship back to AWS who will then upload to S3
* The smallest Snow Family device has 22 TB of storage, with the heavier devices having 80TB of storage.
* AWS Snowmobile is waterproof and tamper-resistant in a large 45 foot long shipping container.
* All snow devices are 256 bit encrypted.
* AWS Snow Family makes uploading large amounts of data efficient and cost effective (compared to AWS Direct Connect connection)

## 🟥 AWS DataSync
* DataSync specialises in moving on-promises data stores into your AWS account with minimal fuss/effot
* This happens over a regular internet connection, and unlike Snow Famiy, you are not limites to S3
* DataSync lets you drop data into any AWS service on your account
* E.g. you can do the following:
  * Secure data from datacentres to S3 or Glacier
  * Transfer data sets to S3, EFS or FSx - which can be processed by your EC2 instances
* A single DataSync task can handle external transfer rates up to 10 Gbps and offer encryption and validation