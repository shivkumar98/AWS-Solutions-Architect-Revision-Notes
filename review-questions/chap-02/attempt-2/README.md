# Chapter 2 - Review Questions Attempt 2

## Results:

* Date: 19/10/2024
* Score: 23/24 (96%)

| Question # | Correct  |
| ---------- | -------  |
| 1          |  ✅     |
| 2          |  ✅     |
| 3          |  ✅     |
| 4          |  ✅     |
| 5          |  ✅     |
| 6          |  ✅     |
| 7          |  ✅     |
| 8          |  ✅     |
| 9          |  ✅     |
| 10         |  ✅     |
| 11         |  ✅     |
| 12         |  ✅     |
| 13         |  ❌     |
| 14         |  ✅     |
| 15         |  ✅     |
| 16         |  ✅     |
| 17         |  ✅     |
| 18         |  ✅     |
| 19         |  ✅     |
| 20         |  ✅     |
| 21         |  ✅     |
| 22         |  ✅     |
| 23         |  ✅     |
| 24         |  ✅     |

## ✏️ Summary Notes ✏️

## 🟧 Question 1
❓ You need to deploy multiple EC2 Linux instances that will provide your company with virtual private networks (VPNs) using software called OpenVPN. Which of the following will be the mmost efficient solutions? (CHOOSE TWO) ❓

* A.  Select a regular Linux AMI and bootstrap it using user data that will install and configure OpenVPN package on the instance and use it for your VPN instances.
* B. Search the community AMI for an official AMI provided and supported by the VPN company.
* C. Search the AWS marketplace to see whether there's an official AMI provided and supported by the OpenVPN company
* D. Select a regular Linux AMI and SSH to manually install and configure the OpenVPN package
* E. Create a site-to-site VPN connection from the wizard in the AWS VPC dashboard

<details>
<summary> 📝 My answer 📝 </summary>

* E is not valid
* D is not efficient
* A is the best and C comes second up
* **A,C**✅✅✅✅
* Community AMIs are not official and may not support version of Open VPN
</details>

<hr>


## 🟧 Question 2
❓ As part of your company's long term cloud migration strategy, you have a VMware virtual machine in your local infrastructure that you'd like to copy to your AWS account and run as an EC2 instance. Which of thhe following will be necessary steps? (CHOOSE TWO)❓

* A. Import your virtual machine to your AWS region using secure SSH tunnel
* B. Import the virtual machine using VM Import/Export.
* C. Select the imported VM from among your private AMIs and launch an instance.
* D. Select the imported VM from the AWS Marketplace AMIs and launch an instance.
* E. Use the AWS CLI to securely copy your virtual machine image to an S3 bucket within the AWS region you'll be using.

<details>
<summary> 📝 My answer 📝 </summary>

* I don't think an image can be imported via SSH.
* My guess would be B and C
* **B,C**✅✅✅✅
</details>

<hr>


## 🟧 Question 3
❓ Your AWS CLI command to launch an AMI as an EC2 instance has failed, giving you an error message that includes `InvalidAMIID.NotFound`. What of thhe following is the most likely cause? ❓

* A. You haven't configured the `~/.aws/config` file
* B. The AMI is being updated and temporarily unavailable.
* C. Your key pair file has been given the wrong (overly) permissions
* D. The AMI you specified exists in a different region than the one you've currently specified.

<details>
<summary> 📝 My answer 📝 </summary>

* **D**✅✅✅✅
</details>

<hr>

## 🟧 Question 4
❓ The sensitivity of the data your company works with means that the instances you run must be secured through complete physical isolation. What should you specify as you configure a new instance ❓

* A. Dedicated Host tenancy
* B. Shared tenancy
* C. Dedicated Instance tenancy
* D. Isolated tenancy

<details>
<summary> 📝 My answer 📝 </summary>

* B is definitely wrong
* D is not a thing
* **A**✅✅✅✅
*  Dedicated Instance tenancy means the instance will be in a server allocated to a single customer, but this does not meet the complete physical isolation necessary for this question
</details>

<hr>


## 🟧 Question 5
❓ Normally, two instances running `m5.large` instance types can handle the traffic accessing your online e-commerce site, but you know that you will face short, unpredictable periods of high demand. Which of the following choices should you implement? (CHOOSE TWO) ❓

* A. Configure autoscaling
* B. Configure load balancing
* C. Purchase two `m5.large` instances on the spot market and as many on-demand instances as necessary.
* D. Shut down your large `m5.large` instances and purchase instances using a more robust innstance type to replace them.
* E. Purchase two `m5.large` reserve instances and as many on-demand instances as necessary

<details>
<summary> 📝 My answer 📝 </summary>

* **A,E**✅✅✅✅
</details>

<hr>


## 🟧 Question 6 
❓ Which of the following use cases would be most cost effective if run using spot market instances ❓

* A. Your e-commerce website is built using a publicly available AMI.
* B. You provide high-end video rendering services using a fault tolerant process that can easily manage a job that was unexpectedly interrupted.
* C. You're running a backend database that must be reliably updated to keep track of critical transactions.
* D. Your deployment runs as a static website on S3.

