# Amazon Web Services

<style>a{color:#997;background-color:black;padding:4px;border-radius:3px;}
/* body{background-color:darkgray} */
</style>

<img src="https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg" width=300 style="border-radius:4px" height=150>

>“You're going to pay a price for every bloody thing you do and everything you don't do. You don't get to choose to not pay a price. You get to choose which poison you're going to take. That's it." - *Jordan B Peterson*
- - - -
- What Is Cloud Computing?

```Cloud computing is the on-demand delivery of compute power, database storage, applications, and other IT resources through a cloud services platform via the internet with pay-as-you-go pricing.```

https://aws.amazon.com/what-is-cloud-computing/.

Infrastructure:

Amazon cloud computing resources are hosted in multiple locations world-wide. These locations are composed of AWS Regions, Availability Zones, and Local Zones. Each AWS Region is a separate geographic area. Each AWS Region has multiple, isolated locations known as Availability Zones.Resources aren't replicated across AWS Regions unless you do so specifically. 

Each AWS Region is designed to be isolated from the other AWS Regions. This design achieves the greatest possible fault tolerance and stability.

When you view your resources, you see only the resources that are tied to the AWS Region that you specified. This is because AWS Regions are isolated from each other, and we don't automatically replicate resources across AWS Regions. 

## AWS Free:
Note that before you use any of these services, you should check whether they are eligible for the AWS Free Tier: https://aws.amazon.com/free

## Compute services:
EC2,
LightSail

### EC2:
Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure and resizable compute capacity in the cloud. It's designed to make web-scale cloud computing easier for developers.

Amazon EC2 presents a true virtual computing environment, and it allows you to use web service interfaces to launch instances with a variety of operating systems, load them with your custom application environment, manage your network’s access permissions, and run your image by using as many or few systems as you want.

#### Amazon EC2 instance types:
Amazon EC2 provides a wide selection of instance types that are optimized to fit different use cases. Instance types comprise varying combinations of CPU, memory, storage, and networking capacity. They give you the flexibility to choose the appropriate mix of resources for your applications. Each instance type includes one or more instance sizes, which allows you to scale your resources to the requirements of your target workload. Current details about available instance types are available at: https://aws.amazon.com/ec2/instance-types/ 

- General Purpose:These instances provide a balance of compute,memory and networking resources,and can be used for a variety of diverse workloads.These instances are ideal for applications which use these resources in equal proportions such as web servers and code repositories.

- Compute Optimised:Compute optimised instances are ideal for compute bound applications which benefit from high performance processors.Instances belonging to this family are well suited for batch processing, dedicated gaming servers,ad server engines, machine learning inference, scientific modeling, high performance computing and other compute intensive applications.

- Memory Optimised: These instances deliver fast performance for workloads that process large data sets in memory.

- Accelarated Computing:Accelarated Computing Instances makes use of hardware accelarators or co-processors, to perform functions such as floating point number calculations,graphic processing or data pattern matching,more efficiently than is possible from software running on CPUs.

- Storage Optimised:Storage optimised instances are designed for workloads which require high,sequential read and write access to large sets of data in local storage.They are optimised to deliver tens of thousands of low latency,random I/O operations per second to applications.

#### Container services:Docker:ECS,Kubernetes:EKS,serverless:aws lambda

Complete list can be found at:
https://aws.amazon.com/products/compute/

### Lightsail:
Amazon Lightsail is the easiest way to get started with AWS for developers, small businesses, students, and other users who need a simple virtual private server (VPS) solution. Lightsail provides developers compute, storage, and networking capacity, and it also provides capabilities to deploy and manage websites and web applications in the cloud. Lightsail includes everything you need to launch your project quickly--a virtual machine, solid state drive (SSD)-based storage, data transfer, Domain Name System (DNS) management, and a static IP--for a low, predictable monthly price.

### CIDR Notation

An important concept that's used in networking on AWS is CIDR, or Classless Inter-Domain Routing. CIDR network addresses are allocated in a virtual private cloud (VPC) and in a subnet by using CIDR notation. A /16 block provides 65,536 IPv4 addresses. A /24 block provides 256 addresses. 

CIDR calculator:
http://www.subnet-calculator.com/cidr.php

### Virtual Private Cloud:
Amazon Virtual Private Cloud (Amazon VPC) lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including the selection of your own IP address range, the creation of subnets, and the configuration of route tables and network gateways. You can use both IPv4 and IPv6 in your VPC for secure and easy access to resources and applications. You could create up to five non-default VPCs per AWS account per Region. (See below for information about default VPCs.)

Details on Amazon VPC can be found here: https://aws.amazon.com/vpc

* Subnets
A VPC spans all the Availability Zones in the Region. After creating a VPC, you can add one or more subnets in each Availability Zone. When you create a subnet, you specify the CIDR block for the subnet, which is a subset of the VPC CIDR block. Each subnet must reside entirely within one Availability Zone, and it can't span Availability Zones.

    This is an important fundamental topic, and we strongly recommend that you review the information at: https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html

Default VPC

In each Region, AWS will provision a default VPC. This VPC has a /16 IPv4 CIDR address block of 172.31.0.0/16. This provides 65,536 private IPv4 addresses. In addition, there will be a /20 subnet that is created for each Availability Zone in the Region, which provides 4,096 addresses per subnet, with a few addresses reserved for AWS usage. The route table that is associated with the default VPC will have a public route, which in turn is associated with a provisioned internet gateway.

You can modify or delete the default VPC if you want to do so.

The most current details on the default VPC can be found here: https://docs.aws.amazon.com/vpc/latest/userguide/default-vpc.html