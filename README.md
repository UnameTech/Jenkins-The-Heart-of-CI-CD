# Jenkins-The-Heart-of-CI-CD
Jenkins – The Heart of CI/CD

---
---

 **Jenkins for CI CD**, with:

- CI and CD explained through **realistic labs on a Linux VM or EC2**
- A clear **note** that Docker and Kubernetes integrations will be covered *after learners master them*
- Logical sequencing for a student who has zero prior exposure

---
---

##  Module Objective  
To teach learners how to set up and use Jenkins to automate Continuous Integration and Continuous Delivery using hands-on projects on a virtual machine or cloud instance. Docker and Kubernetes deployment will be taught after learners have gone through those technologies in upcoming modules.

---

## 🔧 Lab Infrastructure Prerequisites

- One **Ubuntu virtual machine** or **AWS EC2 Ubuntu instance**
- Java 11 or above installed
- Git and Maven installed
- Internet access to install Jenkins and plugins
- Access to a GitHub account (for Git integration)

---

#  Module Structure

---

## Section 1 – Introduction to Jenkins

- 1.1 What is Jenkins  
  - Open-source CI CD tool  
  - Jenkins history and community  
  - Where Jenkins fits in the DevOps lifecycle  

- 1.2 Jenkins Architecture  
  - Master and agent model  
  - Jenkins job, workspace, build, and executor  

- 1.3 Installing Jenkins on Ubuntu or EC2  
  - Install Java  
  - Add Jenkins repo and install Jenkins  
  - Start Jenkins and unlock using admin password  
  - Install suggested plugins and setup first admin user  

- 1.4 Lab: Install Jenkins on EC2 and access via browser  
  - Verify service is up and running  
  - Configure initial settings  

---

## Section 2 – Jenkins Freestyle Jobs

- 2.1 What is a freestyle job  
  - Create a simple job to run shell script  

- 2.2 Lab: Create a freestyle job  
  - Print date and system status  
  - Save build logs  

- 2.3 Build Triggers  
  - Manual trigger  
  - Poll SCM  
  - Scheduled (CRON)

- 2.4 Lab: Build a Java Maven project  
  - Pull from GitHub  
  - Run Maven clean install  
  - Archive the JAR as build artifact  

---

## Section 3 – Continuous Integration with Jenkins

- 3.1 What is Continuous Integration  
  - Merge small changes frequently  
  - Test early and often  

- 3.2 Lab: Build on every Git push  
  - Setup webhook from GitHub  
  - Trigger Jenkins build automatically  
  - Notify success or failure via email  

- 3.3 Add test stage to build  
  - Run unit tests after compilation  
  - Fail the job if tests break  

- 3.4 Lab Summary  
  - From push to GitHub to test and artifact generation  

---

## Section 4 – Continuous Delivery with Jenkins

- 4.1 What is Continuous Delivery  
  - Automate deployment up to staging or test server  
  - Add manual approval to push to production  

- 4.2 Lab: Copy artifact to remote VM  
  - Use Jenkins Publish Over SSH plugin  
  - SSH into a second Ubuntu VM (or same EC2 with separate folder)  
  - Deploy JAR to target location  
  - Start application using `nohup` or `systemd`

- 4.3 Real-World Workflow  
  - Developer pushes code  
  - Jenkins builds, tests, archives  
  - Jenkins copies the artifact to server and restarts app  
  - Notify on Slack or Email  

---

## Section 5 – Jenkins Pipelines

- 5.0 What is a pipeline  
  - Stages and steps explained  
  - Jenkinsfile format  
  - Declarative vs Scripted  

- 5.0.1 Lab: Simple pipeline to print messages and run shell script  

- 5.0.2 Lab: Full CI CD pipeline using Jenkinsfile  
  - Stage 1: Checkout code  
  - Stage 2: Build  
  - Stage 3: Test  
  - Stage 4: Deploy  
  - Stage 5: Notify
 

## **Pipeline as Code in Jenkins**

---