<details>
<summary> 📝 My answer 📝 </summary>

* **B**✅✅✅✅
</details>

<hr>

## 🟧 Question 7
❓ In the course of a routine infrastructure audit, your organization discovers that some of your running EC2 instances are not configured properly and must be updated. Which of the following configuration details cannot be change on an existing EC2 instance ❓

* A. AMI
* B. Instance tyepe
* C. Security group
* D. Public IP address

<details>
<summary> 📝 My answer 📝 </summary>

* Instance type can be modified, but will not take effect until instance is shutdown
* Security groups can be modified and take effect immediately
* **A**✅✅✅✅
</details>

<hr>


## 🟧 Question 8
❓ For an account with multiple resources running as part of multiple projects, which of the following key/value combination examples would make for the most effective identification convention for resource tags? ❓

* A. `servers:server1`
* B. `project1:server1`
* C. `EC2:project:server1`
* D. `server1:project1`

<details>
<summary> 📝 My answer 📝 </summary>

* **B**✅✅✅✅
</details>

## 🟧 Question 9
❓ Which of the following EBS options will you need to keep your data-hungry application that requires up to 20,000 IOPS happy? ❓

* A. Cold HDD
* B. General purpose SSD
* C. Throughput-optimized HDD
* D. Provisioned-IOPS SSD

<details>
<summary> 📝 My answer 📝 </summary>

* **D**✅✅✅✅
</details>

<hr>


## 🟧 Question 10
❓ Your organization needs to introduce Auto Scaling to its infrastructure and needs to generate a "golden image" AMI from an existing EBS volume. This image will need to be shared among multiple AWS accounts belonging to your organisation. Which of the following steps will get you there? (CHOOSE THREE) ❓

* A. Create an image from a detached EBS volume, use it to create a snapshot, select your new AMI from your private collection, and use it for your launch configuration.
* B. Create a snapshot of the EBS root volume you need, use it for create an image, select your new AMI from your private collection, and use it for your launch configuration.
* C. Create an image from the EBS volume attached to the instance, select your new AMI from your private collection, and use it for your launch configuration.
* D. Search the AWS Marketplace for the appropiate image and use it for your launch configuration.
* E. Import the snapshot of an EBS root volume from a different AWS account, use it to create an image, select your new AMI from your private collection, and use it for your launch configuration.

<details>
<summary> 📝 My answer 📝 </summary>

* A is false as you cannot take an image from a detached EBS volume
* D is false
* **B,C,E**✅✅✅✅
</details>

<hr>

## 🟧 Question 11
❓ Which of the following are benefits of instance store volumes? (CHOOSE TWO)❓

* A. Instance volumes are physically attached to the server that's hosting your instance, allowing faster data access.
* B. Instance volumes can be used to store data even after the instance is shutdown
* C. The use of instance volumes does not incur costs (beyond those for the instance itself)
* D. You can set termination protection so that an instance volume can't be accidentally shut down.
* E. Instance volumes are commonly used as a base for the creation of AMIS

<details>
<summary> 📝 My answer 📝 </summary>

* There is absolutely no protectionf for instance store volumes, so D is wrong
* **A,C**✅✅✅✅
</details>

<hr>

## 🟧 Question 12
❓ According to default behaviour (and AWS recommendations), which of the following IP addresses could be assigned as the private IP for an EC2 instance? (CHOOSE TWO)❓

* A. `54.61.211.98`
* B. `23.176.92.3`
* C. `172.17.23.43`
* D. `10.0.32.176`
* E. `192.140.2.118`

<details>
<summary> 📝 My answer 📝 </summary>

* C is valid
* D is valid
* E is wrong as the range is `192.168.0.0` - `192.168.255.255`
* A and B are not in range as they begin with 54 and 23
* **C,D**✅✅✅✅
* Valid range includes `172.16.0.0` - `172.31.255.255`
</details>

<hr>

## 🟧 Question 13
❓ You need to restrict access to your EC2 instance-based application to only certain clients and only certain targets. Which three attributes on an incoming data packet are used by a security group to determine whether it should be allowed thhrough (CHOOSE THREE) ❓


* A. Network port
* B. Source Address
* C. Datagram header size
* D. Network protocol
* E. Destination address

<details>
<summary> 📝 My answer 📝 </summary>

* **C,E**❌❌❌❌
* NOTE: I misread the question!
</details>

<hr>

## 🟧 Question 14
❓ How are IAM roles commonly used to ensure secure resource access in relation to EC2 instances? ❓

* A. A role can assign processes running on the EC2 instances itself permission to access other AWS resources.
* B. A user can be given permission to authenticate as a role and access all associated resources.
* C. A role can be associated with individual instance based processes (Linux instances only), giving them permission to access other AWS resources.
* D. A role can give users and resource permission to access the EC2 instance.

<details>
<summary> 📝 My answer 📝 </summary>

* Roles cannot be associated with instance processes, only resources themselves.
* **D**✅✅✅✅
</details>

<hr>


