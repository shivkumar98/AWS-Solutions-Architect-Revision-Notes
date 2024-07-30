<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 2.7 AWS Systems Manager
* The AWS Systems Manager enables you to automatically or manually peform actions against AWS resources and on-premises servers
* This can take over maintainence tasks, e.g. for EC2 instances, you can do tasks like upgrading installed packages, installing a new application or for other services, creating an image from EBS snapshot, disabling read access to S3 buckets.
* System Manager provides the following two capabilities:
  1. Actions
  2. Insights
  
<hr>

## 🟥 Actions
* Actions let you automatically or manually perform actions against your AWS resources.
* Actions must be defined in `documents` which are divided into 3 categories:
   1. `Automation` - actions you can run against your AWS resources
   2. `Command` - actions you run against your Linux or Windows instances
   3. `Policy` - processes for collecting inventory data from managed instances

### 🟡 Automation
* Automation enables you to perform actions against your AWS resources in bulk.
* E.g. you an restart multiple EC2 instances, update CloudFormation stacks and patch AMIs.
* Automation gives you the granularity to executing individual actions, i.e. whether to execute all actions in one swoop or item by item. This enables you to control what happens and
* Rate control can be used to specify what percentage of instances to affect at once.

### 🟡 Run Command
* Run commands let you execute tasks on your managed instances which would otherwise need you to login or use a third party tool to execute a script
* Systems Manager accomplishes these tasks using an agent installed on the instance (installed by default on most AMIs) or installed on your on-premisis server
* By default, Systems Manager doesn't have permissions to do anything on the instance.
* To permit core functionality, you need to apply an instance profile which contains the `AmazonSSMManagedInstanceCore` policy.
* There are AWS pre-configured documents for instances. E.g. `AWS-InstallApplication` document enables you to  install software on Windows machines
* You can target instances by their tag or select them manually

### 🟡 Session Manager
* Session Manager lets you achieve interactive Bash and Powershell  access to your Linux and Windows instances without loosening secuitry nor worrying about SSH keys
* You open a session using either the web console or AWS CLI.
* You must first install the Session Manager plugin to your local machine to use the AWS CLI to start a session.
* The Session Manager SDK has libraries for developers to create custom applications that connect to instances.

### 🟡 Patch Manager
* Patch manager helps you to automate the patching of your Linux and Windows instances. 
* Patch manager works with many of the popular operating systems and AMIs
* You can individually chooese instances to patch, or patch on tags or create a **patch group**
* Patch Manager uses patch baselines to define which patches to install, also whether a patch can be installed automatically or request approval
* You can create your own baseline to control which patches get installed
* A custom baseline contains one or more approval rules, even an auto approval delay which if the patch is not approved for the delayed amount gets applied automatically

### 🟡 State Manager
* Patch manager ensures all instances are all at the same level, State Manager ensures instances have the software you need and are configured to your needs.
* Generally, State Manager lets you automatically run commands and policy documents against your instance.
* E.g. you may want to install antivirus on your instances and then take a software inventory.
* You create an *association* whichdefines the command document to run, parameters, instances to target and schedule.
* Once an association is created, State Manager will execute it immediatelty against online instances, and optionally there after if it is scheduled.
* The `AWS-GatherSoftwareInventory` policy document includes the metadata you wish to collect from the instances.
* This policy can collect network configurations, file information, CPU information and registry values. 


## 🟥 Insights
* Insights offers aggregated data of health, operational details and compliance of AWS resources in a single area of AWS Systems Manager.
* Some insights are categorized accoording to AWS Resource groups (collections of resources in a AWS region)
* You can define a resource group based on tag keys and tag values

### 🟡 Built-In Insights
* These monitoring view are availabble to by default, including:
   1. **AWS Config Compliance** - insights shows the total number of resources in a resource group which are or are no compliant with AWS Config tules, as well as compliance by resource.
   2. **CloudTrail Events** - displays each resource in the group, resourcer type and last event that CloudTrail recorded
   3. **Personal Health Dashboard** - alerts when AWS experiences issue that may impact resources. E.g. some APIs experience delayed responses.
   4. **Trusted Advisor Recommendations** - can check your AWS environment for optimizations and recommendations for cost optimisation, performance, security, and fault tolerance. 

* All AWS customers get the following security checks for free:
  * Public access to S3 bucket
  * Security Groups with unrestricted port access
  * Whether you have created an IAM user
  * Whether MFA is enabled for root user
  * Public access to an EBS or RDS snapshot

## 🟥 AWS Systems Manager Inventory
* The Inventory Manager collects data from instance such as OS and application versions.
* It can collect the following data:
   - OS name and version
   - Applications and filenames, versions, and sizes
   - Network configuration, including IP and MAC address
   - Windows updates, roles, services, and registry values
   - CPU model, cores, and speed
* You can decide which instances to collect data from by creating a regionwide inventory association by executing `AWS-GatherSoftwareInventory` policy document.

### 🟡 Compliance
* Compliance insights show how the patch and association status of your instances stack up against the rules you've configured
* Patch compliance shows number of instances which are patched against baseline
* Association compliance shows number of instances which have has successfully executed associations against them.