# 🧠 4.1 Introduction
* Amazon's Virtual Private Cloud (VPC) provides a networking layer of EC2
* It's a virutal network which can contain EC2 instances and network resources for other AWS services.
* By default, VPCs are isolated from any form of network.
* However, we CAN introduce connection to other networks like the internet, on premiwse networks and other VPCs

* VPCs are foundational to many AWS services.
* A VPC can only exist within an AWS region. I.e. creating a VPC in one region means it won't show up in other regions.
* Multiple VPCs can be generated for a single account and single region.

* While VPCs function like traditional TCP/IP network, but there are important differences
* VPCs are SCALABLE, and can be expanded without having to add physical hardware.
* To allow this, there are some limitations which would be available in a traditional network - such as switches and VLANs, these are abstracted into software functions and called by different names