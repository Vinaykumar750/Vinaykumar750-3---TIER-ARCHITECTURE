\# 3-Tier AWS Architecture



\## Project Overview



This project demonstrates the implementation of a \*\*3-Tier Architecture on AWS\*\* for a web application.



The architecture is divided into three main layers:



1\. \*\*Web Tier / Presentation Layer\*\*

2\. \*\*Application Tier / Business Logic Layer\*\*

3\. \*\*Database Tier / Data Layer\*\*



The project uses AWS services such as \*\*Amazon VPC, EC2, Application Load Balancer, Auto Scaling, NAT Gateway, Internet Gateway, and Amazon RDS\*\* to build a scalable, highly available, and secure infrastructure.



\## Architecture



```text

&#x20;                        Internet

&#x20;                           |

&#x20;                    Internet Gateway

&#x20;                           |

&#x20;                   Public Subnets

&#x20;                    /           \\

&#x20;               ALB - Web Tier

&#x20;                 /             \\

&#x20;             EC2 Web          EC2 Web

&#x20;                \\               /

&#x20;                 \\             /

&#x20;                 Application ALB

&#x20;                      |

&#x20;                Private Subnets

&#x20;                 /           \\

&#x20;            EC2 App        EC2 App

&#x20;                 \\           /

&#x20;                  \\         /

&#x20;                   Amazon RDS

&#x20;                  MySQL Database

```



\## AWS Services Used



\* \*\*Amazon VPC\*\* – Creates the isolated network environment.

\* \*\*Public Subnets\*\* – Host resources that require internet access.

\* \*\*Private Subnets\*\* – Host application and database resources.

\* \*\*Internet Gateway\*\* – Provides internet connectivity for public subnets.

\* \*\*NAT Gateway\*\* – Provides outbound internet access for private subnets.

\* \*\*Amazon EC2\*\* – Hosts the web and application servers.

\* \*\*Application Load Balancer (ALB)\*\* – Distributes incoming traffic across instances.

\* \*\*Auto Scaling Group\*\* – Automatically manages EC2 capacity based on demand.

\* \*\*Amazon RDS\*\* – Provides the MySQL database.

\* \*\*Security Groups\*\* – Control inbound and outbound network traffic.

\* \*\*AMI\*\* – Used to create reusable EC2 machine images.

\* \*\*Launch Template\*\* – Defines the configuration for EC2 instances.



\## Network Configuration



The project uses:



\* VPC CIDR: `20.0.0.0/16`

\* 2 Availability Zones

\* 2 Public Subnets

\* 4 Private Subnets

\* 1 Internet Gateway

\* 2 NAT Gateways

\* Route Tables for public and private subnets



Public subnets use the Internet Gateway for internet access, while private subnets use NAT Gateways for outbound connectivity.



\## Web Tier



The Web Tier handles user requests and provides the presentation layer.



The project uses:



\* EC2 instances

\* Application Load Balancer

\* Public subnets

\* Security Groups



The Application Load Balancer distributes incoming requests between healthy EC2 instances.



\## Application Tier



The Application Tier contains the application's business logic and processing.



It uses:



\* EC2 instances

\* Private subnets

\* Application Load Balancer

\* Auto Scaling



The application instances are placed in private subnets to provide additional network isolation.



\## Database Tier



The Database Tier stores application data using \*\*Amazon RDS with MySQL\*\*.



Configuration includes:



\* RDS MySQL

\* DB Subnet Group

\* Multi-AZ configuration

\* Private subnet placement

\* Database connectivity from the application tier



\## Auto Scaling



An Auto Scaling Group is configured using:



\* Launch Template

\* Desired Capacity

\* Minimum Size

\* Maximum Size

\* Scaling Policies

\* Load Balancer integration



Auto Scaling helps automatically increase or decrease the number of EC2 instances based on application requirements.



\## Load Balancing



Two Application Load Balancers are used:



\* Web Tier Load Balancer

\* Application Tier Load Balancer



Target Groups are configured to register EC2 instances and perform health checks before routing traffic.



\## Database Connectivity



The application tier connects to the Amazon RDS MySQL database using the RDS endpoint.



Example:



```bash

mysql -h <RDS-ENDPOINT> -u admin -p

```



After connecting to MySQL, a database and table can be created and accessed by the application.



\## Key Concepts Demonstrated



\* AWS VPC

\* CIDR and subnetting

\* Public and private subnets

\* Availability Zones

\* Internet Gateway

\* NAT Gateway

\* Route Tables

\* Security Groups

\* Amazon EC2

\* AMI

\* Launch Templates

\* Application Load Balancer

\* Target Groups

\* Auto Scaling

\* Amazon RDS

\* MySQL

\* Multi-Tier Architecture

\* High Availability

\* Scalability

\* Network Security



\## Project Outcome



The project demonstrates how to design and implement a scalable three-tier application architecture on AWS.



The infrastructure separates the presentation, application, and database layers, providing better organization, scalability, availability, and security.



\## Project Documentation



Detailed project documentation, AWS configuration steps, screenshots, and implementation details are available in:



\*\*3-TIER-ARCHITECTURE-BY-VINAY.pdf\*\*



\## Author



\*\*R. Vinay Kumar\*\*



AWS | Cloud | DevOps



\## Repository Structure



```text

3-Tier-AWS-Architecture/

│

├── README.md

└── 3-TIER-ARCHITECTURE-BY-VINAY.pdf

```



