# Introduction to Networking	
Networking – interconnected devices that can exchange data and resources.
### Amazon Virtual Private Cloud (VPC) 
Provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. It provides 3 benefits:
-	Helps increase security because you can secure and monitor connections, screen traffic and restrict instance access.
-	Gives full control over resource placement, connectivity, and security.
-	Spend less time setting up, managing, and validating the virtual network

### Subnet
Used to organize your resources and can be made publicly or privately accessible.
-	A private subnet – used to contain resources like a database storing customer or transactional information
-	A public subnet – used for resources like a customer-facing website


### Organizing resources in the AWS Cloud

Internet gateway – connection between a VPC and the internet. 

Virtual Private Network (VPN) – creates a connection that is more like a secure tunnel through the internet. Using encryption, it hides and protects everything sent and received from outside eyes.

Virtual private gateway – component in the AWS Cloud that connects the protected traffic to enter the VPC, only if it is coming from an approved network.


### More Ways to Connect to the AWS Cloud
#### AWS Client VPN

Networking service that can be used to connect remote workers and on-premises networks to the cloud. 
-	It’s a fully managed , elastic VPN service that automatically scale up or down based on used demand.
-	It’s a cloud VPN solution; you don’t need to install and manage hardware or try to estimate how many remote users to support at one time
-	It uses an OpenVPN-based client, and it works with global Regions by using the AWS global network

Benefits: Provides advanced authentication, remote access. 

Use case: It can be used to quickly scale remote-worker access


#### AWS Site-to-Site VPN
Create a secure connection between the data centre or branch offices and AWS Cloud resources.

Benefits: Provides high availability, secure and private sessions, and accelerated applications

Use cases: For application migration and secure communication between remote locations.


#### AWS PrivateLink
Highly available, scalable technology that can be used to privately connect the VPC to services and resources as if they were in your VPC. 
-	Don’t need to use an internet gateway to allow communication with AWS services or resources from your private subnets.
-	You control the specific API endpoints, sites, services, and resources that are reachable from your VPC

Benefits: Helps secure traffic and connect with simplified management rules

Use case: For connecting your clients in your VPC to resources, other VPCs, and endpoints.


#### AWS Direct Connect
Service that establishes a dedicated private connection between your network and VPC in the AWS Cloud.
-	Bypasses the internet and provides a consistent, low-latency network experience. Making it ideal for applications that require high performance like video streaming
-	Ensures smooth and reliable data transfers at a massive scale for real-time analysis, rapid data backup, or broadcast media processing
-	Link your AWS and on-premises network to build applications that span environments without compromising performance.

Benefits: Reduces network costs and increases amount of bandwidth.


### Subnets, Security Groups, and Network Access Control Lists

Network traffic in a VPC: the movement of data packets travelling across a network

Packet: unit of data sent over the internet or a network which enters the VPS through an internet gateway

Network Access Control List: Virtual firewall that controls inbound and outbound traffic at the subnet level. 
-	The permissions define by the network ACLs indicate what packets are allowed or denied from the subnet. 
It is based on who sent the packet and how the packet is trying to communicate with the resources in a subnet
-	Each AWS account includes a default network ACL. When configuring your VPC, you can use the account’s default network ACL or create a custom network ACLs
-	All network ACLs have an explicit deny rule which makes sure that a packet matches any of the other rules on the list.

#### Stateless packet filtering: remember nothing and check packets that cross the subnet border each way, inbound and outbound

Security group: Virtual firewall that control inbound and outbound traffic for specific AWS resources, like Amazon EC2 instances
-	By default, denies all inbound traffic and allows all outbound traffic. You can add custom rules for the inbound traffic to configure which traffic should be allowed.
-	With multiple Amazon EC2 instances within the same VPC, you can associate them with the same security group or sue different ones for each instance

#### Stateful packet filtering: remember previous decisions made for incoming packets


## Amazon VPC Demo
#### Creating VPC
1.	Search and click on ‘VPC’
2.	Click on ‘Create VPC’
3.	Select ‘VPC only’ on Resources to create and give it a name on Name tag
4.	Enter the IPv4 address and select ‘Create VPC’

#### Create Subnets
1.	On your VPC dashboard, under the Virtual private cloud, choose Subnets
2.	Click on ‘Create subnet’ and on that page, choose your VPC on the VPC ID
3.	Name your subnet on Subnet name and choose use-east-1a on Availability Zone
4.	For IPv4 subnet CIDR block , write your subnet IP address range and click ‘Create subnet’
5.	Select the created subnet and select ‘Edit subnet settings’ from  ‘Actions’ 
6.	Under the Auto-assign IP settings, if the ‘Enable auto-assign public IPv4 address’ is not checked, it means that subnet is private. If not, its public subnet

