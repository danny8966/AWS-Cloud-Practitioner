# Introduction to Serverless Computing
EC2 is unmanaged service. 

ELB, SNS , SQS is managed services meaning you will manage less amount of infrastructure and will be able to focus more on your applications.

Fully managed services eliminated the need to provision or manage any servers at all. 
Lambda is a serverless compute service where AWS handles most while you remain responsible for securing and managing your application code.



## AWS Lambda
Serverless compute service that runs code in response to events without the need to provision or manage servers
-	Automatically manages the underlying infrastructure, scaling resources based on the volume of requests
-	Charged only for the compute time consumed, down to the millisecond
-	Handles execution, scaling, and resource allocation
-	Optimize performance by configuring the appropriate memory size for your function

How Lambda works:
1.	Upload the code to Lambda, which will be ‘Lambda function’
2.	Configure your code to be triggered by events like AWS services, mobile apps etc
3.	Code runs only when an event occurs, the Lambda runtime executes your function code using the event data passed to it.
4.	Pay for compute time used, and the price depends on the amount of memory allocated to your function

Lambda use cases:
-	Real-time image processing for a social media application
-	Personalized content delivery
-	Real-time event handling for an online game


## Containers and Orchestration on AWS
Containers package your application with everything it needs to run, so it works the same on any computer.
-	Helps to move, update, and manage
-	Faster and lighter than virtual machines (VMs) because they share the host computer’s OS

Orchestration services automate deployment , scaling , and management to keep everything running smoothly.

### Amazon Elastic Container Service (ECS) 
Scalable container orchestration service for running and managing containers on AWS.

### Amazon Elastic Kubernetes Service (EKS)
Fully managed service for running Kubernetes on AWS. 
-	Simplifies deploying, managing and scaling containerized applications using open-source Kubernetes, with ongoing support and updates from the broader community.

### Amazon Elastic Container Registry (ECR)
Place where you can store , manage and deploy container images. 
-	Supports container images that follow the Open Container Initiative (OCI) standards. 
-	Push, pull and manage images in your Amazon ECR repositories using standard container tooling and command line interfaces (CLIs)

## Container hosting platforms
#### Amazon EC2
With Amazon ECS 
-	For small-to-medium businesses that need full control over infrastructure
-	For custom applications requiring specific hardware or networking configurations.

With Amazon EKS
-	For enterprises needing full control over infrastructure
-	Offers deep customization of EC2 instances alongside Kubernetes scalability
-	For complex , large-scale workloads
#### AWS Fargate - Serverless compute engine for containers
With Amazon ECS
-	For startups or small teams building web applications with variable traffic

With Amazon EKS
-	For teams wanting Kubernetes flexibility without managing servers


## Additional Compute Services	
### AWS Elastic Beanstalk
Fully managed service that streamlines the deployment, management, and scaling of web applications.
-	Supports various programming languages and frameworks, such as Java, .NET, Python, Node.js, Docker …
-	Provides full control over the underlying AWS resources while automating many operational tasks.
  
Good for deploying and managing web applications, RESTful APIs, mobile backend services, and microservices architecture, with automated scaling and simplified infrastructure management.
### AWS Batch
Fully managed service that can be used to run batch computing workloads on AWS.
-	Automatically schedules, manages, and scales compute resources for batch jobs, optimizing resource allocation based on job requirements

Good for processing large-scale, parallel workloads in areas like scientific computing, financial risk analysis, media transcoding, big data processing, machine learning training and genomics search.
### Amazon Lightsail
Cloud service offering virtual private servers (VPSs), storage, databases, and networking at a predictable monthly price.
-	For small businesses, basic workloads, and developers seeking a straightforward AWS experience without the complexity of the full AWS Management Console

Good for basic web applications, low-traffic websites, development and testing environments, small business websites, blogs, and learning cloud services.
### AWS Outposts
Fully managed hybrid cloud solution that extends AWS infrastructure and services to on-premises data centres
-	Provides a consistent experience between on premises and the AWS Cloud, offering compute, storage, and networking components.

Good for low-latency applications, data processing in remote locations, migrating and modernizing legacy application, and meeting regulatory compliance or data residency requirements.
