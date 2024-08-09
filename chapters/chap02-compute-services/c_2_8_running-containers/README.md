<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 2.8 Running Containers
* While EC2 container are fast, the nature of each VM being a discrete  system with an OS and full software stack means they have alot of hardware overhead
* Containers are significantly more efficient as a result of sharing the host's kernal.
* Layered and modular architecture of containers allows for quick initial builds and extremely short subsequent load times.
* These containers are expressed as docker files - simple text files, used to build the binary image
* The hosting software used to run and connect your container workloads is where things become complicated - AWS provides two services for running containers in production:
1. **Amazon Elastic Container Service (ECS)**
2. **Amazon Elastic Kubernetes Service (EKS)**
* We shall see how the above and quickly look at AWS's own container repo: Elastic Container Registry (Amazon ECR)

<hr>

## 🟥 Amazon Elastic Container Service
* The best result of container technologies is a consequence of intelligent scripting of their operation.
* Scripts can be used to launch thousands of containers
* Changing condititions can automatically trigger adjustments to deployment
* To get many parts to work together accross complicated networks requires sophisticated orchestration - this is where **ECS** comes in
* ECS lets your define your application, selecting container images, environment resources and other elements your app needs - ECS will take care of everything else

<hr>

## 🟥 Amazon Elastic Kuberenetes Service
* Kubernetes (K8s) is an open source container orchestrator originally built by Google for its own internal use.
* Elastic Kubernetes Service plays a similar role to ECS but not tied to one platform
* Kurbenetes is the most popular tool, all major cloud provides offer Kubernetes services

<hr>

## 🟥 Other Container-Oriented Services
* **AWS Fargate** abstracts alot of the complixity for users who don't need any control over the infrastructure
* **Amazon Elastic Container Registry (ECR)** is a managed Docker container registry service which makes it easy for users to store, manage and deploy docker container images
* This removes need of platforms like GitHub to build the container