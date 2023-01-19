# Team Magenta, Group Two

## Contents
* [Introduction](#Introduction)
* [Team](#Team-Members)
* [Objective](#Objective)
* [Project Management](#Project-Management)
* [Risk Assessment](#Risk-Assessment)
* [Technologies Used ](#Technologies-Used )
* [Activities](#Activities)
* [Solution](#Solution)
* [Cost](#Cost)
* [Constraints](#Constraints)
* [Future Work](#Future-Work)
* [Conclusion](#Conclusion)
* [Acknowledgments](#Acknowledgments)

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

<p align="center">
    <img src="https://github.com/Adamcoakley/team-magenta-group-two/blob/main/readme-images/jira-board.png?raw=true">
</p>

<p align="center">
    <img src="https://github.com/Adamcoakley/team-magenta-group-two/blob/main/readme-images/burndown.png?raw=true">
</p>

<p align="center">
    <img src="https://github.com/Adamcoakley/team-magenta-group-two/blob/main/readme-images/epic-progress.png?raw=true">
</p>


## Risk Assessment 
Before embarking on the project our team devised a cursory risk assessment (shown below) which outlines possible hazards that the application could encounter. These risks influenced our choices when developing the CI/CD pipeline for the application. For example, we followed the principal of least privilege when assigning policies to the AWS resources and users needed for our pipeline. We also chose to use reputable repository services for our source code and container images as well as avoiding sharing or hardcoding sensitive information. Going forward we would like to further increase the security and reliability of the application and our CI/CD pipeline by integrating AWS resources such as GuardDuty.

<p align="center">
    <img src="https://github.com/Adamcoakley/team-magenta-group-two/blob/main/readme-images/risk-assessment.png?raw=true">
</p>


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

## AWS CodeBuild
AWS CodeBuild is a fully managed continuous integration service that compiles source code, runs tests, and produces ready-to-deploy software packages. We used buildspec files on both the frontend and backend repository to containerise the application and push images to ECR.

### AWS Elastic Container Service (ECS)
We chose ECS as our deployment option because its a highly scalable container orchestration and deployment service that is native to AWS. It eliminates the need to install, operate and scale our own cluster management infrastructure. 

### Elastic Container Registry (ECR)
We chose to use ECR over the more traditional DockerHub because it’s integrated with the other AWS service, particularly with ECS. It automatically encrypts images at rest and transfers images over HTTPS. Access to individual repositories on ECR can be managed with IAM policies.

## Activities
To begin with, our team thought it would be a good idea to get a feel for the application, which involved taking a look at the file structure, understanding the code and running it locally. Here is a list of the local activities we engaged in:
* Started the backend using the command: ``` ./mvnw spring-boot:run```
* Installed the correct dependencies, mainly angular-cli version 11.2.11
* Started a development server with the command: ```ng serve```
* We built the application in a dedicated docker image using the provided Dockerfile: ```docker build -t spring-petclinic-angular:latest .```
* Ran the tests locally using the command: ```ng test```

Each of these tasks were successfully completed, the backend and frontend were both operating efficiently, the application was locally containerised, and all of the tests were successful. 

<p align="center">
    <img src="https://github.com/Adamcoakley/team-magenta-group-two/blob/main/readme-images/tests-cli.png?raw=true">
</p>

<p align="center">
    <img src="https://github.com/Adamcoakley/team-magenta-group-two/blob/main/readme-images/tests-karma.png?raw=true">
</p>

<p align="center">
    <img src="https://github.com/Adamcoakley/team-magenta-group-two/blob/main/readme-images/angular-app.png?raw=true">
</p>


## Solution 
The completed pipeline detects changes to your image, which is stored in an image repository such as Amazon ECR, and uses CodeDeploy to route and deploy traffic to an Amazon ECS cluster and load balancer.

<p align="center">
    <img src="https://github.com/Adamcoakley/team-magenta-group-two/blob/main/readme-images/pipeline.png?raw=true">
</p>

## Cost 
​​AWS offers a pay-as-you-go approach for pricing for the vast majority of their cloud services. With AWS you pay only for the individual services you need, for as long as you use them, and without requiring long-term contracts or complex licensing. There are no additional costs or termination fees.

For this project we used AWS Pricing Calculator to get an estimate on the cost of the technologies we are going to use. First we did an estimate for the technologies we had initially planned to use at the start of the week.

<p align="center">
    <img src="https://github.com/Adamcoakley/team-magenta-group-two/blob/main/readme-images/cost-report.png?raw=true">
</p>

You can also view the cost report as a pdf [here.](https://github.com/Adamcoakley/team-magenta-group-two/blob/main/cost/aws-cost-report.pdf)

## Constraints
### Time
We found the four days we had to complete the project to be quite restricting. We encountered more problems than we had hoped for, and sadly, they took longer to resolve than we had anticipated. Our time management could have been more effective, which would have led to a better solution as time was our biggest constraint. We will be more capable of estimating and managing our time while developing and troubleshooting as we gain more experience.

### Lack of Clarity 
Although the concepts and technologies specified in the brief were familiar to us, this was our first time using them in a project of this scale. Due to our lack of knowledge regarding the ideal technology stack, we were hesitant to choose one technology over another. By working incredibly hard and for long hours, our team did make a valiant effort to solve our problems. We believe that after attempting a project of this size and scope, our uncertainty about how to approach such a project has improved.

### AWS Permissions
We ran into many different technical issues throughout the course of the project, some cost us more time than others. IAM policies were a consistent issue as we had little experience with them, we are now well versed in how to attach them to users and roles. We ran into hardware issues with using docker on our laptops and the mySQL docker image proved an issue with three of the four people in our group who have mac laptops. 

## Future Work
The first step would be to add a test server instead of deploying the changes directly into the production server. The advantages of deploying this way are:
* Avoid bugs or errors that could interfere in the normal activity of the app.
* Double test to ensure everything works as expected.
* Playground for developers to deploy possible future app features without compromising the integrity of the production app.
On the other hand, this solution requires another server running which can increase the cost of maintaining the process.

As the project was short, we did not make use of infrastructure as a code (IaC). However, as a team we now understand it's benefits and can envision a solution where IaC would be really helpful. Going forward, we would like to make use of an IaC tool, terraform, ansible or cloudformation to make the solution to improve many aspects of the solution, including: maintenance, consistency, and the ability to reproduce an environment.

## Conclusion
In conclusion, we can say that the project has exceeded our expectations in terms of difficulty. Combining all the tools that we have been learning throughout the program has been tough, mainly due to the blockers we faced, for example, AWS permissions. However, as a group, we came together and put in a great effort, which resulted in a positive experience overall.

## Acknowledgments
We want to express our gratitude to Deloitte and the members of the Cloud Engineering team for their assistance and for hospitably hosting us on several occasions throughout our training.

We want to express our appreciation to AMS and the staff there for their unwavering support and guidance.

We appreciate QA and the training team for supplying us with the knowledge required to complete this assignment.






