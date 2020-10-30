# Amazon Web Services

 <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.7.2/animate.min.css"
    />
<div class="animated fadeIn">
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
<div style="background-color:#d7cfa5;padding:10px;border-radius:10px">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1d/AmazonWebservices_Logo.svg/1200px-AmazonWebservices_Logo.svg.png"></div>

> If a person doesn’t know to which port they sail, no wind is favourable -Seneca
- - - -
#### Articles:
https://www.freecodecamp.org/news/how-to-take-any-aws-certification-from-home/

https://www.freecodecamp.org/news/how-i-passed-the-aws-certified-developer-associate-exam/

https://adayinthelifeof.nl/2020/05/20/aws.html - AWS services explained in a single line

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

EBS and EFS storage can be attached to EC2 instances

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

#### Data Types:

Amazon Simple Storage Service (Amazon S3)
Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. This means customers of all sizes and industries can use it to store and protect any amount of data for a range of use cases, such as websites, mobile applications, backup and restore, archive, enterprise applications, IoT devices, and big data analytics. Amazon S3 provides easy-to-use management features so you can organize your data and configure finely-tuned access controls to meet your specific business, organizational, and compliance requirements.   More information on Amazon S3 is available at: https://aws.amazon.com/s3/

Amazon S3 Glacier
Amazon S3 Glacier is a secure, durable, and extremely low-cost cloud storage service for data archiving and long-term backup. It is designed to deliver 99.999999999% durability, and provides comprehensive security and compliance capabilities that can help meet even the most stringent regulatory requirements.  More information on Amazon S3 Glacier can be found at: https://aws.amazon.com/glacier/ 

Amazon Relational Database Service (Amazon RDS)
Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks such as hardware provisioning, database setup, patching and backups. It frees you to focus on your applications so you can give them the fast performance, high availability, security and compatibility they need.

Amazon RDS is available on several database instance types - optimized for memory, performance or I/O - and provides you with six familiar database engines to choose from, including Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle Database, and SQL Server. You can use the AWS Database Migration Service to easily migrate or replicate your existing databases to Amazon RDS.  More information on Amazon RDS can be found at: https://aws.amazon.com/rds/ 

Amazon DynamoDB
Amazon DynamoDB is a key-value and document database that delivers single-digit millisecond performance at any scale. It's a fully managed, multiregion, multimaster database with built-in security, backup and restore, and in-memory caching for internet-scale applications. DynamoDB can handle more than 10 trillion requests per day and can support peaks of more than 20 million requests per second.  More information on Amazon DynamoDB can be found at: https://aws.amazon.com/dynamodb/ 

Amazon Timestream
Amazon Timestream is a fast, scalable, fully managed time series database service for IoT and operational applications that makes it easy to store and analyze trillions of events per day at 1/10th the cost of relational databases.  Details on Amazon Timestream can be found at: https://aws.amazon.com/timestream/ 

Amazon Quantum Ledger Database (QLDB)
Amazon QLDB is a fully managed ledger database that provides a transparent, immutable, and cryptographically verifiable transaction log ‎owned by a central trusted authority. Amazon QLDB tracks each and every application data change and maintains a complete and verifiable history of changes over time.

Amazon QLDB is a new class of database that eliminates the need to engage in the complex development effort of building your own ledger-like applications. With QLDB, your data’s change history is immutable – it cannot be altered or deleted – and using cryptography, you can easily verify that there have been no unintended modifications to your application’s data.   Details about Amazon QLDB can be found at: https://aws.amazon.com/qldb/

Amazon Elastic Block Store
Amazon Elastic Block Store (EBS) is an easy to use, high performance block storage service designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction intensive workloads at any scale. A broad range of workloads, such as relational and non-relational databases, enterprise applications, containerized applications, big data analytics engines, file systems, and media workflows are widely deployed on Amazon EBS.  More information on Amazon EBS is available at: https://aws.amazon.com/ebs/

Amazon Elastic File System
Amazon Elastic File System (Amazon EFS) provides a simple, scalable, elastic file system for Linux-based workloads for use with AWS Cloud services and on-premises resources.  Amazon EFS is well suited to support a broad spectrum of use cases from highly parallelized, scale-out workloads that require the highest possible throughput to single-threaded, latency-sensitive workloads. Use cases such as lift-and-shift enterprise applications, big data analytics, web serving and content management, application development and testing, media and entertainment workflows, database backups, and container storage.  More information about Amazon EFS can be found at: https://aws.amazon.com/efs/

