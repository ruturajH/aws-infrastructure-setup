# aws-infrastructure-setup


**Project  – Designing a Cloud Solution for a Medical Startup Company**

**AWS Final Architecture:**

![image](https://user-images.githubusercontent.com/53853127/141351152-b627588e-36f6-4637-8554-1e76d780b9af.png)




Please read ahead for more specification related to architecture and details in depth:

**Introduction-**
A medical company has a product which is software as a service ready to be launched for Global market(US,APAC and Europe)
This service consists of online medical social networking and diagnosis application over the network.
Connects patients and doctors 
Contains PII data and need HIPAA compliance.
Customers can upload documents and extracted data should be stored in database.
Application marked as critical and be highly available all the time for use

**Business Objectives** 
The company’s main objective is to make sure that we provide high availability and scalability to our customers for a SaaS platform. Currently, on premises we have issues scaling our application based on customers usage globally. During, peak times there is frequent performance degradation of our networking infrastructure. We have chosen AWS as our critical cloud provider to solve availability, scaling, performance, networking, and resiliency issues which would enhance our customer experience.  We have designed our architecture in considerations to all the benefits provided by AWS.  

**Key Benefits**
Write Infrastructure as Code, scale identical solution globally.
Cost effective solution, pay as you go model.
Innovate faster, reduced time to market.
Management and Governance at scale

**Current Architecture**
The medical company is using Microsoft Windows servers to host their web and application tiers with Microsoft SQL Server Standard Edition backend databases. The configuration is as follows:

Web Tier:
Two physical servers (Two CPUs / 4-GB memory)
Application Tier:
Two physical servers (Four CPUs / 16-GB memory)
Database Tier:
One physical server (Eight CPUs / 32-GB memory / 5-TB storage)


![image](https://user-images.githubusercontent.com/53853127/97471624-4d825600-191f-11eb-8e0f-649817fd7334.png)

**Requirements:**
Access permissions to the authorized users based on their roles.
Provide network connectivity to the applications in different environments.
Building efficient architecture capable of autoscaling and handling disruptions.
Providing security to customers data and be HIPPA compliant.
Load balancing across application and web tier.
Building resilient architecture incorporating monitoring services.

**Technical Design Specification**
Virtual private cloud hosting 3 tier architecture.
Web and application layer using Microsoft Windows licenses.
IAM users and roles granting least privileged access. 
Users access only ALB for interacting with the Web servers hosting in public subnet. 
Multi-AZ deployment for RDS instances.
Amazon Textract managed services to extract documents.

**AWS Services Used:**
![image](https://user-images.githubusercontent.com/53853127/141350292-86fd2ec3-cbe9-494c-9ccd-337e44f413f2.png)


**User Authentication**
![image](https://user-images.githubusercontent.com/53853127/141350527-a9a79f48-cbfa-428d-98ca-0076641877a1.png)

![image](https://user-images.githubusercontent.com/53853127/141350616-17d7e6c3-90e8-479f-b296-5282ce99ab38.png)

![image](https://user-images.githubusercontent.com/53853127/141350678-b2a7c828-d6de-4e03-a5c8-e43d23fea6ea.png)

![image](https://user-images.githubusercontent.com/53853127/141350736-2e4ceec0-a6e2-49c7-9be2-c65508f067d7.png)


![image](https://user-images.githubusercontent.com/53853127/141350804-90508218-b4bb-41a8-9990-094ae6374801.png)

![image](https://user-images.githubusercontent.com/53853127/141350851-d38cff4e-bcbb-4ab2-883a-dffb7566b906.png)

**Monitoring:**
AWS Cloud Watch: Monitoring
Provides you with data and actionable insights to monitor application.
Help in optimize resource utilization.
Detect anomalous behavior and help troubleshoot issues.
Collects operational and performance data in the form of logs, metrics, and events.
Analyze the operational health of services and send monitoring alerts.

AWS Cloud Trail: Auditing
continuously log events initiated through console, API by users and roles on services.
IAM access analyzer to see access across users and services.

