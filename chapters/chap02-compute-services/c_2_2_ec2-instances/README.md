# 🧠 2.2 EC2 Instances

* Like a physical server, you will have access to storage, memory and a network interface.

<hr>

## 🟥 Provisioning Your Instance
* Before launching your instance, you must configure it's storage, hardware, operating system.
* The **Amazon Machine Image (AMI)** determines the operating system.
* And the **Instance Type** determines the hardware specification

### 🟡 Amazon Machine Images

* There are four kinds of AMIs:
   1. Amazon Quick Start AMIs - the quick start tab on the launch instance page includes popular releases; this includes having Linux, Windows, MacOS. These are official and up to date
   2. AWS Marketplace AMIS: AMIS from market place, which are official and vendored by industry experts
   3. Community AMIS: independently maintained and for very specific use case.
   4. Private AMIS: these are your own images from your own instance deployments. These are images which you specifically determine and match your needs.

* A specific AMI may only be available in one region - most likely there is an equivalent one in another region, but you must be careful of invoking a particular AMI ID.

* IMPORTANT NOTE: you may be billed hourly amounts or license fees for using a particular AMI with bundled software.

<br>

### 🟡 Instance Types
* The instance type determines what hardware resources Amazon will allocate your instance.
* You should balance cost against power, memory and storage space.
* You can easily modify your instance type by stopping it, changing the type, and restarting it.
* There are over 60 types of instances, they are organised into **INSTANCE TYPE FAMILIES**:

| Instance Type Family | Types                                   |
|----------------------|-----------------------------------------|
| **General purpose**      | Mac, T4g, T3, T2, M6g, M6i, M6a, M5, M5a, M5n, M5zn, M4, A1 |
| **Compute optimised**    | C7g, C6g, C6i, C6a, Hpc6a, C5, C5a, C5n, C4 |
|  **Memory optimised**    | R6g, R6i, R5, R5a, R5b, R5n, R4, X2gd, X2idn, X2iedn, X2iezn, X1e, X1, High Memory, z1d |
| **Accelerated computing** | P4, P3, P2, DL1, Trn1, lnf1, G5, G5g, G4dn, G4ad, G3, F1, VT1 |
| **Storage optimized** | Im4gn, Is4gen, I4i, I3, I3en, D2, D3, D3en, H1 |

<br>

Here is a brief description of the instance type families:
1. **General Purpose:** 
   - this family includes T3, T2, M5 and M4 Types. 
   - provide a balance of memory, compute and network resources
   - the T2 types start from `t2.nano` (one virutal CPU and 0.5 GB of memory) to `t2.2xlarge` (eight CPUs and 32 GB of memory)
   - `t2.nano` is part of free tier, so good for experimentation.
   - T4g and M6g instance types use the AWS-designed Arm-based Graviton processor.
   - T4g ranges from `tf6.nano` (0.5 GB memory, 2 CPUs) to `t4g.2xlarge` (32 GB, 8 CPUs)
2. **Compute Optimized:**
   - this famaily is intended for high demanmd web servers or machine learning workloads
   - this famiy includes C6i machines which range from `c6i.large` to `c6i.metal` (128 CPUs, 256 GB, and 50 Gbps network bandwith)
3. **Memory Optimized:**
   - these work well for intensive database, data analysis and caching operations
   - The R6i runs on **3rd gen Xenon Scalable** processors which have higher memory bandwich and networking capacity
   - The `X1e`, `X1` and `R4` types have up to 3.9 TB of DRAM and low-latency SSD volumes attached
4. **Accelerated Computing:**
   - The `P4`, `P3`, `G5` and `F1` types off higher performing general purpose graphics processing unit (GPGPU) performancer
   - These instance utitlize high performance NVIDIA GPUs.
   - This family is intended for high performance computing and high end medical-research, financial, engineering, AI workloads
5. **Storage Optimized:** the H1, I3, D2 types offer fast read/writes to EBS instance storage volumes. This family is ideal for heavyweighted data processing and distributed filesystems.

* AWS continually changes the instance type names, it's important to visit the instance types page before provisioning projects: [https://aws.amazon.com/ec2/instance-types/](https://aws.amazon.com/ec2/instance-types/) 

<br>

### 🟡 Configuring an Environment for Your Instance
* Determining the environment of your instance is very important, there are three details to get right:
   1. Geographic Location
   2. Virtual Private Cloud (VPC)
   3. Tenancy Model