Amazon Redshift
Amazon Redshift extends data warehouse queries to your data lake, with no loading required. You can run analytic queries against petabytes of data stored locally in Redshift, and directly against exabytes of data stored in Amazon S3. It is simple to set up, automates most of your administrative tasks, and delivers fast performance at any scale.  Information about Amazon Redshift  is available at: https://aws.amazon.com/redshift/ 

Amazon Athena
Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. Athena is serverless, so there is no infrastructure to manage, and you pay only for the queries that you run.

Athena is easy to use. Simply point to your data in Amazon S3, define the schema, and start querying using standard SQL. Most results are delivered within seconds. With Athena, there’s no need for complex ETL jobs to prepare your data for analysis. This makes it easy for anyone with SQL skills to quickly analyze large-scale datasets.  Details about Amazon Athena can be found at: https://aws.amazon.com/athena/ 

Data Transfer
AWS Snowball
Snowball is a petabyte-scale data transport solution that uses devices designed to be secure to transfer large amounts of data into and out of the AWS Cloud.   Snowball devices use tamper-resistant enclosures, 256-bit encryption, and an industry-standard Trusted Platform Module (TPM) designed to ensure both security and full chain-of-custody for your data. More information about AWS Snowball can be found at: https://aws.amazon.com/snowball/ 

AWS Snowmobile
AWS Snowmobile is an Exabyte-scale data transfer service used to move extremely large amounts of data to AWS. You can transfer up to 100PB per Snowmobile, a 45-foot long ruggedized shipping container, pulled by a semi-trailer truck. Snowmobile makes it easy to move massive volumes of data to the cloud, including video libraries, image repositories, or even a complete data center migration. Transferring data with Snowmobile is more secure, fast and cost effective.  Information about how to get started with AWS Snowmobile can be found at: https://aws.amazon.com/snowmobile/ 


#### Encryption in Transit and at Rest

Encryption of Data in Transit
You can mount a file system so all NFS traffic is encrypted in transit using Transport Layer Security 1.2 (TLS, formerly called Secure Sockets Layer [SSL]) with an industry-standard AES-256 cipher. TLS is a set of industry-standard cryptographic protocols used for encrypting information that is exchanged over the wire. AES-256 is a 256-bit encryption cipher used for data transmission in TLS. If your organization is subject to corporate or regulatory policies that require encryption of data and metadata in transit, we recommend setting up encryption in transit on every client accessing the file system. More information on Encryption of data in transit can be found at: https://docs.aws.amazon.com/whitepapers/latest/efs-encrypted-file-systems/encryption-of-data-in-transit.html

Encryption of Data at Rest
You can create an encrypted file system so all your data and metadata is encrypted at rest using an industry-standard AES-256 encryption algorithm. Encryption and decryption is handled automatically and transparently, so you don’t have to modify your applications. If your organization is subject to corporate or regulatory policies that require encryption of data and metadata at rest, we recommend creating an encrypted file system.

AWS Key Management Service (KMS)
AWS Key Management Service (KMS) makes it easy for you to create and manage keys and control the use of encryption across a wide range of AWS services and in your applications. AWS KMS is a secure and resilient service that uses FIPS 140-2 validated hardware security modules to protect your keys. AWS KMS is integrated with AWS CloudTrail to provide you with logs of all key usage to help meet your regulatory and compliance needs. More details on AWS KMS can be found at:https://aws.amazon.com/kms/

AWS CloudHSM
AWS CloudHSM is a cloud-based hardware security module (HSM) that enables you to easily generate and use your own encryption keys on the AWS Cloud. With CloudHSM, you can manage your own encryption keys using FIPS 140-2 Level 3 validated HSMs. CloudHSM offers you the flexibility to integrate with your applications using industry-standard APIs, such as PKCS#11, Java Cryptography Extensions (JCE), and Microsoft CryptoNG (CNG) libraries. CloudHSM is standards-compliant and enables you to export all of your keys to most other commercially-available HSMs, subject to your configurations. It is a fully-managed service that automates time-consuming administrative tasks for you, such as hardware provisioning, software patching, high-availability, and backups. CloudHSM also enables you to scale quickly by adding and removing HSM capacity on-demand, with no up-front costs. More information on AWS CloudHSM can be found at:https://aws.amazon.com/cloudhsm/