## Objective:  
To teach learners how to create and manage Jenkins pipelines using code (Jenkinsfile) rather than manual UI configuration, enabling versioned, repeatable, and automated CI/CD workflows.

---

##  Topics for Section 5 – Pipeline as Code in Jenkins

### 5.1 What is Pipeline as Code  
- Concept of codifying your CI CD process  
- Benefits over freestyle jobs  
  - Version controlled pipelines  
  - Reusability  
  - Better collaboration  
  - Easier to review, audit, and debug

### 5.2 Jenkinsfile Explained  
- What is a Jenkinsfile  
- Where is it stored (in your source repo)  
- Declarative vs Scripted syntax  
- Structure of a declarative Jenkinsfile  
  - pipeline  
  - agent  
  - stages  
  - steps  
  - post actions

### 5.3 Creating Your First Jenkinsfile  
- Basic pipeline that prints Hello World  
- Lab: Store Jenkinsfile in a GitHub repo and run with Jenkins  
- Explanation of what each part of the file is doing

### 5.4 Real-World Pipeline Example  
- Build → Test → Package → Archive  
- Lab:  
  - Checkout code from GitHub  
  - Run Maven build  
  - Archive artifact  
  - Email on success or failure

### 5.5 Pipeline Best Practices  
- Keep pipelines simple  
- Separate build and deploy pipelines  
- Use environment variables  
- Use shared libraries (overview)  
- Secure credentials with Jenkins secrets  

### 5.6 Debugging Pipelines  
- View pipeline logs  
- Fail stages intentionally for demo  
- Retry failed stages  
- Use `when`, `input`, `timeout` blocks  

### 5.7 Bonus: Parallel Steps and Matrix Builds  
- When to use parallelism  
- Example of testing on multiple JDK versions  
- Matrix build explained with sample code  

---

## Section 6 – Integrating Jenkins with GitHub

- 6.1 GitHub credentials setup in Jenkins  
- 6.2 Create webhook in GitHub  
- 6.3 Lab: Automate builds on GitHub push  

---


## **Section 7 – Jenkins Integration with Docker and Kubernetes**  
*Note: This section will be taught **after** learners complete Docker and Kubernetes modules in upcoming chapters.*

---

### 7.1 Jenkins with Docker – Overview  
- Why Jenkins needs Docker for modern CI CD  
- Use cases: building Docker images, running containerized apps, using Docker agents

---

### 7.2 Jenkins Pipeline to Build and Push Docker Images  
- Writing a Jenkinsfile to build a Docker image  
- Tagging and pushing image to Docker Hub or Amazon ECR  
- Managing Docker credentials securely in Jenkins  
- Real-world scenario: Microservice build and containerization

---

### 7.3 Running Jenkins in Docker  
- Running Jenkins as a container  
- Persistent volumes and custom images  
- Pros and cons of containerized Jenkins

---

### 7.4 Jenkins with Kubernetes – Intro  
- Why Jenkins integrates with Kubernetes  
- Use cases: dynamic agents, deployments, CI CD pipelines in EKS

---

### 7.5 Deploy to Kubernetes from Jenkins  
- Jenkins plugin for Kubernetes  
- Using `kubectl` in pipeline  
- Helm chart deployment via pipeline  
- Real-world example: CI CD pipeline deploying microservice to EKS

---

### 7.6 Jenkins Agent on Kubernetes  
- What is a Kubernetes-based Jenkins agent  
- Launching Jenkins agents as pods dynamically  
- Using pod templates in pipeline definition

---

### 7.7 Jenkins, Docker, and Kubernetes – Putting It All Together  
- Full CI CD pipeline  
  - Build → Test → Containerize → Push → Deploy to Kubernetes  
- Lab: Jenkins pipeline with Docker build and Kubernetes deployment  
- Tips for real-world CI CD architecture using Jenkins and K8s

---


## Section 8 – Bonus Topics 

- 8.1 Jenkins global settings  
- 8.2 Plugin management  
- 8.3 Managing multiple jobs using folders  
- 8.4 Jenkins credentials and secrets  

---

