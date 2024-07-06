# 🧠 1.3 AWS Platform Architecture
* AWS has its datacenter for its servers distributed accross the globe.
* For low latency, you should host your workloads geographically close to your users.
* This can help manage compliance and ensure data is is kept within legal jurisdictions.

<br>

* The datacenters are enclosed within an **AWS Region**
* There are 21 AWS regions listed in this book - but more have been added over time
* When launcching an AWS resource in a particular AWS region you must consider costs, latency and service availability

## 🟥 Publicly Accessible AWS Regions

| Name       | Region   | Endpoint                 |
| -----------|----------|--------------------------|
| **US East (Ohio)** | `us-east-2` | `us-east-2.amazonaws.com` |
| **US West (N. California)** | `us-west-1` | `us-west-1.amazonaws.com` |
| **US West (Oregon)** | `us-west-2` | `us-west-2.amazonaws.com` |
| **Asia Pacific (Hong Kong)** | `ap-east-1` | `us-east-1.amazonaws.com` |
| **Asia Pacific (Mumbai)** | `ap-south-1` | `ap-south-1.amazonaws.com` |
| **Asia Pacific (Tokyo)** | `ap-northeast-1` | `ap-northeast-1.amazonaws.com` |
| **Asia Pacific (Seoul)** | `ap-northeast-2` | `ap-northeast-2.amazonaws.com` |
| **Asia Pacific (Osaka-Local)** | `ap-northeast-3` | `ap-northeast-3.amazonaws.com` |
| **Asia Pacific (Singapore)** | `ap-southeast-1` | `ap-southeast-1.amazonaws.com` |
| **Asia Pacific (Sydney)** | `ap-southeast-2` | `ap-southeast-2.amazonaws.com` |
| **Canada (Central)** | `ca-central-1` | `ca-central-1.amazonaws.com` | 
| **Canada (Beijing)** | `cn-north-1` | `cn-north-1.amazonaws.com` |
| **China (Ningxia)** | `cn-northwest-1` | `cn-northwest-1.amazonaws.com` |
| **EU (Frankfurt)** | `eu-central-1` | `eu-central-1.amazonaws.com` |
| **EU (Ireland)** | `eu-west-1` | `eu-west-1.amazonaws.com` |
| **EU (London)** | `eu-west-2` | `eu-west-2.amazonaws.com` |
| **EU (Paris)** | `eu-west-3` | `eu-west-3.amazonaws.com` |
| **EU (Stockholm)** | `eu-north-1` | `eu-north-1.amazonaws.com` |
| **Middle East (Bagrain)** | `eu-south-1` | `eu-south-1.amazonaws.com` |

<br>

* AWS Regions are exposed to your AWS account
* Resources from a region are organised within VPCs
* A **VPC** is a network address space which you can create network subnets and associate them with availability zones.
* This architecture can provide effective resource isolation and duplication.