#### Encryption at rest and in transit (Databases)
Amazon RDS allows you to encrypt your databases using keys you manage through AWS Key Management Service (KMS). On a database instance running with Amazon RDS encryption, data stored at rest in the underlying storage is encrypted, as are its automated backups, read replicas, and snapshots.

Amazon RDS supports Transparent Data Encryption in SQL Server and Oracle. Transparent Data Encryption in Oracle is integrated with AWS CloudHSM, which allows you to securely generate, store, and manage your cryptographic keys in single-tenant Hardware Security Module (HSM) appliances within the AWS cloud.

Amazon RDS supports the use of SSL to secure data in transit.

Network isolation
AWS recommends that you run your database instances in Amazon VPC, which allows you isolate your database in your own virtual network and connect to your on-premises IT infrastructure using industry-standard encrypted IPsec VPNs. You can configure firewall settings and control network access to your database instances.

Resource-level permissions
Amazon RDS is integrated with AWS Identity and Access Management (IAM) and provides you the ability to control the actions that your AWS IAM users and groups can take on specific Amazon RDS resources, from database instances through snapshots, parameter groups, and option groups. You can also tag your Amazon RDS resources and control the actions that your IAM users and groups can take on groups of resources that have the same tag and associated value. For example, you can configure your IAM rules to ensure developers are able to modify "Development" database instances, but only Database Administrators can make changes to "Production" database 

Information on Amazon RDS Security can be found at​ https://aws.amazon.com/rds/features/#security

#### S3 Encryption:

Amazon S3 default encryption provides a way to set the default encryption behavior for an S3 bucket. You can set default encryption on a bucket so that all objects are encrypted when they are stored in the bucket. The objects are encrypted using server-side encryption with either Amazon S3-managed keys (SSE-S3) or AWS KMS-managed keys (SSE-KMS).

When you use server-side encryption, Amazon S3 encrypts an object before saving it to disk in its data centers and decrypts it when you download the objects.  More details on using Encryption with Amazon S3 can be found at: https://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html

Amazon Macie 
Amazon Macie is a security service that uses machine learning to automatically discover, classify, and protect sensitive data in AWS. Amazon Macie recognizes sensitive data such as personally identifiable information (PII) or intellectual property, and provides you with dashboards and alerts that give visibility into how this data is being accessed or moved. The fully managed service continuously monitors data access activity for anomalies, and generates detailed alerts when it detects risk of unauthorized access or inadvertent data leaks. Currently, Amazon Macie is available to protect data stored in Amazon S3.  More information about Amazon Macie is available at: https://aws.amazon.com/macie/

#### Elastic Block Storage (EBS) Encryption:

Amazon EBS encryption offers seamless encryption of EBS data volumes, boot volumes and snapshots, eliminating the need to build and manage a secure key management infrastructure. EBS encryption enables data at rest security by encrypting your data volumes, boot volumes and snapshots using Amazon-managed keys or keys you create and manage using the AWS Key Management Service (KMS). In addition, the encryption occurs on the servers that host EC2 instances, providing encryption of data as it moves between EC2 instances and EBS data and boot volumes. For more information, see Amazon EBS encryption in the Amazon EC2 User Guide.

Access to Amazon EBS volumes is integrated with AWS Identity and Access Management (IAM). IAM enables access control to your Amazon EBS volumes. For more information, see AWS Identity and Access Management.  For more information about Amazon EBS encryption, see: https://aws.amazon.com/ebs/features/

#### Securing Amazon EC2 Instances
The process for securing EC2 instances involves principles that are applicable to any OS, whether running in a virtual machine or on premises:

Least Access: Restrict server access from both the network and on the instance, install only the required OS components and applications, and leverage host-based protection software.

Least Privilege: Define the minimum set of privileges each server needs in order to perform its function.
Configuration Management: Create a baseline server configuration and track each server as a configuration item. Assess each server against the current recorded baseline to identify and flag any deviations. Ensure each server is configured to generate and securely store appropriate log and audit data.

