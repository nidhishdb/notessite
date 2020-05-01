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


Container services:Docker:ECS,Kubernetes:EKS,serverless:aws lambda

Complete list can be found at:
https://aws.amazon.com/products/compute/

