# Team Magenta, Group Two
## Introduction 
The aim of this project is to migrate the Petclinic application, and all of their resources to the cloud. This project will involve concepts from all core training modules; more specifically, this will involve:
* Agile & Project Management 
* Databases & Cloud Fundamentals
* Programming & Testing Fundamentals
* Continuous Integration
* Infrastructure as Code & Configuration Management
* Containerisation & Orchestration
* Cloud Configuration and Management

This project will encapsulate aspects of many modules throughout training to achieve the specification outlined in the sections below.

## Team Members
* Ciara Fennessy
* Adam Coakley
* Kiishi Ifebajo
* Diego Pascual

## Objective
The following applications were provided to our team:
* https://github.com/spring-petclinic/spring-petclinic-angular
* https://github.com/spring-petclinic/spring-petclinic-rest

And the overall objective of the project was to: *“plan, design and implement a solution for automating the development workflows and deployments of a given application, with utilisation of supporting tools, methodologies and technologies that encapsulate all modules covered during training.”*

## Project Management
We adopted an andapted Agile approach to this project. We organised the workload across the four-day time limit that became our sprint.  We assigned the traditional roles of Project Manager and Scrum Master to a new member of the group each day as well as the role of Activity Logger who kept minutes on which member of the group was working on which aspect of the project. We rotated these roles everyday to give each member of the group equal opportunity to explore the responsibilities of the individual roles. 

We set-up a software development project on Jira to help us visualise, track and organise our project. The project manager from the first day of the project setup the product backlog and populated it with all the epics, userstories and tasks that we imagined we would need to execute our plan for the week. As this was our first project of this scale, we allowed the subsequent project managers to edit or add any tasks or user-stories to the sprint that we had not originally envisioned. We assigned each user-story/issue a story-point estimate and a member of the group. The Scrum Master and Project Manager collaborated on facilitating the daily stand-ups in which the group members brought eachother up-to-date on their progress and outlined any blockers they had been facing. As team members worked on and completed aspects of the project they edited the board on Jira to reflect their progress.  

## Technologies Used 
### GitHub
For version control, git was used, with the project repository hosted on GitHub. On top of that, the feature branch model was used, which means, a separate branch was created for each additional feature. Once the functionality was developed, the feature branch was merged with the master branch and our team repeated this process until the project was complete.

### Docker
Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime. Our team made use of Docker commands within the buildspec.yaml file to containerise the application within the pipeline.

### Amazon Web Services (AWS)
Amazon Web Services is an online platform that provides scalable and cost-effective cloud computing solutions. AWS is a broadly adopted cloud platform that offers several on-demand operations like compute power, database storage and content delivery, to help corporates scale and grow. Using AWS allowed our team to leverage many services, including AWS Elastic Compute Cloud, AWS CodePipeline, AWS CodeBuild, AWS Elastic Container Service (ECS) and Elastic Container Registry (ECR).

### AWS Elastic Compute Cloud
Amazon Elastic Compute Cloud (Amazon EC2) provides scalable computing capacity in the AWS Cloud. Using Amazon EC2 eliminates your need to invest in hardware up front, so you can develop and deploy applications faster. By utilising the load balancer within the EC2 dashboard, our team was able to automatically distribute the applications incoming traffic across multiple targets and availability zones.

### AWS CodePipeline
AWS CodePipeline is a fully managed continuous delivery service that helps you automate your release pipelines for fast and reliable application and infrastructure updates. After some discussion and planning, our team created a multi-stage pipeline that uses two sources: one for the frontend, and one for the backend. The pipeline was also configured to have a webhook in place, so that each time a user pushes a commit to GitHub, the pipeline goes through each phase automatically.
AWS CodeBuild
AWS CodeBuild is a fully managed continuous integration service that compiles source code, runs tests, and produces ready-to-deploy software packages. 

### AWS Elastic Container Service (ECS)

### Elastic Container Registry (ECR)

## Activities
To begin with, our team thought it would be a good idea to get a feel for the application, which involved taking a look at the file structure, understanding the code and running it locally. Here is a list of the local activities we engaged in:
* Started the backend using the command: ``` ./mvnw spring-boot:run```
* Installed the correct dependencies, mainly angular-cli version 11.2.11
* Started a development server with the command: ```ng serve```
* We built the application in a dedicated docker image using the provided Dockerfile: ```docker build -t spring-petclinic-angular:latest .```
* Ran the tests locally using the command: ```ng test```

Each of these tasks were successfully completed, the backend and frontend were both operating efficiently, the application was locally containerised, and all of the tests were successful. 

## Solution 





