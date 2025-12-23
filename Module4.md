# Introduction to Going Global

AWS has footprint facilities called edge locations. Edge locations cache items like images, videos, and other resources, so that users can access the content they need with lower latency.

AWS has services, such as CloudFormation, that can help to automate the deployment of cloud resources. These services use infrastructure as code, or IaC, helping to achieve a consistent, reliable set up each time.


## Choosing AWS Regions
1.	Compliance 
Different geographical locations have varying regulatory requirements and data protection laws that organizations must follow.
2.	Proximity
Regions closer to your user base minimize data travel time, which reduces latency and enhances application responsiveness.
3.	Feature availability
AWS is constantly expanding features and services to multiple locations, but not all Regions contain all AWS offerings.
4.	Pricing
Some Regions have lower operational costs than others and might offer tax incentives or have lower tax rates, which can impact the overall expenses for hosting applications, services and customer pricing.

 
## Diving Deeper into AWS Global Infrastructure
High availability: the capability of a system to operate continuously without failing. It means that your applications can handle the failure of individual components without significant downtime

Agility: the ability to quickly adapt to changing requirements or market conditions. With AWS infrastructure in place, you can modify and deploy services rapidly.

Elasticity: the ability of a system to scale resources up or down automatically in response to changes in demand 

### Edge locations
Global edge network that provides quicker content access to users outside of standard Regions.
-	Offers multiple services to run closer to end users, including AWS networking services like Amazon CloudFront. 

Regions > Availability Zones > Edge locations


## Infrastructure and Automation
AWS CloudFormation

Service that helps model and set up AWS resources. 
-	Define your infrastructure as code
-	Create a template that describes all the AWS resources that you want like Amazon EC2 instances), 
-	Takes care of provisioning and configuring these resources


### Interacting with AWS
1.	Programmatic access
   
AWS CLI and AWS SDKs are best suited for developers and those familiar with coding languages.
AWS CLI: Manage multiple AWS services directly from the command line. You can automate routine tasks through scripts.
AWS SDKs: Help integrate AWS services by providing APIs for various programming languages. AWS provides documentation and sample code to help with using SDKs. 

Use cases:
-	Write a script to provide routine backups for a service such as Amazon Elastic Block Store (Amazon EBS)
-	Use an SDK to store user data in an AWS storage service such as Amazon Simple Storage Service (Amazon S3)

2.	AWS Management Console
   
A web interface that is used for managing AWS services, offering quick access to services, search functionality, and simplified workflows. For those new to the cloud or users with minimal or no development experience.

Use cases:
-	Billing and cost optimization dashboards and visualisations
-	Services focused on graphical representations (like Amazon QuickSight, and Amazon Neptune)

3.	Infrastructure as Code (IaC)
   
Automate resource management across your organization with AWS service integrations offering efficient and repeatable resource creation and management.

Use cases:
-	Managing infrastructure with DevOps such as continuous integration and delivery (CI/CD) pipelines
-	Scaling resources such as Amazon EC2 instances to multi-Region applications in a consistent, repeatable way.
