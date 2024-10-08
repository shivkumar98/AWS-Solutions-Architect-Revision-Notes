# Chapter 2 - Review Questions Attempt 1

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


## 🟧 Question 1

❓ You need to deploy multiple EC2 Linux instances that will provide your company with VPNs using a software called OpenVPN. Which of the following will be thhe most efficient solutionss (CHOOSE TWO)❓

* A. Select a regular Linux AMI and bootstrap it using user data thhat will install and configure the OpenVPN package on the instance and use it for your VPN instances
* B. Search the community AMIs for an official AMI provided and supported by the Open-VPN company
* C. Search the AWS Marketplace to see whether there's an official AMI provided and supported by the OpenVPN company
* D. Select a regular Linux AMI and SSH to manually install and configure the OpenVPN package
* E. Create a site-to-site VPN connection from the wizard in the AWS VPC dashboard

<details>
<summary> 📝 My answer 📝 </summary>

* **B,C**
</details>

<hr>


## 🟧 Question 2

❓ As part of your company's long-term cloud migration strategy, you have a VMware virtual machines in your local infrastructure that you'd like to copy to your AWS account and run as an EC2 instance. Which of the following will be necessary steps? (choose two) ❓

* A. Import the virtual machine to your AWS region using a secure SSH tunnel.
* B. Import the virtual machine using VM Import/Export.
* C. Select the imported VM from among your private AMIs and launch an instance.
* D. Select the imported VM from the AWS Marketplace AMIs and launch an instance.
* E. Use the AWS CLI to securely copy your virtual machine image to an S3 bucket within the AWS region you'll be using.

<details>
<summary> 📝 My answer 📝 </summary>

* The VM Import/Export tool should be used, then you will deploy it via your private AMIS
* **B,C**

</details>

## 🟧 Question 3

❓ Your AWS CLI command to launch an AMI as an EC2 instance has failed, giving you an error message that includes `InvalidAMIID.NOTFOUND`. What of the following is the most likely cause? ❓

* A. You haven't configured the `~/.aws/config` file
* B. The AMI is being updated and is temporarily unavailable.
* C. Your key pair file has been given the wrong (overly permissive) permissions.
* D. The AMI you specified exists in a different region than the one you've currently speicified.

<details>
<summary> 📝 My answer 📝 </summary>

* Total guess that it is D, all other answers seem irrelevant
* **D**

</details>

## 🟧 Question 4

❓ The sensitivity of the data your company works with means that the instances you run must be secured through *complete* physical isolation. What should you specify as you configure as a new instance. ❓

* A. Dedicated Host tenancy
* B. Shared tenancy
* C. Dedicated Instance tenancy
* D. Isolated tenancy

<details>
<summary> 📝 My answer 📝 </summary>

* It's definitely not B
* I don't even think D is a valid option
* **A**
</details>

## 🟧 Question 5

❓ Normally, two instances running `m5.large` instance types can handle the traffic accessing your online e-commerce site, but you know that you will face short, unpredictable periods of high-demand. Which of the following choices should you implement? (choose two)

* A. Configure autoscaling.
* B. Configure load balancing.
* C. Purchase two `m5.large` instances on the spot market and as many on-demand insances as necessary.
* D. Shut down your `m5.large` instances and purchase instances using a more robust instance type to replace them.
* E. Purchase two `m5.large` reserve instances and as many on-demand instances as necessary.

<details>
<summary> 📝 My answer 📝 </summary>

* My guess its A and B, but E doesn't seem wrong neither
* **A,B**
</details>

## 🟧 Question 6

❓ Which of the following use cases would be most cost effective if run using spot market instances? ❓

* A. Your e-commerce website is built using  a publicly available AMI
* B. You provide high-end video rendering services using a fault-tolerant process that can easily manage a job that was unexpectedly interrupted.
* C. You're running a backend database that must be reliably updated to keep track of critical transactions.
* D. Your deployment runs as a static website on S3.

<details>
<summary> 📝 My answer 📝 </summary>

* Spot market instances are intended for short term and consistent usage.
* I'm guessing its B
* **B**
</details>