**AWS Regions**
* You will want your EC2 instance geographically close to majority of your customers, or within a jurisdiction your data must be compliant to
* When managing EC2 instances, you must ensure you are in the correct AZ - this is congfigurable by a dropdown in the Console.
* Costs and functionality vary between regions

**VPCs**
* VPCs are network organisers
* It is easy to setup VPCs to isolate your EC2 instance from all other resources.
* You can provision a VPC for free if it doesn't incorporate a NAT or VPN
* I will learn more about VPCs in chapter 4

**Tenancy**
* By default EC2 instances have a share tenancy configuration - meaning you will be sharing physical the SAME hardware with other hosted instances.
* You can choose to have your own dedicated hardware using the `Dedicated Instance` option


* I work on the following exercises:
   - [🏋️ Exercise 2.1 Launch an EC2 Linux Instance and Login Using SSH 🏋️](/exercises/chap02/e_2_1/) 
   - [🏋️ Exercise 2.2 Access the Free Capacity of a Running Instance and Change It's Instance Type 🏋️](/exercises/chap02/e_2_2/)


<hr>

## 🟥 Configuring Instance Behavior
* Using `user data` (found in instance configuration) you can execute commands on your instance as it bootups - this known as bootstrapping
* You can use scripts to bring your instance to a desired state.
* You can use simple commands to install a web server and setup its root
* Or you can use `Puppet Enterprise` as a working node.

<hr>

## 🟥 Placement Groups
* AWS will create a default profile which attempts to spread your instances across AWS's infrastructure which is optimal for MOST use cases.
* AWS `Placement Groups` allow you to specify nonstandard profile to meet your needs.
* There are three kinds of placement groups:
1. `Cluster` groups - this will launch each instance into a SINGLE AZ within close proximity to each other. This is ideal for low latency networking
2. `Spread` groups - this is ideal for reliability and availability of servers. Instances are spread across distinct hardware racks and even AZs to mitigate risk of data failure or service loss.
3. `Partition` groups - partitioned instances are instances which are associated with each other but kept physically seperate from other partitions.


<hr>

## 🟥 Instance Pricing
* There are 2 pricing models for EC2 instances:
   1. `On Demand` - for deployments less than 12 months, this is the most expensive option
   2. `Reserved Instance` (Savings Plans)- this is a reservation between 1-3 years.

* Amazon's spot market can save you even more money, you can specify a bid and your instance will automatically be launched if a spot is available below or equal to your bid
* I will learn more about this in chapter 13
* I work on [🏋️ Exercise 2.3 Assess Which Pricing Model Will Best Meet the Needs of a Deployment 🏋️](/exercises/chap02/e_2_3/)
<hr>

## 🟥 Instance Life Cycle
* The state of a EC2 instance running can be managed in differrent ways.
* Terminating an instance will shut down the instance and release its resources to the general AWS pool
   - In most cases, terminating will destroy all data keptr on primary storage - execeptr for EBS volumes which always persists.
* Stopping the instance and restarting it can be a cost savings effective way of "pausing" the instance - however any storage on instance volume is lost
* I will learn about EBS and instance store volumes later into this chapter
* I need to be aware that the public IP address is non-persistent
   - If you need a known IP address which stays the same after restarts, you can allocate an elastic IPP address and associate it with the instance.
* The instance's security group can be updated even when the instance is running. Modifying the instance type requires stopping the instance
<hr>

## 🟥 Resource Tags
* Tags are keys with optional values which can be applied to any AWS resource in your account
* It is best to establish a consistent naming convention and apply it to tags
* You can apply the tag `production-server` to each element of production deployment
   - You can use `production-server` as keys, and then use the value to signify the resource (see table below as an example)

| Key             | Value           |
|-----------------|-----------------|
| `production-server` | `server1`   |
| `production-server` | `server2`  |
| `production-server` | `security-group1` |
| `staging-server`    | `server1` |
| `staging-server`    | `server2` |
| `staging-server` | `security-group1` |
| `test-server` | `server1`  |
| `test-server` | `security-group1` |

<hr>

## 🟥 Service Limits
* Each AWS account haas limits to the number of instances it can launch by default.
* Thesel imits can apply to single region or globally
* E.g. you are only allowed 5 VPCs per region and 500 SSH key pairs across your account.
* You can ask AWS to raise these limits