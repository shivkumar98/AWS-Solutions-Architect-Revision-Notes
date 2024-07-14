# 🧠 2.5 Securing Your EC2 Instance
* AWS provided 4 tools for helping you configure the security of you EC2 instances to prevent unauthorised use:
   1. Security Groups
   2. Identity and Access Management (IAM) Roles
   3. Networking Address Translations (NAT)
   4. Key Pairs

<br>

## 🟥 Security Groups
* Security groups function as a firewall
* By default, it will permit all outgoing traffic and deny all incoming traffic.
* You define security group behaviour by setting policy rules which will block or allow specific traffic types - data packets entering or leaving the perimeter will be measured against the rules.

<br>

* Traffic is assessed by examining:
   - its source and destination
   - the network port it is targetting
   - protocol it's set to use

* For example, a TCP packet sent to thhe SSH port could only be allowed access to a particular instance if its source IP address matches the local public IP used by computers in your office.
* You could use a Security Group to open up the website to the world, but only allow access to backend severs for your team.


<hr>

## 🟥 IAM Roles
* AWS resources can be accessed via IAM role
* IAM Roles are defined by giving permission to peform actions on specified services - e.g. to download an object from S3
* When a user is assigned a role, the user will have access the resource in the policy.
* You can also give a role ***TO** an EC2 instance
   - e.g. you can give acdcess to external services like RDS
* I wil learn more about IAM in chapter 6 Authentication and Authorisation - AWS Identity and Access Management

<hr>

## 🟥 NAT Devices
* You may not want to give your EC2 instance exposre to the internet, bnut you may want it to access the internet for software updates/patches
* NAT (network address translation) can give an EC2 instance access to internet while limiting it from being available via interrnet
* There are two ways to do this in AWS:
   - NAT instance
   - NAT gateway
* NAT Gateway is a managed service, so it wouldn't require manual intervention

<hr>

## 🟥 Key Pairs
* Running instance should never be initiated over unencrypted plain-text connection.
* Generating a ketg pair, saving the public key to your EC2 server and saving the private key file locally will secure sessions.
* For Windows-based AMIs, you will use a private key file to retrieve the password
* For Linux-based AMIs, the private key will enable you to open an SSH session
* Each key pair that AWS generates will remain installed within its original region and available up untol you delete the instance

<br>

* In the case of the public key being exposed, you should delete AWS copy of private key