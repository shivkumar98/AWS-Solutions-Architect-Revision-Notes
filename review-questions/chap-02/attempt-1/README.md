# Chapter 2 - Review Questions Attempt 1

## Results:

* Date: 
* Score:

| Question # | Correct  |
| ---------- | -------  |
| 1          |       |
| 2          |       |
| 3          |       |
| 4          |       |
| 5          |       |
| 6          |       |
| 7          |       |
| 8          |       |
| 9          |       |
| 10         |       |
| 11         |       |


## 🟧 Question 1

❓ You need to deploy multiple EC2 Linux instances that will provide your company with VPNs using a software called OpenVPN. Which of the following will be thhe most efficient solutionss (CHOOSE TWO)❓

* A. Select a regular Linux AMI and bootstrap it using user data thhat will install and configure the OpenVPN package on the instance and use it for your VPN instances
* B. Search the community AMIs for an official AMI provided and supported by the Open-VPN company
* C. Search the AWS Marketplace to see whether there's an official AMI provided and supported by the OpenVPN company
* D. Select a regular Linux AMI and SSH to manually install and configure the OpenVPN package
* E. Create a site-to-site VPN connection from the wizard in the AWS VPC dashboard

<details>
<summary> 📝 My answer 📝 </summary>

* **B,C**
</details>

<hr>


## 🟧 Question 2

❓ As part of your company's long-term cloud migration strategy, you have a VMware virtual machines in your local infrastructure that you'd like to copy to your AWS account and run as an EC2 instance. Which of the following will be necessary steps? (choose two) ❓

* A. Import the virtual machine to your AWS region using a secure SSH tunnel.
* B. Import the virtual machine using VM Import/Export.
* C. Select the imported VM from among your private AMIs and launch an instance.
* D. Select the imported VM from the AWS Marketplace AMIs and launch an instance.
* E. Use the AWS CLI to securely copy your virtual machine image to an S3 bucket within the AWS region you'll be using.

<details>
<summary> 📝 My answer 📝 </summary>

* The VM Import/Export tool should be used, then you will deploy it via your private AMIS
* **B,C**

</details>

## 🟧 Question 3

❓ Your AWS CLI command to launch an AMI as an EC2 instance has failed, giving you an error message that includes `InvalidAMIID.NOTFOUND`. What of the following is the most likely cause? ❓

* A. You haven't configured the `~/.aws/config` file
* B. The AMI is being updated and is temporarily unavailable.
* C. Your key pair file has been given the wrong (overly permissive) permissions.
* D. The AMI you specified exists in a different region than the one you've currently speicified.

<details>
<summary> 📝 My answer 📝 </summary>

* Total guess that it is D, all other answers seem irrelevant
* **D**

</details>

## 🟧 Question 4

## 🟧 Question 5

## 🟧 Question 6

## 🟧 Question 7

## 🟧 Question 8

## 🟧 Question 9

## 🟧 Question 10

## 🟧 Question 11
