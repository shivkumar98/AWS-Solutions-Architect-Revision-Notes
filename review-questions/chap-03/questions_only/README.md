# Chapter 3 - Review Questions Attempt #

## Results:

* Date: 
* Score:

| Question # | Correct  |
| ---------- | -------  |
| 1          |       |
| 2          |       |
| 3          |       |
| 4          |       |
| 5          |       |
| 6          |       |
| 7          |       |
| 8          |       |
| 9          |       |
| 10         |       |
| 11         |       |
| 12         |       |
| 13         |       |
| 14         |       |
| 15         |       |
| 16         |       |
| 17         |       |
| 18         |       |
| 19         |       |
| 20         |       |


## ✏️ Summary Notes ✏️


## 🟧 Question 1

❓ Your organisation runs Linux-based EC2 instances that all require low latency read/write access to a single set of files. Which of the following AWS services are your best choices? (CHOOSE TWO) ❓

* A. `AWS Storage Gateway`
* B. `AWS S3`
* C. `Amazon Elastic File System`
* D. `AWS Elastic Block Store`

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>


## 🟧 Question 2

❓ Your organisation expects to be storing and processing large volumes of data in many small increments. When considering S3 usability, you'll need to know whether you'll face any practical limitations in the use of AWS account resources. Which of the following will normally be available only in limited amounts? ❓

* A. PUT requests/month against an S3 bucket
* B. The volume of data space available per S3 bucket
* C. Account-wide S3 storage space
* D. The number of S3 buckets within a single account.

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 3
❓ You have a publicly available file called `filename` stored in an S3 bucket names `bucketname`. Which of the following addresses will successfully retrieve the file using a web browser? ❓

* A. `s3.amazonaws.com/bucketname/filename`
* B. `filename/bucketname.s3.amazonaws.com`
* C. `s3://bucketname/filename`
* D. `s3://filename/bucketname`

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 4
❓ If you want the files stored in an S3 bucket to be accessible using a familiar directory hierarchy system, you'll need to specify prefixes and delimiters. What are prefixes and delimiters? ❓

* A. A prefix is the name common to the objects you want to group, and a delimiter is the bar (|) character
* B. A prefix is the DNS name that precedes the `amazonaws.com` domain, and a delimiter is the name you want to give your file directory
* C. A prefix is the name common to the objects you want to group, and a delimiter is a forward slash character (/)
* D. A prefix is the name common to the file type you want to identify, and a delimiter is a forward slash character (/)


   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 5
❓ Your web application relies on data objects stored in AWS S3 buckets. Compliance with industry regulations requires that those objects be encrypted and that related events be closely tracked. Which combination of tools should you use? (CHOOSE TWO) ❓

* A. Server-side encryption
* B. Amazon S3-Managed Keys
* C. AWS KMS-Managed Keys
* D. Client-side encryption
* E. AWS End-to-End managed keys

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 6 
❓ You are engaged in a deep audit of the use of your AWS resources and you need to better understand the structure of your S3 server access logs. Which of the following operational details are likely to be included in S3 server access logs? (CHOOSE THREE) ❓

* A. Source bucket name
* B. Action requested
* C. Current bucket size
* D. API bucket creation calls
* E. Response status

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 7
❓ You're accessing the level of durability you'll need to sufficiently ensure the long-term viability of a new web application you're planning. Which of the following risks are covered by S3's durability guarantee (CHOOSE TWO) ❓

* A. User misconfiguration
* B. Account security breach
* C. Infrastructure failure
* D. Temporary service outages
* E. Datacenter security breach

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 8
❓ Which of the following explains the difference in durability between S3's Standard-IA and S3 Intelligent-Tiering classes? ❓

* A. Standard-IA data has only 99.9% availability, whereas Intelligent-Tiering's availability depends on the data's current state.
* B. Standard-IA data is heavily replicated but only within a single availablity zone, whereas Intelligent-Tiering data is only lightly replicated
* C. Standard-IA data is replicated across AWS regions, whereas Intelligent-Tiering data is restricted to a single region.
* D. Standard-IA data is automatically backed up to Amazon Glacier, whereas Intelligent-Tiering data remains within S3.

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 9
❓ Which of the following is the 12-month availability guarantee for the S3 Standard-IA class? ❓