## 🟧 Question 7
❓ In the course of a routine infrastructure audit, your organisation discovers that some of your running EC2 instances are not configured properly and must be updated. Which of the following configuration details cannot be changed be changed to an existing EC2 instance. ❓

* A. AMI
* B. Instance type
* C. Security Group
* D. Public IP address

<details>
<summary> 📝 My answer 📝 </summary>

* It's A or D
* **A**
</details>


## 🟧 Question 8
❓ For an account with multiple resources running as part of multiple projects, which of the following key/value pair combination examples would make the most effective identification convention for resource tags?

* A. `servers:server1`
* B. `project1:server1`
* C. `EC2:projectg1:server1`
* D. `server1:project1`

<details>
<summary> 📝 My answer 📝 </summary>

* **B**
</details>

## 🟧 Question 9
* Which of the following EBS options will you need to keep your data-hungry application that requires 20,000 IOPS happy?

* A. Cold HDD
* B. General Purpose SSD
* C. Throughput-optimized HDD
* D. Provisioned IOPS SSD

<details>
<summary> 📝 My answer 📝 </summary>

* My guess would be D, but C could also be correct too.
* **D**
</details>


## 🟧 Question 10
* Your organisation needs to introduce Auto Scaling to its infrastructure and needs to generate a "golden image" from an existing EBS volume. This image will need to be shared among multiple AWS accounts belonging to your organisation. Which of the following steps will get you there? (Choose three.)

* A. Create an image from a detached EBS volume, use it to create a snapshot, select your new AMI from your private collection, and use it for your launch configuration.
* B. Create a snapshot of the EBS root you need, use it to create an image, select your new AMI from your private collection, and use it for your launch configuration.
* C. Create an image from the EBS volume attached to the instance, select your new AMI from your private collection, and use it for your launch configuration.
* D. Search the AWS Marketplace for the appropiate image and use it for your launch configurationn.
* E. Import the snapshot of an EBS root volume from a different AWS account, use it to create an image, select your new AMI from your private collection, and use it for your launch connfiguration.

<details>
<summary> 📝 My answer 📝 </summary>

* **A,B,E**
</details>


## 🟧 Question 11
* Which of the following are benefits of instance store volumes? (Choose two)

* A. Instance volumes are physically attached to the server that's hosting your instance, allowing faster data access.
* B. Instance volumes can be used to store data even after the instance is shut down.
* C. The use of instance volumes does not incur costs (beyond those for the instance itself)
* D. You can set termination protection so that an instance volume can't be accidentally shut down.
* E. Instance volumes are commonly used as a base for the creation of AMIs.

<details>
<summary> 📝 My answer 📝 </summary>

* A - true
* B - don't know
* C - false
* D - true
* E - false
* **A,D**
</details>

## 🟧 Question 12
* According to default behavior (and AWS recommendations), which of the following IP addresses could be assigned as the private IP for an EC2 instance? (Choose two)

* A. `54.61.211.98`
* B. `23.176.92.3`
* C. `172.17.23.43`
* D. `10.0.32.176`
* E. `192.140.2.118`

<details>
<summary> 📝 My answer 📝 </summary>

* C and E seem to be the only valid ones
* **C,E**
</details>

## 🟧 Question 13
* You need to restrict access to your EC2 instance-based application to only certain clients and only certain targets. Which three attributess of an incoming data packet are used by a security groupp to determine whether it should be allowed through (Choose three)

* A. Network port
* B. Source address
* C. Datagram header size
* D. Network protocol
* E. Destination address

<details>
<summary> 📝 My answer 📝 </summary>

* E is false, C is false
* **A,B,D**
</details>

## 🟧 Question 14
* How are IAM roles commonly used to ensure secure resource accessss in relation to EC2 instances?

* A. A role can assign processes running on the EC2 instance itself permissionn to access other AWS resources.
* B. A user can be given permission to authenticate as a role annd access all associated resources.
* C. A role can be associated with individual instance-based processes (Linux instances only), giving them permission to access other AWS resources.
* D. A role can give users and resources permission to access the EC2 instance.

<details>
<summary> 📝 My answer 📝 </summary>

* A - doesn't sound right
* B - seems right
* C - false
* D - correct
* **D**
</details>

## 🟧 Question 15
