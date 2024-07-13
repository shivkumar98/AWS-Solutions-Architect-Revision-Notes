# 🧠 2.3 EC2 Storage Volumes
* Storage drives (volumes) are virtualised physical drives.
* From the perspective of the OS, the volume is same as a normal physical drive
* There are different types of AWS volumes

<br>

## 🟥 Elastic Block Store Volumes
* Elastic Block Store (EBS) volumes can be attached to at most one instance at a time - but you can attach multiple volumes to a single instance.
* These can be used exactly as you would you use a USB flash drive, HDDs you would use for a physical server.
* The AWS SLA guarantees reliability of 99.99% of the date stored on its EBS volumes.
   - If EBS volume were to fail, it will already be made available via a backup before a problem can even be observed.
* There are four EBS volume types in this book but there are three on AWS as of now:
   1. Solid State Drive (SSD) Volumes
   2. Hard Disk Drive (HDD) Volumes
   3. Previous Generation Volumes
* The performance of the volume type is measured in `maximum IOPS/volume` - maximum input/output operations per seconds
* The four volume types in this book consist of two SSD types, and two HDD types.
* Here are the four types from most expensive to cheapest:
   1. **EBS-Provisioned IOPS SSD**
   * Maximum IOPS: 64,000
   * Maximum throughput: 1,000 MB/s
   * Ideal for application with intense I/O operation rates
   2. **EBS General-Purpose SSD**
   * Maximum IOPS: 16,000
   3. **Throughput-Optimized HDD**
   * Maximum IOPS: 500
   * Maximum throughput: 500 MB/s
   4. **Cold HDD**
   * Maximum IOPS: 250

### 🟡 EBS Volume Features
* You can create a snapshot of an EBS volume - this allows you to copy volumes
* Snapshots can be shared to instances or be converted to an AMI
* You can create an AMI image directly from a running instance - to avoid losing data, thhe instance should be shut down first
* EBS volumes can be encrypted to protect their data.
* I work on [Exercise 2.4](/exercises/chap02/e_2_4/) which walks through how to launch a new instance based on an existing snapshot

<hr>

## 🟥 Instance Store Volumes
* Instance volumes are ephemeral - when the attached-to instance is shutdown, the data is permanently lost
* Here are reasons why you would store data on instance store volume over EBS:
   - These are SSDs which are physically attached to the server hosting the instance via NVME, hence are very fast
   - This is included in the pricing model, so it is ideal for temporary and disposable data.
* The number of instance store volumes is dependent on the instance type.