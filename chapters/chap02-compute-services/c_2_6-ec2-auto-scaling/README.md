# 🧠 2.6 EC2 Auto Scaling
* Auto Scaling is a feature of EC2 instances which can help avoid application failure and recover from it if it occurs
* Auto Scaling automatically provision and starts a specified number of instances
* If an instance fails or gets terminated, auto scaling will replace thhe instance

<br>

* A **launch configuration** or **launch template** is used by auto scaling to configure the instances.
* Both of these allow you to configure parameters/scripts run on the instances when launchhed.
* Launch templates are newer than launch configurations

<br>

## 🟥 Launch Configurations
* Launch configurations are based on already created instance
* When you launch an instance, you specify configuration parameters:
   - AMI
   - Instance type
   - SSH key pair
   - Security groups
   - Instancce profile
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

<br>

* I work on [Exercise 2.5 - Create a Launch Template](/exercises/chap02/e_2_5/)

<hr>

## 🟥 Auto Scaling Groups

<hr>

## 🟥 Auto Scaling Options

<hr>

