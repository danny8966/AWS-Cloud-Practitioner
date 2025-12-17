# Amazon EC2 (Amazon Elastic Compute Cloud)
•	Highly flexible
•	Cost-effective
•	Quick 

It offers on-demand compute capacity that can be quickly launched, scaled and terminated. You only pay for running instances, not stopped or terminated instances.
You have complete control over what happens on your instance

Multitenancy: Virtual machines share resources on the same physical host, with isolation between them.
Vertical scaling: Making instance bigger or smaller depending on your needs.
The type of EC2 instance (how powerful you want it) and the Amazon machine Image(AMI) which determines the OS and software must be specified when launching an EC2 instance

LAUNCH    ->   CONNECT   -> USE


## Amazon EC2 Instance Types
Each Amazon EC2 instance type is grouped under an instance family:
- General purpose:
Has Balanced Resources -> Diverse workloads, Web servers, Code repositories
- Compute optimized:
For Compute-intensive tasks -> Gaming servers, High performance computing (HPC), Scientific modelling
- Memory optimized:
For Memory-intensive tasks -> processing large datasets, data analytics, and databases
- Accelerated computing:
Uses Hardware accelerators -> Floating point number calculations, Graphics processing, Data pattern matching
- Storage optimized:
For workloads requiring High performance for locally stored data -> large databases, data warehousing and I/O-intensive applications

## Interacting with AWS services
API – Application programming interface 
The customer handles the operating system, networking, and applications on the EC2 instances. AWS manages the hardware.

### 3 main ways to call AWS APIs:
1.	AWS Management Console
•	Set up test environments
•	View AWS bills
•	View monitoring
•	Work with non-technical resources

2.	AWS Command Line Interface (CLI)
Make API calls using the terminal on your machine through commands
aws ec2 run-instances
aws ec2 describe-availability-zones

3.	AWS Software Development Kit (SDK)
Interact with AWS resources through various programming languages like Python

## Launching an EC2 instance
Using AWS Management Console:
1.	Go to the EC2 console by searching etc
2.	‘Launch instance’
3.	Give name to the instance
4.	Choose the AMI  (Amazon Linux, macOS, Windows etc)
5.	Choose the instance type (how much computing power the web server will have)
6.	Choose the Key pair (login) – can create too
7.	Choose Network settings
Check the ‘Allow HTTP traffic from the internet’
8.	Choose the Configure storage
9.	Go to the Advanced details -> User data( allows us to past a script to install and activate  Nginx webserver
10.	Launch instance
11.	Copy the public IP address
12.	 Paste it on a new browser to get your own EC2 running basic web server 

AMI Components -> Operating system, storage setup, architecture type, permissions for launching, and any extra software that is already installed.
Three ways to use AMI:
1.	Create your own 
2.	Use pre-configured AWS AMIs
3.	Purchase AMIs from AWS Marketplace
AMI repeatability
Same configuration --> Automated deployments --> Consistent environments --> Scaling with confidence


## Amazon EC2 Pricing
### Purchase options:
- On-Demand Instances – pay for the compute capacity you consume
- Savings Plans – up to 72% discount across a variety of instance types by committing to a consistent usage level for 1 or 3 years 
- Reserved Instances – up to 75% discount after committing to 1- or 3-year term for predictable workloads using specific instance families and AWS regions
- Spot Instances – request excess EC2 instance at up to 90% discount with the flexibility to be interrupted when AWS reclaims the instance
- Dedicated Hosts – reserve a physical server for exclusive use. Offers full control and ideal for workloads with strict security or licensing needs.
- Dedicated Instances – pay for running instances on hardware dedicated solely to your account. Provides isolation from other AWS customers.

### Pricing options
1. Savings Plans: for predictable workloads
Offer discounts in exchange for a commitment to use a specified amount of compute power over 1- or 3-year period.
Provides flexible pricing for Amazon EC2, AWS Fargate, AWS Lambda and Amazon SageMaker AI usage, regardless of instance type or AWS region.
Payment options – All upfront, Partial upfront, or No upfront
2. Capacity Reservations: for critical workloads with strict capacity requirements
Reserve compute capacity in a specific Availability Zone for critical workloads. 
Only pay for the instances you run.
Ideal for strict capacity requirements for current or future business-critical workloads
3. Reserved Instance flexibility: for steady-state workloads with predictable usage
Offers up to 75% savings by applying discounts across instance sizes and multiple Availability Zones within a Region. 
AWS automatically applies the discount to other instance sizes within the same family based on the instance size footprint.
Applies discount across multiple Availability Zones for enhanced resource distribution and fault tolerance


## Scaling Amazon EC2
Scalability ->
Ability of a system to handle an increased load by  adding resources. Scale up (vertical scaling) by adding more power to existing machines or Scale out (horizontal scaling) by adding more machines. Focuses on long-term capacity planning to make sure that the system can grow and accommodate more users or workloads as needed.

Elasticity ->
Ability to automatically scale resources up or down in response to real-time demand. A system can rapidly scale out during periods of high demand and scale in when the demand decreases. Provides cost efficiency and optimal resource usage at any given moment.

## Amazon EC2 Auto Scaling
Automatically adjust the number of EC2 instances based on changes in application demand, providing better availability. 

Dynamic scaling – adjusts in real time to fluctuations in demand

Predictive scaling  - pre-emptively schedules the right number of instances based on anticipated demand

Auto Scaling group = collections of EC2 instances than can scale in or out to needs
Configured with three key settings:
1.	Minimum capacity – least number of EC2 instances required to keep the application running
2.	Desired capacity – ideal number of instanced needed to handle the current workload (default is minimum capacity)
3.	Maximum capacity – upper limit on the number of instances than can be launched, preventing over-scaling and controlling costs.

## Directing Traffic with Elastic Load Balancing
Elastic Load Balancing (ELB) 

Automatically distributes incoming application traffic across multiple resources to  optimize performance and reliability. 
A load balancer serves as the single point of contact for all incoming web traffic to an Auto Scaling group. As the number of EC2 instances fluctuates in response to traffic demands, incoming requests are first directed to the load balancer. From there, the traffic is distributed evenly across the available instances.
Although ELB and Amazon EC2 Auto Scaling are distinct services, they work in tandem to enhance application performance and ensure high availability. Together, they enable applications running on Amazon EC2 to scale effectively while maintaining consistent performance.

### Benefits of ELB:
- Efficient traffic distribution – evenly distributes traffic across EC2 instances, preventing overload and optimizing resource utilization
- Automatic scaling – scales traffic and automatically adjusts to changes in demand for a seamless operation as backend instanced are added or removed
- Simplified management – decouples front-end and backend tiers and reduces manual synchronization. Handles maintenance, updates and failover to ease operational  overhead

Routing methods:
-	Round Robin – distributes traffic evenly across all available servers in cyclic manner 
-	Least Connections – routes traffic to the server with the fewest active connections, maintaining a balanced load
-	IP Hash – used the client’s IP address to consistently route traffic to the same server
-	Least Response Time – directs traffic to the server with the fastest response time, minimizing latency
