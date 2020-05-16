# Amazon Web Services

<link href="https://fonts.googleapis.com/css2?family=Montserrat&display=swap" rel="stylesheet">
<style>
a{color:#faedcb;background-color:#403d39;padding:4px;border-radius:3px;}
 body{background-color:#0c1821;color:#faedcb;line-height:2.0rem;font-size:1.0em;font-family:Montserrat}
 code{color:#eb5e28;}
 .vscode-light pre {
 background-color: rgba(32, 33, 36, 0.4);
 box-shadow: 0px 0px 2px 1px #00000070;
}
</style>
<div style="background-color:#403d39;padding:10px;border-radius:10px">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1d/AmazonWebservices_Logo.svg/1200px-AmazonWebservices_Logo.svg.png"></div>

>“Nothing is true. Everything is permitted" - Ezio Auditore da Firenze (Assassin's Creed)
- - - -
#### Articles:
https://www.freecodecamp.org/news/how-to-take-any-aws-certification-from-home/

https://www.freecodecamp.org/news/how-i-passed-the-aws-certified-developer-associate-exam/

- - - -
- What Is Cloud Computing?

```Cloud computing is the on-demand delivery of compute power, database storage, applications, and other IT resources through a cloud services platform via the internet with pay-as-you-go pricing.```

https://aws.amazon.com/what-is-cloud-computing/.

#### Infrastructure:

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

#### Lightsail:
Amazon Lightsail is the easiest way to get started with AWS for developers, small businesses, students, and other users who need a simple virtual private server (VPS) solution. Lightsail provides developers compute, storage, and networking capacity, and it also provides capabilities to deploy and manage websites and web applications in the cloud. Lightsail includes everything you need to launch your project quickly--a virtual machine, solid state drive (SSD)-based storage, data transfer, Domain Name System (DNS) management, and a static IP--for a low, predictable monthly price.

#### CIDR Notation:

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

#### Storage
RDS :Object

EBS:

Block Storage (EBS) is stored independent of EC2.When a new instance of EC2 is created the old EBS volumes can be attached to it.

"The Elastic Volume feature of Amazon EBS allows you to dynamically increase capacity, tune performance, and change the type of live volumes with no downtime or performance impact. This allows you to easily right-size your deployment and adapt to performance changes."

(EBS attaches to only one EC2)

#### Amazon Simple Storage Service (Amazon S3):

Amazon Simple Storage Service (Amazon S3) stores data as objects within resources that are called buckets. You can store as many objects as you want within a bucket, and you can write, read, and delete objects in your bucket. Objects can be up to 5 TB in size.

You can control access to both the bucket and the objects (who can create, delete, and retrieve objects in the bucket for example), and view access logs for the bucket and its objects. You can also choose the AWS Region where a bucket is stored to optimize for latency, minimize costs, or address regulatory requirements.

Full details on Amazon S3 can be found here: https://aws.amazon.com/s3.

Estimate your monthly bill by using the [AWS Simple Monthly Calculator](https://calculator.s3.amazonaws.com/index.html)


#### EFS FileSystem

Amazon Elastic File System (Amazon EFS) provides simple, scalable, elastic file storage for use with AWS Cloud services and on-premises resources. It is straightforward to use, and it offers a simple interface that allows you to create and configure file systems quickly and easily.

Amazon EFS is designed to provide massively parallel shared access to thousands of Amazon EC2 instances. This enables your applications to achieve high levels of aggregate throughput and IOPS that scale as a file system grows, with consistent low latencies.

When an Amazon EFS file system is mounted on Amazon EC2 instances, it provides a standard file system interface and file system access semantics, which allows you to seamlessly integrate Amazon EFS with your existing applications and tools. Multiple Amazon EC2 instances can access an Amazon EFS file system at the same time, thus allowing Amazon EFS to provide a common data source for workloads and applications that run on more than one Amazon EC2 instance.

Current details on Amazon EFS can be found at: https://aws.amazon.com/efs/

#### Databases:
RDS - Amazon Relational database service(sql based database):

Amazon Relational Database Service (Amazon RDS) makes it straightforward to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks such as provisioning hardware, setting up the database, patching, and making backups.

Amazon RDS currently supports six database engines:

* Amazon Aurora: https://aws.amazon.com/rds/aurora/

* PostgreSQL: https://aws.amazon.com/rds/postgresql/

* MySQL: https://aws.amazon.com/rds/mysql/

* MariaDB: https://aws.amazon.com/rds/mariadb/

* Oracle: https://aws.amazon.com/rds/oracle/

* Microsoft SQL Server: https://aws.amazon.com/rds/sqlserver/

You can use the AWS Database Migration Service (AWS DMS) (https://aws.amazon.com/dms) to quickly and securely migrate your databases to AWS.

Amazon RDS is eligible for the AWS Free Tier. More details on pricing for Amazon RDS are available here: https://aws.amazon.com/rds/pricing/


----
DynomoDB (nosql database):
[Amazon DynamoDB](https://aws.amazon.com/dynamodb) is a fast and flexible NoSQL database service for applications that need consistent, single-digit millisecond latency at any scale. Its a fully managed cloud database, and it supports both document and key-value store models. Its flexible data model, reliable performance, and automatic scaling of throughput capacity make it a great fit for mobile, web, gaming, advertising technology (ad tech), Internet of Things (IoT), and many other applications. [Pricing for DynamoDB](https://aws.amazon.com/dynamodb/pricing/) includes a non-expiring AWS Free Tier allotment.


#### Amazon CloudWatch

[Amazon CloudWatch](https://aws.amazon.com/cloudwatch/) is a monitoring service for AWS Cloud resources and the applications that you run on AWS. You can use Amazon CloudWatch to collect and track metrics, collect and monitor log files, set alarms, and automatically react to changes in your AWS resources.

----

Amazon CloudWatch Events:

[Amazon CloudWatch Events](https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/WhatIsCloudWatchEvents.html) delivers a near real-time stream of system events that describe changes in AWS resources. Using simple rules that you can quickly set up, you can match events and route them to one or more target functions or streams. CloudWatch Events becomes aware of operational changes as they occur.

----

Amazon CloudWatch Logs Metrics:

You can use [Amazon CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html) to monitor, store, and access your log files from Amazon EC2 instances, AWS CloudTrail, Amazon Route 53, and other sources. You can then retrieve the associated log data from CloudWatch Logs.

You can collect [metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CW_Support_For_AWS.html) from servers by installing the CloudWatch agent on the server. You can install the agent on both Amazon EC2 instances and on-premises servers, and on servers that run either Linux or Windows Server.

#### Elastic Load Balancing:

[Elastic Load Balancing (ELB)](https://aws.amazon.com/elasticloadbalancing/) automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, and IP addresses. It can handle the varying load of your application traffic in a single Availability Zone or across multiple Availability Zones.

ELB offers three types of load balancers that all feature the high availability, automatic scaling, and robust security that are necessary to make your applications fault-tolerant.

An Application Load Balancer operates at the request level (Layer 7), routing traffic to targets--such as EC2 instances, microservices and containers--within Amazon VPC, based on the content of the request. It's ideal for the advanced load balancing of Hypertext Transfer Protocol (HTTP) and Secure HTTP (HTTPS) traffic.

A Network Load Balancer operates at the connection level (Layer 4), routing connections to targets--such as Amazon EC2 instances, microservices, and containers--within Amazon VPC, based on IP protocol data. It's ideal for load-balancing Transmission Control Protocol (TCP) traffic.

The Classic Load Balancer provides basic load balancing across multiple Amazon EC2 instances, and it operates at both the request level and the connection level.

#### Auto scaling:

[Amazon EC2 Auto Scaling](https://aws.amazon.com/ec2/autoscaling) helps you maintain application availability, and it allows you to dynamically scale your Amazon EC2 capacity up or down automatically according to conditions that you define. You can use Amazon EC2 Auto Scaling for fleet management of Amazon EC2 instances, which can help maintain the health and availability of your fleet, and ensure that you are running your desired number of Amazon EC2 instances. You can also use Amazon EC2 Auto Scaling to dynamically scale Amazon EC2 instances. Dynamic scaling automatically increases the number of Amazon EC2 instances during demand spikes to maintain performance and decrease capacity during lulls, which can help reduce costs. Amazon EC2 Auto Scaling is well-suited to applications that have stable demand patterns, or applications that experience hourly, daily, or weekly variability in usage.

#### AWS Cost Explorer:

[AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/
) lets you visualize, understand, and manage your AWS costs and usage over time. You can create custom reports (including charts and tabular data) that analyze cost and usage data, both at a high level (e.g., total costs and usage across all accounts) and for highly specific requests (e.g., m2.2xlarge costs within account Y that are tagged project: secretProject).

----

AWS Trusted Advisor:

[AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/trustedadvisor/) is an online resource to help you reduce costs, increase performance, and improve security by optimizing your AWS environment. Trusted Advisor provides real-time guidance to help you provision your resources by following our best practices.

#### AWS Identity and Access Management (IAM):
 AWS Identity and Access Management (IAM) enables you to manage access to AWS services and resources securely. Using IAM, you can create and manage AWS users and groups, and use permissions to allow and deny their access to AWS resources. 

IAM is a feature of your AWS account offered at no additional charge. You will be charged only for use of other AWS services by your users.

To get started using IAM, or if you have already registered with AWS, go to the AWS Management Console and get started with these IAM Best Practices.

#### AWS Organizations
AWS Organizations helps you centrally govern your environment as you grow and scale your workloads on AWS. Whether you are a growing startup or a large enterprise, Organizations helps you to centrally manage billing; control access, compliance, and security; and share resources across your AWS accounts.  More information on AWS Organizations can be found at: https://aws.amazon.com/organizations/

#### Route Tables
A route table contains a set of rules, called routes, that are used to determine where network traffic is directed.

Each subnet in your VPC must be associated with a route table; the table controls the routing for the subnet. A subnet can only be associated with one route table at a time, but you can associate multiple subnets with the same route table.

#### AWS Direct Connect
AWS Direct Connect is a cloud service solution that makes it easy to establish a dedicated network connection from your premises to AWS. Using AWS Direct Connect, you can establish private connectivity between AWS and your datacenter, office, or colocation environment, which in many cases can reduce your network costs, increase bandwidth throughput, and provide a more consistent network experience than Internet-based connections.

AWS Direct Connect lets you establish a dedicated network connection between your network and one of the AWS Direct Connect locations. Using industry standard 802.1q VLANs, this dedicated connection can be partitioned into multiple virtual interfaces. This allows you to use the same connection to access public resources such as objects stored in Amazon S3 using public IP address space, and private resources such as Amazon EC2 instances running within an Amazon Virtual Private Cloud (VPC) using private IP space, while maintaining network separation between the public and private environments. Virtual interfaces can be reconfigured at any time to meet your changing needs.  More information including pricing for AWS Direct Connect is available at: https://aws.amazon.com/directconnect/ .

#### AWS CloudTrail 
AWS CloudTrail is a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account. With CloudTrail, you can log, continuously monitor, and retain account activity related to actions across your AWS infrastructure. CloudTrail provides event history of your AWS account activity, including actions taken through the AWS Management Console, AWS SDKs, command line tools, and other AWS services. This event history simplifies security analysis, resource change tracking, and troubleshooting.  More information about AWS CloudTrail can be found at: https://aws.amazon.com/cloudtrail/ .

#### AWS Config 
AWS Config is a service that enables you to assess, audit, and evaluate the configurations of your AWS resources. Config continuously monitors and records your AWS resource configurations and allows you to automate the evaluation of recorded configurations against desired configurations. With Config, you can review changes in configurations and relationships between AWS resources, dive into detailed resource configuration histories, and determine your overall compliance against the configurations specified in your internal guidelines. This enables you to simplify compliance auditing, security analysis, change management, and operational troubleshooting.  More information about AWS Config can be found at: https://aws.amazon.com/config/

#### Amazon Inspector
Amazon Inspector is an automated security assessment service that helps improve the security and compliance of applications deployed on AWS. Amazon Inspector automatically assesses applications for exposure, vulnerabilities, and deviations from best practices. After performing an assessment, Amazon Inspector produces a detailed list of security findings prioritized by level of severity. These findings can be reviewed directly or as part of detailed assessment reports which are available via the Amazon Inspector console or API.

Amazon Inspector security assessments help you check for unintended network accessibility of your Amazon EC2 instances and for vulnerabilities on those EC2 instances. Amazon Inspector assessments are offered to you as pre-defined rules packages mapped to common security best practices and vulnerability definitions. Examples of built-in rules include checking for access to your EC2 instances from the internet, remote root login being enabled, or vulnerable software versions installed. These rules are regularly updated by AWS security researchers.  More information on Amazon Inspector can be found at: https://aws.amazon.com/inspector/ 

#### Amazon GuardDuty
Amazon GuardDuty is a threat detection service that continuously monitors for malicious activity and unauthorized behavior to protect your AWS accounts and workloads. With the cloud, the collection and aggregation of account and network activities is simplified, but it can be time consuming for security teams to continuously analyze event log data for potential threats. With GuardDuty, you now have an intelligent and cost-effective option for continuous threat detection in the AWS Cloud. The service uses machine learning, anomaly detection, and integrated threat intelligence to identify and prioritize potential threats. GuardDuty analyzes tens of billions of events across multiple AWS data sources, such as AWS CloudTrail, Amazon VPC Flow Logs, and DNS logs. With a few clicks in the AWS Management Console, GuardDuty can be enabled with no software or hardware to deploy or maintain. By integrating with AWS CloudWatch Events, GuardDuty alerts are actionable, easy to aggregate across multiple accounts, and straightforward to push into existing event management and workflow systems.  More information about Amazon GuardDuty can be found at: https://aws.amazon.com/guardduty/ 

#### AWS Security Hub
AWS Security Hub gives you a comprehensive view of your high-priority security alerts and compliance status across AWS accounts. With Security Hub, you have a single place that aggregates, organizes, and prioritizes your security alerts, or findings, from multiple AWS services, such as Amazon GuardDuty, Amazon Inspector, and Amazon Macie, as well as from AWS Partner solutions. Your findings are visually summarized on integrated dashboards with actionable graphs and tables. You can also continuously monitor your environment using automated compliance checks based on the AWS best practices and industry standards your organization follows.   More information about AWS Security Hub can be found at: https://aws.amazon.com/security-hub/ 