* A. 99.99 percent
* B. 99.9 percent
* C. 99.999999999 percent
* D. 99.5 percent

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 10
❓ Your application regularly writes data to an S3 bucket, but you're worried about the potential for data corruption as a result of conflicting concurrent operations. Which of the following data operations would not be subject to concerns about eventual consistency? ❓

* A. Operations immediately preceding the deletion of an existing object
* B. Operations subsequent to the updating of an existing object
* C. Operations subsequent to the deletion of an existing object
* D. Operations subsequent to the creation of a new object

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 11
❓ You're worried that updates to the important data you store in S3 might incorrectly overwrite existing files. What must you do to protect objects in S3 buckets from being accientally lost ❓

* A. Nothing. S3 protects existing files by default.
* B. Nothing. S3 saves older versions of your files by default.
* C. Enable versioning
* D. Enable file overwrite protection

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 12
❓ Your S3 buckets contain many thousands of objects. Some of them could be moved to less expensive storage classes and others still require instant availability. How can you apply transitions between storage classes for only certain objects within an S3 bucket?  ❓

* A. By specifying particular prefixes when you define your life cycle rules.
* B. This isn't possible. Life cycle rules must apply to all the objects in a bucket.
* C. By specifying particular prefixes when you create the bucket.
* D. By importing a predefined life cycle rule template

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 13
❓ Which of the following classes will usually make the most sense for long-term storage when included within a sequence of life cycle rules? ❓

* A. S3 Glacier Flexible Retrieval
* B. Reduced Redundancy
* C. S3 One Zone-IA
* D. S3 Standard-IA


   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 14
❓ Which of the following are recommended methods for providing secure and controlled access to your buckets? (CHOOSE TWO) ❓

* A. S3 access control lists (ACLs)
* B. S3 bucket policies
* C. IAM policies
* D. Security groups
* E. AWS Key Management Service

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 15
❓ In the context of an S3 bucket policy, which of the following statements describe a principal? ❓

* A. The AWS service being defined (S3 in this case)
* B. An origin resource that's given permission to alter an S3 bucket
* C. The resource whose access is being defined
* D. The user or entity to which access is assigned

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 16
❓ You don't want to open up the contents of an S3 bucket to anyone on the Internet, but you need to share the data with specific clients. Generating and then sending them a presigned URL is a perfect solution. Assuming you didn't explicitly❓

* A. 24 hours
* B. 3,600 seconds
* C. 5 minutes
* D. 360 seconds

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 17
❓ Which non-S3 AWS resources can improve the security and user experience of your S3-hosted static website? (CHOOSE TWO) ❓

* A. AWS Certificate Manager
* B. Elastic Compute Cloud (EC2)
* C. Relational Database Service (RDS)
* D. Route 53
* E. AWS Key Management Service

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 18
❓ How long will it take to retrieve an archive from Amazon Glacier Deep Archive? ❓

* A. 5 hours
* B. 12 hours
* C. 2 days
* D. 1 week

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 19
❓ You need a quick way to transfer very large (peta-scale) data archives to the cloud. Assuming your Internet connection isn't up to the task, which of the following will be both relatively fast and cost-effective? ❓

* A. Direct Connect
* B. Server Migration Service
* C. Snowball
* D. Storage Gateway

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>

## 🟧 Question 20
❓ Your organisation runs Windows-based EC2 instances that all require low-latency read/write access to a single set of files. Which of the following AWS services is your best choice? ❓

* A. Amazon FSx for Windows File Server
* B. Amazon FSx for Lustre
* C. Amazon Elastic File System
* D. Amazon Elastic Block Store

   <details>
   <summary> 📝 My answer 📝 </summary>


   * **CORRECT ANSWER:**

   </details>

<hr>