## 🟧 Question 15
❓ You have an instance running within a private subnet that needs external network access to recieve software updates and patches. Which of thhe following can securely provide that access from a public submet within the same VPC? (CHOOSE TWO) ❓

* A. Internet gateway
* B. NAT instance
* C. Virtual private gateway
* D. NAT gateway
* E. VPN

<details>
<summary> 📝 My answer 📝 </summary>

* NAT instance and NAT gateway are used to give restricted access to internet
* **B,D**✅✅✅✅
</details>

<hr>


## 🟧 Question 16
❓ What do you have to do to securely authenticate to the GUI console of a Windows EC2 session? ❓

* A. Use the private key of your key pair to initiate an SSH tunnel session
* B. Use the public key of your key pair to initiate an SSH tunnel session
* C. Use the public key of your key pair to retrieve the password you'll use to log in.
* D. Use the private key of your key pair to retrieve the password you'll use to log in.

<details>
<summary> 📝 My answer 📝 </summary>

* SSH connections are typical for Linux instances.
* For windows, you need to decrypt the adminstrator password to connect via RDP
* **D**✅✅✅✅
</details>

<hr>

## 🟧 Question 17
❓ Your application deployment includes multiple EC2 instances that need low-latency connections to each other. Which of the following AWS tools will allow you to locate EC2 instances closer to each other to reduce network latency? ❓

* A. Load balancing
* B. Placement groups
* C. AWS Systems Manager
* D. AWS Fargate

<details>
<summary> 📝 My answer 📝 </summary>

* **B**✅✅✅✅
</details>

<hr>

## 🟧 Question 18
❓ To save configuration time and money, you want your application to run only when network events trigger it but shut down immediately after. Which of thhe following will do that for you? ❓


* A. AWS Lambda
* B. AWS Elastic Beanstalk
* C. Amazon Elastic Container Service (ECS)
* D. Auto Scaling

<details>
<summary> 📝 My answer 📝 </summary>

* **A**✅✅✅✅
</details>

<hr>


## 🟧 Question 19
❓ Which of the following will allow you to quickly copy a virtual machine image from your local infrastructure to your AWS VPC? ❓

* A. AWS Simple Storage Service (S3)
* B. AWS Snowball
* C. VM Import/Export
* D. AWS Direct Connect

<details>
<summary> 📝 My answer 📝 </summary>

* **C**✅✅✅✅
</details>

<hr>


## 🟧 Question 20
❓ You've configured an EC2 Auto Scaling group to use a launch configuration to provision and install an application on several instances. You now need to reconfigure Auto Scaling to install an additional application on new instances. Which of the following should you do? ❓

* A. Modify the launch configuration.
* B. Create a launch template and configure the Auto Scaling group to use it.
* C. Modify the launch template.
* D. Modify the CloudFormation template.

<details>
<summary> 📝 My answer 📝 </summary>

* **B**✅✅✅✅
</details>

<hr>

## 🟧 Question 21
❓ You create an Auto Scaling group with a minimum group size of 3, a maximum group size of 10, and a desired capacity of 5. You then manually terminate two instances in the group. Which of the following will Auto Scaling do? ❓

* A. Create two new instances.
* B. Reduced the desired capacity to 3.
* C. Nothing.
* D. Increment the minimum group size to 5

<details>
<summary> 📝 My answer 📝 </summary>

* Auto scaling does not have effect on configuration settins.
* **A**✅✅✅✅
</details>

<hr>


## 🟧 Question 22
❓ You're running an application that recieves a spike in traffic on the first day of every month. You want to configure Auto Scaling to add more instances before the spike begins and then add additional instances in proportion to the CPU utilistion❓

* A. Target tracking policies
* B. Scheduled actions
* C. Step scaling policies
* D. Simple scaling policies
* E. Load balancing

<details>
<summary> 📝 My answer 📝 </summary>

* Scheduled actions is ideal as we know there's a pattern in increased traffice
* Step scaling is ideal to proportionally handle CPU utilisation in response to how much a cloudwatch alarm is exceeded
* **B,C**✅✅✅✅
</details>

<hr>

## 🟧 Question 23
❓ As part of your new data backup protocols, you need to manually take EBS snapshots of several hundred volumes. Which type of Systems Manager document enables you to do this? ❓

* A. Command
* B. Automation
* C. Policy
* D. Manual

<details>
<summary> 📝 My answer 📝 </summary>

* **B**✅✅✅✅
</details>

<hr>


## 🟧 Question 24
❓ You want to launch and manage a complex microservices container workload in AWS but you want to avoid as many configuration headaches as possible. You figure you'll be fine with whatever defaults you're offered. Which of these platforms is your best choice? ❓

* A. Amazon Elastic Kubernetes Services
* B. AWS Fargate
* C. Amazon EKS Distro
* D. Amazon Elastic Container Service

<details>
<summary> 📝 My answer 📝 </summary>

* AWS Fargate abstracts alot of the configuration details of Amazon Elastic Kubernetes Services and Amazon Elastic Container Service
* **B**✅✅✅✅
</details>

<hr>
