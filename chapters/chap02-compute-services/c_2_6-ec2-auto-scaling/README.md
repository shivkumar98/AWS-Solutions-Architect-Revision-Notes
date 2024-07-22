<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 2.6 EC2 Auto Scaling
* Auto Scaling is a feature of EC2 instances which can help avoid application failure and recover from it if it occurs
* Auto Scaling automatically provision and starts a specified number of instances
* If an instance fails or gets terminated, auto scaling will replace thhe instance

<br>

* A **launch configuration** or **launch template** is used by auto scaling to configure the instances.
* Both of these allow you to configure parameters/scripts run on the instances when launchhed.
* Launch templates are newer than launch configurations


## 🟥 Launch Configurations
* Launch configurations are based on already created instance
* When you launch an instance, you specify configuration parameters:
   - AMI
   - Instance type
   - SSH key pair
   - Security groups
   - Instance profile
   - Block device mapping
   - EBS Volumes
   - Placement tenancy
   - User data (custom scripts to install your app)
* All of the aboce information is used to automaticaly launch an instance
* If you create a launch configuration from an existing instance, auto scaling will copy the settings for you - but you can also create it from scratch.
* Launch configurations are JUST for auto scaling - you can not manually launch an instance
* Once a launch configuration is created, it can not be modified⚠️

<hr>

## 🟥 Launch Templates
* Launch templates are more versatile - it can be both used for auto scaling and manually spin up a fleet
* Launch templates havce versioning, any time you update the template, AWS automatically creates a new version.

* I work on [Exercise 2.5 - Create a Launch Template](/exercises/chap02/e_2_5/)

<hr>

## 🟥 Auto Scaling Groups
* An **Auto Scaling group** is a group of EC2 instance which Auto Scaling manages 
* In order to create an Auto Scaling group, you must specify either the launch configuration or template which you created
* You must specify the number of instances you want to provisions via the launch configuration or template

<hr>

### 🟡 Specifying a Load Balancer
* You can use a load balancer when creating an Auto Scaling group.
* A load balancer is used to DISTRIBUTE traffic to your instances

### 🟡 Health Checks Against Application Instances
* Auto Scaling group will maintain the minimum or desired number of instance, if one becomes unhealth then it gets terminated and replaced
* EC2 health checks are used to determine if an instnace is healthy.
* In chapter 7 - CloudTrail, CloudWatch and AWS Config covers how EC23 automatically performs system and instance status checks
* These check for issues like memory exhaustion, filesystem corruption
* If an instance fails health check, load balancer will re-route the traffic away from instance

### 🟡 Configuring Scaling Policies
* You specify the follwing options:
   1. `Minimum` - the number of healthy instances will not go below this value
   2. `Maximum` - the number of healthy instance will not go above this value
   3. `Desired Capacity` - this is an optional setting

<hr>

## 🟥 Auto Scaling Options
* An Auto Scaling Group enables you to maintain a desired minimum number of instances.
* Auto Scaling also offers other options to scale out the number of instances to meet demand

### 🟡 Manual Scaling
* Auto scaling automatically adjusts when you change the min/max number of instance

### 🟡 Dynamic Scaling Policies
* Most AWS-managed resources are elastic, these include S3, loadbancers, Internet gateways, and NAT gateways.
* AWS is responsible for ensuring that resources are available while they continue to perform
* Running out of instance resource (CPU utilisation, memory, disk space) will lead to application failure.
* To ensure instances are not over burdened, dynamic scaling policies automatically provision more instance before this can occur
* Auto Scaling generate the following aggregate metrucs for all instances within the group
   - Aggregate CPU utilisation
   - Average request count per target
   - Average network bytes in 
   - Average network bytes out

* You can also use metrics from CloudWatch logs
  * E.g. you app can generate logs which dictate how long a process took to complete
  * If it takes too long, Auto scaling can spin up new instances.
* Dynamic scaling policies work by monitoring a CloudWatch alarm
  * There are three dynamic scaling policies: simple, step and target tracking
  
### 🟡 Simple Scaling Policies
* With simple scaling policies, whenever a metric goes above threadhold, Auto Scaling will increase the desired capacity.
* The amount it increases depends on ADJUSTMENT TYPE:
   1. `ChangeInCapacity` - increases desired capacity by specified value
   2. `ExcactCapacity` - will set desired capacity to value regardless of existing value
   3. `PercentageChangeInCapacity` - increase desired capacity by percentage of existing value
* When Auto Scaling adjustment, it will wait a cooldown period before execuuting the policy again
  * **Default cooldown is 300 seconds**, but it can also be set `0` to disable it
* Auto Scaling will NEVER let capacity exceed maximum capacity

### 🟡 Step Scaling Policies
* Step scaling enables you to scale out your instances based on a metric from cloudwatch
  * E.g. you can use CPU utilisation to specify to use 10 instances if CPU util hits 60%, 30 instances if CPU utili hits 70%, ... etc
* You specify a step adjustment with:
  * **Lower bound**
  * **Upper bound**
  * **Amount to scale, depending on adjustment type**
* E.g. you could have the following step adjustment:
  * Lower bound: 50%
  * Upper bound: 60%
  * Amount to scale: ChangeInCapacity of 2
* Suppose it hits 55%, it will check if `50% <= 62 < 60%` and add to more instances to desired capacity
* There cannot be overlap in the boundaries, so you could specify another step adjustment with lower bound of 60%
* You can also set upper bound to `null` if you want it to go to infinity
* You can also optionally specify a **warm-up time**, which is how long Auto Scaling will wait until adding new instances.
* There is NO cooldown period in step scaling policies⚠️

### 🟡 Target Tracking Policies
* Target Tracking Policies can be more simplified compared to step scaling policies
* You just select a metric and target value, and Auto Scaling will create a Cloud Watch Alarm and a scaling policy to adjust the number of instances to keep the metric near that target.
* You can also scale inwards to delete instances to maintain a target value
* You must select a metric which changes propotionally with instance availability.

### 🟡 Scheduled Actions
* You can adjust your capacity proactively if you can observe patterns in demand ensuring there is enough resource before demand hits
* **To create a scheduled action**, you must specify the following:
  - A min, max or desired capacity
  - Start date and time
* You can also set the policy to run at regular intervals, can also set an end time which automatically deletes the scheduled policy