Change Management: Create processes to control changes to server configuration baselines.

Audit Logs: Audit access and all changes to EC2 instances to verify server integrity to ensure only authorized changes are made.

For more information on securing EC2 instances please see: https://aws.amazon.com/answers/security/aws-securing-ec2-instances/

This white paper provides an overview of security when using Lambda: https://d1.awsstatic.com/whitepapers/Overview-AWS-Lambda-Security.pdf

Amazon Elastic Container Service (Amazon ECS)
Amazon ECS allows you to specify an IAM role for each ECS task. This allows the Amazon ECS container instances to have a minimal role, respecting the ‘least privilege’ access policy and allowing you to manage the instance role and the task role separately. You can also use Amazon CloudWatch Logs to gain visibility into the IAM role to which a task is assigned.  More details on Amazon ECS can be found at: https://aws.amazon.com/ecs/features/



#### Amazon API Gateway

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. With a few clicks in the AWS Management Console, you can create REST and WebSocket APIs that act as a “front door” for applications to access data, business logic, or functionality from your backend services, such as workloads running on Amazon Elastic Compute Cloud (Amazon EC2), code running on AWS Lambda, any web application, or real-time communication applications.  Information about Amazon API Gateway can be found at: https://aws.amazon.com/api-gateway/

#### AWS Shield
AWS Shield is a managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS. AWS Shield provides always-on detection and automatic inline mitigations that minimize application downtime and latency, so there is no need to engage AWS Support to benefit from DDoS protection. There are two tiers of AWS Shield - Standard and Advanced.  Details on AWS Shield are available at: https://aws.amazon.com/shield/

#### AWS WAF
AWS WAF is a web application firewall that helps protect your web applications from common web exploits that could affect application availability, compromise security, or consume excessive resources. AWS WAF gives you control over which traffic to allow or block to your web applications by defining customizable web security rules. You can use AWS WAF to create custom rules that block common attack patterns, such as SQL injection or cross-site scripting, and rules that are designed for your specific application. New rules can be deployed within minutes, letting you respond quickly to changing traffic patterns. Also, AWS WAF includes a full-featured API that you can use to automate the creation, deployment, and maintenance of web security rules.  Details on AWS WAF are available at: https://aws.amazon.com/waf/

#### Secrets Manager
AWS Secrets Manager helps you protect secrets needed to access your applications, services, and IT resources. The service enables you to easily rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle. Users and applications retrieve secrets with a call to Secrets Manager APIs, eliminating the need to hardcode sensitive information in plain text. Secrets Manager offers secret rotation with built-in integration for Amazon RDS, Amazon Redshift, and Amazon DocumentDB. Also, the service is extensible to other types of secrets, including API keys and OAuth tokens. In addition, Secrets Manager enables you to control access to secrets using fine-grained permissions and audit secret rotation centrally for resources in the AWS Cloud, third-party services, and on-premises.  More details on AWS Secrets Manager is available at: https://aws.amazon.com/secrets-manager/

#### AWS Well-Architected
The Well-Architected Framework has been developed to help cloud architects build secure, high-performing, resilient, and efficient infrastructure for their applications. Based on five pillars — operational excellence, security, reliability, performance efficiency, and cost optimization — the Framework provides a consistent approach for customers and partners to evaluate architectures, and implement designs that will scale over time.

### Migration:

* Migration Preparation and Business Planning
* Portfolio discovery and planning
* Designing,Migrating and planning your applications
* Operate

6Rs of Migrating to the cloud:
https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/

----
#### A​WS Cloud Adoption Framework (AWS CAF):

