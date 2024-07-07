# Chapter 1 - Review Questions Attempt 1

## Results:

* Date: 07/07/2024
* Score: 8/11 (73%)

| Question # | Correct  |
| ---------- | -------  |
| 1          |  ✅        |
| 2          |  ✅        |
| 3          |  ✅        |
| 4          |  ❌        |
| 5          |  ✅        |
| 6          |  ❌        |
| 7          |  ✅        |
| 8          |  ✅        |
| 9          |  ❌        |
| 10         |  ✅        |
| 11         |  ✅        |


## 🟧 Question 1

❓ Your developers want to run fully provisioned EC2 instances to support their application code deployments but prefere not to have to worry about manually configuring and launching the necessary infrastructure. Which of the following should they use❓


* A. AWS Lambda
* B. AWS Elastic Beanstalk
* C. Amazon EC2 Auto Scaling
* D. Amazon Route 53

<details>
<summary> 📝 My answer 📝 </summary>

* **B**✅✅✅✅
* You can use Elastic Beanstalk to take care of deployment details
</details>

<hr>


## 🟧 Question 2

❓ Some of your application's end users are complaining of delays when accessing your resources from remote geographic locations. Which of these service would be the most likely to help reduce the delays ❓


* A. AWS CloudFront
* B. Amazon Route 53
* C. Elastic Load Balancing
* D. Amazon Glacier

<details>
<summary> 📝 My answer 📝 </summary>

* I do not think its Elastic Load Balancing, as that is to do with scaling with demand
* Route 53 is to do with domain registration, and Amazon Glacier is about storage
* So I think it's A
* **A**✅✅✅✅
* * CloudFront is a CDB - ensuring low latency delivery of content
</details>

<hr>

## 🟧 Question 3

❓ Which of the following is the best use-case scenario for Elastic Block Store? ❓

* A. You need a cheap and reliable place to store files your application can access.
* B. You need a safe place to store backup archives from your local servers.
* C. You need a source for on-demand compute cucles to meet fluctuating demand for your application
* D. You need persistent storage for the filesystem run by your EC2 instance.

<details>
<summary> 📝 My answer 📝 </summary>

* I think its D
* **D**✅✅✅✅
* Elastic Block Store gives access to virtual block drives which you can install filesystems.
</details>

<hr>


## 🟧 Question 4

❓ (CHOOSE TWO) You need to integrate your company's local user access controls with some of your AWS reosource. Which of the following can help you control the way your local users access your AWS services and administration console?❓

* A. AWS Identity and Acess Management (IAM)
* B. Key Management Service (KMS)
* C. AWS Directory Service
* D. Simple WorkFlow (SWF)
* E. Amazon Incognito

<details>
<summary> 📝 My answer 📝 </summary>

* A is defintely true
* I don't think D or E are true
* So I would guess B is correct.
* **A,B**❌❌❌❌
* **CORRECT ANSWER: A,C**
* The AWS Directory Service enables you to allows users to access to resources using THIRD PARTY AUTHENTICATION SERVICES.
* The Key Management Service is used for creating and managing encryption keys
</details>

<hr>

## 🟧 Question 5

❓ The data consumed by the application your planning will require more speed and flexibility that you can get from a closely defined relational database structure. Which AWS databbase service should you choose? ❓

* A. Relational Database Service (RDS)
* B. Amazon Aurora
* C. Amazon DynamoDB
* D. Key Management Service (KMS)

<details>
<summary> 📝 My answer 📝 </summary>

* If flexibility AND speed is necessary, dyanoDB would be best option
* **C**✅✅✅✅
</details>

<hr>

## 🟧 Question 6

❓ You've launched an EC2 application server instance in the AWS Ireland region and you need to access it from the web. Which of the following is the correct endpoint address that you should use?❓

* A. `compute.eu-central-1.amazonaws.com`
* B. `ec2.eu-central-1.amazonaws.com`  
* C. `elasticcomputecloud.eu-west-2.amazonaws.com`
* D. `ec2.eu-west-1.amazonaws.com`

<details>
<summary> 📝 My answer 📝 </summary>

* EC2 is a compute service
* I don't know which answer is correct so I randomly guess C
* **C**❌❌❌❌
* **CORRECT ANSWER: D**
* EC2 endpoints always have a prefix of `ec2`
* And the AWS region of Ireland is `eu-west-1`
</details>

<hr>

## 🟧 Question 7

❓ When working to set up your first AWS deployment, you keep coming across the term ***availability zone***. What exactly is an avaialability zone?❓

* A. An isolated physical data center within an AWS region
* B. A region containing multiple data centers
* C. A single network subnet used by resource within a single region
* D. A single isolated server room within a data center
  
<details>
<summary> 📝 My answer 📝 </summary>

* Bit of a guess it is A
* **A**✅✅✅✅
* There can be multiple data centers in a geographical areas but an AZ is a single one!
</details>

<hr>

## 🟧 Question 8

❓ As you plan your multi-tiered, multi-instance AWS application, you need to effectively organise your instances and configure their network connectivity and access control. Which tool will let you do that? ❓

* A. Load Balancing
* B. Amazon Virtual Private Cloud (VPC)
* C. Amazon CloudFront
* D. AWS endpoints

<details>
<summary> 📝 My answer 📝 </summary>

* This sounds like a security group
* I am going to guess VPC
* **B**✅✅✅✅
</details>

<hr>

## 🟧 Question 9

❓ You want to be sure that the application you're building using EC2 and S3 resources will be reliable enough to meet the regulatory standards required within your industry. What should you check? ❓

* A. Historical uptime log records
* B. The AWS Program Compliance Tool
* C. The AWS service level agreement (SLA)
* D. The AWS Compliance Programs documentation page
* E. The AWS Shared Responsibility Model

<details>
<summary> 📝 My answer 📝 </summary>

* A, C and E are defintely false
* I would imagine the documentation page would be most up to date
* **D**❌❌❌❌
* **CORRECT ANSWER: C**
* This question is asking about RELIABILITY
* The SLA tells us the minimum availability of different AWS services!
</details>
<hr>

## 🟧 Question 10

❓ Your oranization's operations team members need a way to access and administer your AWS infrastructure via your loacal command line or shell scripts. Which of the following tools will let them do that? ❓

* A. AWS Config
* B. AWS CLI
* C. AWS SDK
* D. The AWS Console

<details>
<summary> 📝 My answer 📝 </summary>

* B is definitely the answer!
* **B**✅✅✅✅
* AWS Config is for editing and auditing your AWS account resources
</details>
<hr>

## 🟧 Question 11

❓ While building a large AWS-based application, your company has been facing configuration problems they can't solve on their own. As a result, they need direct access to AWS support for development and IT team leaders. Which support plan should you purchase? ❓

* A. Business
* B. Developer
* C. Basic
* D. Enterprise

<details>
<summary> 📝 My answer 📝 </summary>

* It's either Business or Enterprise
* **A**✅✅✅✅
* The Developer only can give ONE userf access to a support associate
</details>
<hr>