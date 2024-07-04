# 🧠 1.2 The AWS Cloud
* There are an increasing number of services being added to the AWS console
* As a Solution Architect, the focus should be on core service CATEGORIES
  
<br>

## 🟥 AWS categories:

| Category  | Function              |
| ----------- | --------------------------------- |
| **Compute**   | Services which can replace traditional need for local physical servers. The Compute services have configurations like autoscaling, load balancing, containers |
| **Networking** | Application Connectivity, access control and remote connections |
| **Storage** | Storage solutions for immedia acces and long term backup requirementes |
| **Database** | Data solutions for multiple formats: Relational, SQL, and Cache |
| **Application Management** | Monitoring, Auditing, congifuring AWS account services and resources |
| **Security and Identity** | For managin authentication and authorisation, data + connection encryption, and integration with third party systems |

<br>

## 🟥 Compute Services:

| Service         | Function                 |
| ----------------|--------------------------|
| **EC2 (Elastic Compute Cloud)** | EC2 server instances are virtual versions of servers you would use for a local datacenter. These can bbe provisioned with storage, memory, network and CPU profiles. These can be used to run a web serer or run a multi-fleet architecture. |
| **Lamba** | This is a serverless architecture which provide a 24/7 public facing service which can respond to network events and trigger execution of pre-defined code. |
| **Auto Scaling** | Automatic up or down scaling of EC2 instances can be defined to match demands. |
| **Elastic Load Balancing** | Network traffic can be diverted to multiple web servers to ensure a single web server is not overwhelmed by demand. Can also redirect traffic away from failed servers |
| **Elastic Container Service** | Compute workloads can be provisioned for containerisation technologies (like Docker, Kubernetes). |
| **Elastic Beanstalk** | Elastic Beanstalk can take your pushed code and automatically launch all the needed services in the background (e.g. you can upload a WAR file and deploy your application fully) |

<br>

## 🟥 Networking Services: 

| Service           | Function                       |
|--------------------|--------------------------------|
| **Virtual Private Cloud (VPC)** | These are networking environments designed to host EC2 and RDS instances. The VPC enables yhou to define inbound and outbound networking access |
| **Direct Connect** | This is a fast and secure way of directly accessing AWS based VPCs |
| **Route 53** |  This is a AWS DNS service which lets you manafe domain and record adminstration, routing protocols, and health checks, which are fully integrated with the rest of your AWS resources |
| **CloudFront** | This is Amazon's distrubbuted global content delivery network (CDN). CDNs can cache site content around the world to allow for efficiency and low latency |

<br>

## 🟥 Storage Services: 

| Service          | Function                        |
|-------------------|---------------------------------|
| **S3 (Simple Storage Service)** | S3 has affordable and reliable object storage ideal for backup and data storage. Can also be used to store files needed for AWS configuration (properties files) |
| **S3 Glacier** | This is intended for long-term, affordable and reliable storage of large data archives. Data is not accessible immediately, delays range betweeen hours and days. |
| **Elastic Block Store (EBS)** | EBS provides persistent virtual storage drives which host OS and working data for an EC2 instance. |
| ***Storage Gateway** | This provide on premises application to cloud storage, this is a hyrid solution. Good for data backup and disaster recovery |

<br>

## 🟥 Database Services: 

| Service     | Function                             |
|--------------|--------------------------------------|
| **Relational Database Service (RDS)** | This service helps you build reliale database instances using a varierty of database engines like MySQL, SQL Server, Oracle or Amazon's Aurora |
| **DynamoDB** | This is a simple and fast non-relational database |

<br>

## 🟥 Application Management Services: 

| Service      | Function                          |
|--------------|-----------------------------------|
| **CloudWatch**   | This can be used to monitor resource utilisation and process performance. Can be configured to send a message or trigger a response |
| **CloudFormation**  | Using templates, CloudFormation enables you to deploy complex AWS deployments. This ensures standardisation, improves speed of launch process |
| **CloudTrail** | Collects records of all your account's API events. |
| **Config** | This service helps with change management and compliance. You state a desired configuration state, and Config evaluates statesw against the desired state. |

<br>

## 🟥 Security and Identity Services: 

| Service      | Function                             |
|--------------|--------------------------------------|
| **Identity and Access Management (IAM)** | Using users, groups, roles and policies, you can control who can access/modify your AWS resources. |
| **Key Managemeng Service (KMS)** | KMS is used to administrate and create encryption keys used by any of the AWS resources. |
| **Directory Service** | Enables integration of active directories with AWS resources like Amazon Cognito and Microsoft AD domains |

<br>

## 🟥 Application Integration Services: 

| Service      | Function                                |
|--------------|-----------------------------------------|
| **Simple Notification Service (SNS)** | this is a notification service which can automate the pulishing of alert topics to other services |
| **Simple Workflow (SWF)** | Allows you to coordinate tasks between a range of AWS services or even non-digital events |
| **Simple Queue Service (SQS)** | Can be used to decouple process event driven appplication (like banking applications). Data contained in SQS messages will be reliably delivered. |
| **API Gateway** | Allows you to create and manage secure and reliable APIs for AWS platformed applications. |