[The AWS Cloud Adoption Framework (AWS CAF)](https://aws.amazon.com/professional-services/CAF/) organizes guidance into six areas of focus, called perspectives. Each perspective covers distinct responsibilities owned or managed by functionally related stakeholders. In general, the Business, People, and Governance Perspectives focus on business capabilities; while the Platform, Security, and Operations Perspectives focus on technical capabilities.

This content is part of [Amazon Web Services (AWS) Prescriptive Guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/mrp-solution/overview.html), which provides time-tested strategies, guides, and patterns to help accelerate your cloud adoption

----
How to Migrate:

The [four-phase migration process](https://aws.amazon.com/cloud-migration/how-to-migrate/) is designed to help your organization approach a migration of tens, hundreds, or thousands of applications. While each phase is a common component of a successful migration, they are not discrete phases, but an iterative process.

#### E​lastic Beanstalk

With Elastic Beanstalk, you can quickly deploy and manage applications in the AWS Cloud without having to learn about the infrastructure that runs those applications. Elastic Beanstalk reduces management complexity without restricting choice or control. This can be a useful tool for you to utilize when testing functionality of your applications in AWS. Checkout these Elastic Beanstalk [tutorials](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/tutorials.html) and [concepts](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.html) for more info.

#### T​he Security Pillar

It is important, while evaluating your portfolio, to evaluate the ability to protect your information, systems, and assets. Security should be a major part of the planning, and should be considered from early in the process all the way through to operational phases of your migrations. Here's more info about the [Security pillar](https://wa.aws.amazon.com/wat.pillar.security.en.html). You can also checkout the following articles to learn about how to protect your data [in transit](https://wa.aws.amazon.com/wat.question.SEC_10.en.html) and [at rest](https://wa.aws.amazon.com/wat.question.SEC_9.en.html).

#### A​WS Migration HUB

[AWS Migration Hub](https://aws.amazon.com/migration-hub/faqs/) provides a rich web experience that helps you understand your existing IT assets as well as view and track progress of application migrations. It lets you collect and view data about on-premises resources, group those resources into applications, and track the progress of those applications as you migrate to AWS.

----

Database migration is a complex, multiphase process, which usually includes assessment, database schema conversion script conversion, data migration, functional testing, performance tuning, and many other steps. Read this blog for more info: [Database Migration - What Do You Need to Know Before You Start?](https://aws.amazon.com/blogs/database/database-migration-what-do-you-need-to-know-before-you-start/)

Migration Delivery Partners

[Migration Delivery Partners](https://aws.amazon.com/migration/partner-solutions/) help customers through every stage of migration, accelerating results by providing personnel, tools, and education in the form of professional services. These partners either are, or have a relationship with, an AWS audited Managed Service Provider to help you with ongoing support of AWS workloads.

----

#### AWS Storage Services

AWS has many storage services that you are able to utilize for both block and object storage options, and within those services there are multiple options for you to evaluate. Finding the correct tool for the specific needs you have will be one of the most important tasks while you’re migrating. Checkout the following links to learn more about each topic:

* [A​mason Elastic File System](https://docs.aws.amazon.com/efs/latest/ug/how-it-works.html) (Amazon EFS)
*   [Amazon Elastic Block Store](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEBS.html) (Amazon EBS)
*   [A​mazon EBS Volume Types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html)
*    [A​mason Simple Storage Service (Amazon S3)](https://docs.aws.amazon.com/AmazonS3/latest/dev/Introduction.html)

----

 #### Data Transfer

Just as you should understand that secure data transfer is important, you should also consider that there are different types and styles of data transfer between environments. Whether a one-time migration, or ongoing data synchronization across environments, there are tools within AWS that can assist. Checkout the following links to learn more about each topic:

*    [A​WS Storage Gateway](https://docs.aws.amazon.com/storagegateway/latest/userguide/WhatIsStorageGateway.html)
*    [A​WS DataSync](https://docs.aws.amazon.com/datasync/latest/userguide/how-datasync-works.html)
*    [A​WS Snowball](https://docs.aws.amazon.com/snowball/latest/ug/snowball-transfer-client.html)
*    [A​WS Snowball FAQs](https://aws.amazon.com/snowmobile/faqs/)

----

#### AWS Server Migration Services

[AWS Server Migration Service](https://docs.amazonaws.cn/en_us/server-migration-service/latest/userguide/server-migration.html) (AWS SMS) automates the migration of your on-premises VMware vSphere, Microsoft Hyper-V/SCVMM, and Azure virtual machines to the AWS Cloud. AWS SMS incrementally replicates your server VMs as cloud-hosted Amazon Machine Images (AMIs) ready for deployment on Amazon EC2. Checkout AWS Server Migration Service [FAQs](https://aws.amazon.com/server-migration-service/faqs/) for more info.

----

#### Amazon Aurora

Amazon Aurora is a fully managed relational database engine that's compatible with MySQL and PostgreSQL. You already know how MySQL and PostgreSQL combine the speed and reliability of high-end commercial databases with the simplicity and cost-effectiveness of open-source databases. The code, tools, and applications you use today with your existing MySQL and PostgreSQL databases can be used with Aurora. Here's a quick [overview of Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html) and [how Aurora Serverless works](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless.how-it-works.html).

----

#### AWS DMS and AWS SCT

With AWS DMS, you can perform one-time migrations, and you can replicate ongoing changes to keep sources and targets in sync. Checkout [How AWS Database Migration Service Works](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Introduction.html) for more info. If you want to change database engines, you can use the [AWS Schema Conversion Tool](https://docs.aws.amazon.com/SchemaConversionTool/latest/userguide/CHAP_Welcome.html) (AWS SCT) to translate your database schema to the new platform. You then use AWS DMS to migrate the data.

----

#### Make Migration Easier:
Tools like the [AWS Command Line Interface](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html), [AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html), and [AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-whatis-howdoesitwork.html) all provide methods for you to automate actions being taken will not losing control over what you are doing. These enable the ability to make API calls to AWS in order to launch, configure, and manage services as well as giving access for control and management tasks within your servers’ systems. Here are additional resources that you might want checkout:

* [Working with SSM Agent](https://docs.aws.amazon.com/systems-manager/latest/userguide/ssm-agent.html)

* [A​WS CloudFormation Templates](https://aws.amazon.com/cloudformation/aws-cloudformation-templates/)

#### A​dditional Migration Resources:
AWS provides many tools to give you more of a hands-off approach to your migration tasks. Whether handling assessment, planning, or full application migration, there are several tools within AWS to utilize. 

* [Mi​grate to AWS with Confidence](https://aws.amazon.com/cloud-migration/#tools-and-services)
* [T​SO Logic](https://tsologic.com/)
* [C​loudEndure](https://www.cloudendure.com/live-migration/aws/)

#### Migration Delivery Partners
[Migration Delivery Partners](https://aws.amazon.com/migration/partner-solutions/) help customers through every stage of migration, accelerating results by providing personnel, tools, and education in the form of professional services. These partners either are, or have a relationship with, an AWS audited Managed Service Provider to help customers with ongoing support of AWS workloads.

#### Amazon Lex:

[Amazon Lex](https://docs.aws.amazon.com/lex/latest/dg/what-is.html) is a service for building conversational interfaces into any application using voice and text. Amazon Lex provides the advanced deep learning functionalities of automatic speech recognition (ASR) for converting speech to text, and natural language understanding (NLU) to recognize the intent of the text, to enable you to build applications with highly engaging user experiences and lifelike conversational interactions. With Amazon Lex, the same deep learning technologies that power Amazon Alexa are now available to any developer, enabling you to quickly and easily build sophisticated, natural language, conversational bots (“[chatbots](https://aws.amazon.com/what-is-a-chatbot/)”).

Amazon Lex pricing
With Amazon Lex, you pay only for what you use. You are charged based on the number of text or voice requests processed by your bot. Please see the [pricing page](https://aws.amazon.com/lex/pricing/) for current information.

#### What is Serverless?
[Serverless](https://aws.amazon.com/serverless/) is the native architecture of the cloud that enables you to shift more of your operational responsibilities to AWS, increasing your agility and innovation. Serverless allows you to build and run applications and services without thinking about servers. It eliminates infrastructure management tasks such as server or cluster provisioning, patching, operating system maintenance, and capacity provisioning. You can build them for [nearly any type of application](https://aws.amazon.com/serverless/#Serverless_Application_Use_Cases) or backend service, and everything required to run and scale your application with high availability is handled for you.

#### Amazon API Gateway
[Amazon API Gateway](https://aws.amazon.com/api-gateway/) is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. With a few clicks in the AWS Management Console, you can create an API that acts as a “front door” for applications to access data, business logic, or functionality from your back-end services, such as workloads running on Amazon Elastic Compute Cloud (Amazon EC2), code running on AWS Lambda, or any web application.

#### Mock Integrations in API Gateway
Amazon API Gateway supports mock integrations for API methods. This feature enables API developers to generate API responses from API Gateway directly, without the need for an integration backend. As an API developer, you can use this feature to unblock dependent teams that need to work with an API before the project development is complete. You can also use this feature to provision a landing page for your API, which can provide an overview of and navigation to your API. For an example of such a landing page, see the integration request and response of the GET method on the root resource of the example API discussed in [Build an API Gateway API from an Example](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-create-api-from-example.html).

Pricing

With Amazon API Gateway, you only pay when your APIs are in use. There are no minimum fees or upfront commitments. For HTTP/REST APIs, you pay only for the API calls you receive and the amount of data transferred out. Amazon API Gateway is Free Tier eligable and The Amazon API Gateway free tier includes one million API calls received for HTTP/REST APIs, and one million messages and 750,000 connection minutes for WebSocket APIs per month for up to 12 months. See the Amazon API Gateway pricing page for details. Amazon CloudFront

----

[Amazon CloudFront](https://aws.amazon.com/cloudfront/) is a global content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to your viewers with low latency and high transfer speeds. CloudFront is integrated with AWS – including physical locations that are directly connected to the AWS global infrastructure, as well as software that works seamlessly with services including AWS Shield for DDoS mitigation, Amazon S3, Elastic Load Balancing or Amazon EC2 as origins for your applications, and Lambda@Edge to run custom code close to your viewers. The cost to use CloudFront is based upon data transfer costs as well as requests and includes a free usage tier.

----

Origin Access Identity (OAI)

[Origin Access Identity](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html) provides a method to restrict access to S3 content to only a CloudFront Distribution.

#### Amazon DynamoDB

[Amazon DynamoDB](https://aws.amazon.com/dynamodb/) is a fast and flexible NoSQL database service for all applications that need consistent, single-digit millisecond latency at any scale. It is a fully managed cloud database and supports both document and key-value store models. Its flexible data model, reliable performance, and automatic scaling of throughput capacity make it a great fit for mobile, web, gaming, ad tech, IoT, and many other applications. Pricing for DynamoDB includes a non-expiring free tier allotment. AWS Identity and Access Management

[AWS Identity and Access Management (IAM)](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) is a web service that helps you securely control access to AWS resources. We typically use credentials from IAM Users or IAM Roles to authenticate with AWS when making API calls. We control the permissions for which API actions those Users or Roles can perform with IAM Policies.

An IAM role is an IAM identity that you can create in your account that has specific permissions. Unlike an IAM user, A role is intended to be assumable by anyone who needs it. Also, a role does not have standard long-term credentials such as a password or access keys associated with it. Instead, when you assume a role, it provides you with temporary security credentials for your role session.

IAM is a feature of your AWS account offered at no additional charge. You will be charged only for use of other AWS services by your users. Detailed information about AWS IAM can be found in the documentation.

#### AWS Lambda
[AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) lets you run code without provisioning or managing servers. AWS Lambda executes your code only when needed and scales automatically, from a few requests per day to thousands per second. You pay only for the compute time you consume - there is no charge when your code is not running.

Because your code is only running on-demand, in order to troubleshoot, you'll need to take advantage of [monitoring](https://docs.aws.amazon.com/lambda/latest/dg/troubleshooting.html). You can [troubleshoot Lambda with Amazon Cloudwatch](https://docs.aws.amazon.com/lambda/latest/dg/monitoring-functions.html) and also [troubleshoot Lambda with AWS X-Ray](https://docs.aws.amazon.com/lambda/latest/dg/lambda-x-ray.html).

With Lambda, there are [2 types of permissions](https://docs.aws.amazon.com/lambda/latest/dg/intro-permission-model.html) to be aware of. First, your code running in a [Lambda function is granted permissions by using an IAM Role](https://docs.aws.amazon.com/lambda/latest/dg/intro-permission-model.html#lambda-intro-execution-role). Second, the service triggering your Lambda function can be granted the permissions to do so with a [Lambda Function Policy](https://docs.aws.amazon.com/lambda/latest/dg/intro-permission-model.html#intro-permission-model-access-policy). When configuring triggers using the AWS Management Console, the console will create the necessary Lambda Function Policy for you when you enable the trigger.

If you want more details about what's available to your code as it runs inside AWS Lambda, you can find out more about the [Lambda execution environment](https://docs.aws.amazon.com/lambda/latest/dg/current-supported-versions.html) in the documentation.