When making multiple subnets, choose different Availability Zones and subnet IP address range.

#### Create internet gateway
1.	On your VPC dashboard, under the Virtual private cloud, choose Internet gateways
2.	Click on ‘Create internet gateway’ and on that page, give a name on Name tag
3.	Select ‘Create internet gateway’ and click on ‘Attach to VPC’ under ‘Actions’
4.	Choose your VPC and click on ‘Attach internet gateway’

#### Route table 

Set of rules called routes that are used to determine where network traffic is directed. Each subnet in VPS must be associated with a route table, and the table controls the routing for that subnet. 

#### Create route table
1.	On your VPC dashboard, under the Virtual private cloud, choose Route tables
2.	Click on ‘Create route table’ and on that page, give a name on Name tag
3.	Choose your VPC and click on ‘Create route table’
4.	In Routes, choose Edit routes and write 0.0.0.0/0 under Destination and click on Internet gateway and choose your created internet gateway under Target
5.	Select ‘Save changes’ 
6.	Select Subnet associations tab beside Routes and choose ‘Edit subnet associations’ 
7.	Choose your public subnets and click on ‘Save associations’


## Global Networking
### Edge networking services 

1. Edge networking – process of bringing information storage and computing abilities closer to the devices that produce that information and the users who consume it.

Edge computing is important because:
-	Organizations often need lower latency access to their data and content
-	Organization can deliver faster, more responsive experiences while maintaining better control over their infrastructure
-	Many different services are hosted on the edge, like the DNS service, Amazon Route 53

2. DNS resolution – process of translating a domain name to and IP address
-	It involves a customer DNS resolver communication with a company DNS server
1.	Customer enters the domain name into the browser; this request is sent to ta customer DNS resolver.
2.	The customer DNS resolver asks the company DNS server for the IP address that corresponds to the company website.
3.	The company DNS server responds by providing the IP address for the company website, (192.0.2.0)

### Amazon Route 53
DNS that provides a reliable and cost-effective way to route end users to internet applications.
-	Directs end users to your resources with globally dispersed DNS servers and automatic scaling
-	Gives developers and businesses a reliable way to route end users to internet applications hosted in AWS
-	Connects user requests to infrastructure running in AWS, such as Amazon EC2 instances and load balancers.
-	Routes users to infrastructure outside of AWS
-	Manages the DNS records for domain names 
-	Transfer DNS records for existing domain names managed by other domain registrars making it possible to manage multiple domain names within a single location

### Amazon CloudFront
Content delivery network (CDN) service that delivers content with faster loading times, cost savings, and reliability.
-	Stores copies of your content at locations closer to your user meaning websites, videos, images, and application load much faster no matter the location of customer.

Use cases:
-	Streaming video service – plays videos without buffering even when thousand of users log in simultaneously
-	Ecommerce website – product image and web pages
-	Mobile app – deliver map data and images 

### AWS Global Accelerator
Networking service that uses the AWS global network to improve application availability, performance, and security.
-	Uses intelligent traffic routing and fast failover on of the application locations fail
-	Provides static IP addresses, directing traffic over the AWS global network, and routing to optimal endpoints based on health, user location, and policies.

Use cases:
-	Global gaming company – reduce lag and provide smoother gameplay
-	Financial service application – check balances and make transactions without delays


## Global Architectures
Direct Connect failover when you need much higher  bandwidth with dedicated lines
1.	The customer network clients and servers need a secure, high-bandwidth connection for large data transfers and critical application performance.
2.	The customer has a content router or firewall connecting their network to Direct Connect
3.	In addition to fault tolerance, the customer wanted increased bandwidth. They can combine multiple connections to achieve higher aggregate bandwidth
4.	Using a virtual private gateway, the clients can securely access the private resources in the Amazon VPC.

### Delivering content to several different Regions globally
1.	The users access the company’s website using a custom domain. The request is first sent to a Route 53 DNS record.
2.	Route 53 uses a routing policy to determine which Region is closest to the user.
3.	Route 53 directs the user to the appropriate CloudFront edge location.
4.	The content is fetched from the designated origin server in the chosen Region. Also, the website was built with resources in multiple Availability Zones for high availability.
