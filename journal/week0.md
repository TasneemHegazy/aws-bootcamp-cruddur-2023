# Week 0 — Billing and Architecture

<!-- Introduction -->
##  Introduction 

As I continue to migrate my operations to the cloud, it is important to ensure that my cloud infrastructure is secure, efficient, and scalable. This is where AWS Well-Architected Framework comes in handy. It is a set of best practices that helps me build and operate reliable, secure, efficient, and cost-effective systems in the cloud. As part of this framework, I have undertaken certain homework challenges to improve the security and efficiency of my AWS infrastructure.

Cruddur is a micro-blogging platform with the ability to share content that expires after a set time, emphasizing privacy and the present moment. The platform aims to reduce trust and safety issues by limiting the amount of personal information online, decreasing the potential for cyberbullying and harassment, improving the overall user experience, increasing the sense of community, and increasing trust and safety among users.


## Challenge 1: Destroy my root account credentials, Set MFA, IAM role

The root account is the superuser account in AWS, which has unrestricted access to all AWS services and resources. It is important to secure this account by setting up Multi-Factor Authentication (MFA) and creating an IAM (Identity and Access Management) role for it. The IAM role will provide the necessary permissions to perform specific tasks, while MFA will ensure that the account is only accessible by authorized personnel.

_To complete this challenge, I followed the steps below:_

1. Logged in to my AWS account using my root account credentials
2. Went to the IAM console and created an IAM user with administrative privileges
3. Logged out of my root account and logged in using the newly created IAM user credentials
4. Went to the IAM console and created an IAM role for the root account
5. Assigned the necessary permissions to the IAM role
6. Set up MFA for the root account
4. Tested the setup to ensure that it is working as expected
5. Finally, destroyed my root account credentials.

## Challenge 2: Used EventBridge to hookup Health Dashboard to SNS and send notification when there is a service health issue.

EventBridge is a fully managed event bus service that makes it easy to connect different AWS services and respond to events in real-time. This challenge involved using EventBridge to hookup Health Dashboard to SNS and send notifications when there is a service health issue.

_To complete this challenge, I followed the steps below:_

1. Went to the AWS Health Console and created an event for the service health issue I wanted to monitor.
2. Created an SNS (Simple Notification Service) topic for the notifications.
3. Went to the EventBridge console and created a rule that listens for the specific AWS Health event and sends a message to the SNS topic.
4. Tested the setup to ensure that it is working as expected.

## Challenge 3: Reviewed all the questions of each pillar in the Well-Architected Tool

The Well-Architected Tool is an online tool that provides a comprehensive review of my cloud architecture against the five pillars of the Well-Architected Framework: operational excellence, security, reliability, performance efficiency, and cost optimization. This challenge involved reviewing all the questions of each pillar in the tool.

To complete this challenge, I logged in to the Well-Architected Tool and reviewed all the questions of each pillar. I paid attention to the areas where my architecture needs improvement and took appropriate actions to address the identified gaps.

<!-- Logical Architectual Diagram -->
## Challenge 4: Create an architectural diagram in Lucid Charts
![Blank diagram](https://user-images.githubusercontent.com/82984386/219871250-6c57c134-7244-4d6a-8b1f-db7ed461401d.png)

[Lucid Logical Architectual Diagram.](https://lucid.app/lucidchart/fb31afce-4b31-4cf1-a231-b6202dffda06/edit?viewport_loc=-719%2C213%2C3058%2C1534%2C0_0&invitationId=inv_c092168c-fee0-43ad-bf41-89e73af50062)

The Logical Architectural Diagram includes several components that work together to provide a scalable, highly available, and cost-effective platform. These components include:

* Client: this service enables any user to access the application over the internet

* Authentication: the authentication service verifies users prior to allowing access to the app

* Amazon Route 53: Route 53 is a DNS service that will be used to route the user's requests to the appropriate AWS resources. Route 53 will provide low latency and high availability by routing the requests to the nearest AWS data center.

* Virtual Private Network: this service provides private network capabilities to the cloud environment
 
* Application Load Balancer: this load balancer service is used to maintain traffic flow and avoid congestion or crashing

* ECS EC2 Container: this containerization service provides an environment for the application

* Frontend: The frontend application will be written in JavaScript using React (functional components) to provide a highly responsive and interactive user interface that communicates with the backend API.

* Backend API: The backend application will be written in Python using Flask. Since the platform is an API-only, a micro-framework is chosen to make the backend codebase small, easily maintainable, and performant. Also, an ORM is not used to avoid the limitations of a monolithic application. The API will be responsible for handling incoming requests, authenticating and authorizing users, interacting with the database, and returning responses.

* REST API: this service is used for API calls and communication between the Frontend and Backend

* AWS Lambda: AWS Lambda will host the backend API code and scale it automatically based on the incoming traffic. Since Lambda is a serverless service, it will reduce the operational costs of running the backend API.

* AWS DynamoDB: DynamoDB is a NoSQL database service that will store the user data and posts.

* AWS RDS: this relational database is also used to store app data

* AWS S3: S3 will be used to store user-uploaded media, such as photos and videos. The API will interact with S3 through the AWS SDK for Python, and S3 will provide high durability, availability, and scalability at a low cost.

* AppSync: this service allows applications to access the exact data they need via API and is used to create and manage APIs.

* Momento: this serverless caching service is used to improve performance by providing fast access to frequently accessed data.


These components will work together to provide a scalable, highly available, and cost-effective micro-blogging platform that works on AWS. The frontend application will communicate with the backend API through API Gateway, which will route the requests to the appropriate Lambda function. The Lambda function will interact with DynamoDB to retrieve or store data, and S3 to store user-uploaded media. Route 53 will route the user's requests to the appropriate AWS resources based on the geographic location of the user.

Overall, this logical architecture diagram helps to provide a clear and organized understanding of the AWS services and their functions within the application architecture. By visually representing the flow of data and services, the diagram can serve as a valuable reference tool for optimizing the application's performance and scalability.



## Challenge 5: Research the technical and service limits of specific services and how they could impact the technical path for technical flexibility

AWS provides a vast array of cloud services, each with its own technical and service limits. To optimize my cloud infrastructure and ensure technical flexibility, I had to research the technical and service limits of specific AWS services and how they could impact the technical path for technical flexibility.

_To accomplish this challenge, I followed the steps below:_

1. I researched the various AWS services that I currently use in my cloud infrastructure.
2. I identified the technical and service limits of each service, such as the number of instances, storage capacity, or data transfer limits.
3. I assessed the impact of each service limit on the technical path for technical flexibility.
4. I explored possible workarounds or alternatives to mitigate any issues arising from the service limits.

## Challenge 6: Open a support ticket and request a service limit

As part of my AWS cloud infrastructure, I sometimes need to request service limits, such as the number of instances or storage capacity, to optimize my cloud resources. This challenge required me to open a support ticket and request a service limit.

_To accomplish this challenge, I followed the steps below:_

1. I logged in to the AWS Support Center.
2. I selected the appropriate category for my support ticket and provided detailed information about the service limit that I needed.
3. I provided justification for my request and any relevant supporting documents.
4. I waited for the AWS support team to respond to my ticket and provide the necessary feedback.


In conclusion, the homework challenges that I undertook helped me to improve my knowledge and skills of AWS cloud services. These challenges have equipped me with the skills and knowledge necessary to design, deploy and manage a robust and scalable cloud infrastructure.

