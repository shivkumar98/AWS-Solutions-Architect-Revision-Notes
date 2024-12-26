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