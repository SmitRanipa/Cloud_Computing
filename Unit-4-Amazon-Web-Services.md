# Unit 4 — Amazon Web Services (AWS)

> **Subject:** CCBD (Cloud Computing & Basics of DevOps) | **Code:** 2301CS738

---

## 1. Getting Started with AWS

- **AWS CloudFormation** is used to launch resources — you submit a **template** (a text file) that describes a **stack** (collection of AWS resources to deploy together).
- You can use the **AWS Management Console** to create stacks from templates.
- Templates can include **EC2 instances**, **RDS DB instances**, and other resources.

---

## 2. AWS Compute Services

### 2.1 Amazon EC2 (Elastic Compute Cloud)
- A web service providing **secure, resizable compute capacity** in the cloud.
- Makes **web-scale cloud computing** easier for developers.
- Provides **complete control** of computing resources on Amazon's infrastructure.
- **Location** = AWS Regions + **AZs (Availability Zones)** — AZs are distinct, insulated from failures, low-latency connected.

#### EC2 Features
| Feature | Description |
|---|---|
| **AMIs** (Amazon Machine Images) | Preconfigured templates for instances |
| **Instance Types** | Hardware config: cores, memory, disk |
| **Key Pairs** | Secure login information |
| **Instance Store Volumes** | Temporary storage (deleted on stop/terminate) |
| **EBS Volumes** | Persistent storage using Elastic Block Store |
| **Security Groups** | Virtual firewall (protocols, ports, IP ranges) |
| **Elastic IP** | Static IP for dynamic cloud computing |
| **Tags** | Metadata for EC2 resources |

#### EC2 Advantages
- **Flexibility** — scale up/down rapidly
- **Cost Savings** — pay-as-you-go pricing
- **Reliability & Availability** — automatic failover, load balancing
- **Scalability** — handles growing traffic
- **Security** — VPC, security groups, IAM policies

#### EC2 Image Builder
- Fully managed service to **automate creation** of customized, secure server images.
- Offered at **no cost** (only pay for underlying AWS resources).

### 2.2 Auto Scaling
- **Automatically adjusts capacity** for predictable performance at lowest cost.
- Monitors applications and adjusts resources.
- Works with: **EC2 instances, Spot Fleets, ECS tasks, DynamoDB tables, Aurora Replicas**.
- **3 Steps:** Launch Configuration (recipe) → Auto Scaling Group (container) → Scaling Policies

### 2.3 Amazon Lightsail
- Easiest way to launch and manage a **virtual private server** (VPS) on AWS.
- **Applications:** Simple web apps, custom websites, small business apps, test environments.
- **Benefits:** Simplified UI, Speed, Scaling, Affordable.
- **Features:** Instances, Containers, Load Balancers, Managed Databases, Access to AWS services.

### 2.4 AWS App Runner
- Fully managed **container application service** — deploy containerized web apps and APIs **without prior container experience**.
- Auto **load balances**, **encrypts** traffic, scales to needs.
- **Applications:** Frontend/backend apps, microservices.

### 2.5 AWS Lambda
- **Serverless** computing service — no need to maintain servers.
- Infrastructure fully managed by AWS.
- **Applications:** Data processing, web/mobile backends, ML insights, event-driven apps.

#### Lambda Pros & Cons
| Pros | Cons |
|---|---|
| Entirely Managed Infrastructure | Not always cost-effective |
| Pay per Use | Cold Start Time (5-10 sec if idle >15 min) |
| Tight Integration with AWS (S3, DynamoDB, API Gateway) | Limited Number of Supported Runtimes |

### 2.6 AWS Outposts
- Delivers **AWS infrastructure to on-premises/edge locations** for hybrid experience.
- Available in **1U, 2U servers** to **42U racks**.
- **Applications:** Low latency compute, Data residency, Migration, Local data processing.

---

## 3. AWS Database Services

### 3.1 Amazon SimpleDB
- Distributed database developed in **Erlang** programming language.
- Works with **S3** (Simple Storage Service) and **EC2**.
- **NoSQL** database — also called **key-value data store**.
- Highly available, flexible, **non-relational** database.
- Best for **less complex databases** where users quickly look up data in NoSQL format.
- **Use Cases:** Web apps, Metadata storage, Dynamic/unstructured data, Low-traffic apps.

### 3.2 Amazon DynamoDB
- Fully managed, **serverless, key-value NoSQL** database for high-performance apps.
- Features: Built-in security, continuous backups, multi-Region replication, in-memory caching.
- **Applications:** Software apps, media metadata, retail experiences, gaming platforms.

### 3.3 Amazon RDS (Relational Database Service)
- Managed services for **relational databases** in cloud.
- **7 engines:** Aurora (MySQL), Aurora (PostgreSQL), MySQL, MariaDB, PostgreSQL, Oracle, SQL Server.

### 3.4 Amazon Redshift
- Fast, scalable **data warehouse** service.
- **10x faster** than other data warehouses using ML, parallel query execution, columnar storage.
- Can query **petabytes** in warehouse and **exabytes** in data lake (S3).

### 3.5 Amazon DocumentDB
- Fully managed **JSON document database** with MongoDB compatibility.

---

## 4. AWS Storage Services

### 4.1 Amazon S3 (Simple Storage Service)
- Store and retrieve **any amount of data**, at **any time**, from **anywhere** on web.
- **Buckets** = fundamental container for data storage.
- **Objects** = data + key (assigned name) + metadata. Each object up to **5 TB**.
- Each object gets a **unique version ID**.

#### S3 Key Operations
- **Create Buckets** — store unlimited data
- **Store data** — infinite objects, each up to 5 TB
- **Download data** — anytime
- **Permissions** — grant/deny access
- **Standard interfaces** — REST and SOAP

#### S3 APIs
| API | Description |
|---|---|
| **REST** (Representational State Transfer) | HTTP interface; uses standard HTTP headers and status codes |
| **SOAP** (Simple Object Access Protocol) | SOAP 1.1 interface; **deprecated over HTTP** but available over HTTPS |

#### S3 Data Protection
- **Data Encryption** — client-side (at rest) and server-side (in motion)
- **Versioning** — preserve, recover, restore early versions of objects
- **Cross-region Replication** — automatic copying to different AWS regions
- **Transfer Acceleration** — fast file transfers over long distances

### 4.2 Amazon S3 Glacier
- **Extremely low-cost** storage for **data backup and archival**.
- Retain data for months, years, or decades.
- **Durability:** 99.999999999% (11 nines).
- **Vault Lock** for compliance storage.

#### Glacier Retrieval Speeds
| Option | Time |
|---|---|
| **Expedited** | 1-5 minutes |
| **Standard** | 3-5 hours |
| **Bulk** | 5-12 hours |

#### Glacier Storage Classes
| Class | Description |
|---|---|
| **GLACIER** (S3 Glacier Flexible Retrieval) | Long-term backups; retrieval 1 min to 12 hours |
| **GLACIER_IR** (S3 Glacier Instant Retrieval) | Archive accessed once/quarter; instant retrieval in milliseconds |
| **DEEP_ARCHIVE** (S3 Glacier Deep Archive) | Accessed once-twice/year; restored within 12 hours |

### 4.3 Amazon EBS (Elastic Block Store)
- **Block storage** for persistent data with EC2.
- **99.999% availability**; replicates within AZ.
- Different from EC2 Instance Store (which is temporary).
- One EBS volume = **one instance at a time**.
- Can take **snapshots** (backup) → create new volumes from them.
- Stores: databases (relational/NoSQL), enterprise apps, big data, file systems.

### 4.4 Amazon EFS (Elastic File System)
- **Automatically grows/shrinks** as files are added/removed.
- No provisioning or management needed.
- **99.999999999% durability**, up to **99.99% availability**.
- Pay only for storage used; costs reduced up to **92%** for infrequent files.

### 4.5 Other Storage Services
| Service | Purpose |
|---|---|
| **Amazon File Cache** | High-speed temporary cache for file data |
| **AWS Backup** | Fully managed backup service, immutable backups |
| **AWS DRS** (Elastic Disaster Recovery) | Fast recovery with minimal downtime |
| **AWS Storage Gateway** | Hybrid cloud storage, on-premises access to cloud storage |

---

## 5. AWS Networking

### 5.1 Amazon VPC (Virtual Private Cloud)
- **On-demand configurable pool** of shared computing resources within a public cloud, providing **isolation**.
- Like a **VPN** — secure environment on public infrastructure.
- Best of both worlds: **private cloud security** + **public cloud cost savings**.

#### VPC Advantages
- **Scalability** — add computing resources on demand
- **Easy hybrid cloud** — connect via VPN
- **Better performance** — cloud-hosted apps perform better
- **Better security** — cloud providers update infrastructure regularly

### 5.2 Amazon API Gateway
- Fully managed service to **create, publish, maintain, monitor, secure APIs** at any scale.
- APIs = "front door" for apps to access data/business logic.
- Supports **RESTful APIs** and **WebSocket APIs**.
- Handles traffic management, CORS, authorization, throttling, monitoring.
- **No minimum fees** or startup costs.

### 5.3 Amazon CloudFront
- **CDN (Content Delivery Network)** service for high performance and security.
- **Applications:** Fast websites, dynamic content, live/on-demand video, patches/updates.

### 5.4 Amazon Route 53
- Highly available **DNS (Domain Name System)** service.
- Manages **internal domain names** using **Private DNS** feature.
- Works within **VPCs** — doesn't expose DNS data to public internet.

### 5.5 AWS App Mesh
- Makes running services easier with **consistent visibility and network traffic controls**.
- Removes manual steps for monitoring and traffic routing.

---

## 6. AWS Security

### 6.1 AWS IAM (Identity and Access Management)
- Controls **who** can access AWS services and **what permissions** they have.
- **"Who"** = identity (user, group, role) → **Authentication** (proving who you are)
- **"Permissions"** = policies attached to identity → **Authorization** (what you can do)
- IAM identity = **passport** (authentication); IAM policy = **boarding pass** (authorization)

#### IAM Workflow (6 Elements)
1. **Principal** — entity that can perform actions (user, role, application)
2. **Authentication** — confirming identity with credentials
3. **Request** — principal specifies action and resource
4. **Authorization** — IAM checks if allowed by matching policy
5. **Actions** — view, create, edit, or delete a resource
6. **Resources** — AWS resources in your account

#### IAM Key Concepts
| Concept | Description |
|---|---|
| **Root User** | First identity with complete access; created with email + password |
| **IAM Users** | Entities representing persons/services; can sign in to Console, use API/CLI |
| **IAM Groups** | Collections of users managed as a unit |
| **IAM Roles** | Identities with specific permissions |
| **IAM Policies** | Allow or deny access to specific resources |

#### IAM Security Features
- **Strong Password Policy** — min length, uppercase, lowercase, number, special character
- **MFA (Multi-Factor Authentication)** — supplements username/password with one-time code
  - **Virtual MFA** (software app)
  - **Hardware MFA** (physical device)

### 6.2 AWS Physical & Environmental Security
- **Fire Detection** — smoke sensors, wet-pipe/gaseous sprinkler systems
- **Power** — fully redundant, **UPS (Uninterruptible Power Supply)** + generators
- **Climate Control** — maintains constant temperature for servers
- **Storage Decommissioning** — follows **NIST 800-88** guidelines

### 6.3 AWS API Security
- Multiple access control mechanisms:
  - **IAM Permissions** — control API access
  - **Custom Authorizers** — Lambda functions for access control (JWT, OAuth)
  - **Amazon Cognito User Pools** — authentication for API access
  - **Client-Side SSL Certificates** — backend authentication
  - **Usage Plans** — track API usage, set request rates/quotas

### 6.4 AWS Certificate Manager (ACM)
- Provision, manage, deploy **SSL/TLS certificates**.
- **Applications:** Protect websites, internal resources, improve uptime.

---

## 7. AWS Management Tools

### 7.1 Amazon SQS (Simple Queue Service)
- Fully managed **message queuing** service.
- Decouple and scale **microservices, distributed systems, serverless apps**.

### 7.2 AWS CloudWatch
- **Monitoring and observability** service for resources and applications.
- Provides data and insights to **monitor, respond, optimize** AWS resources.

### 7.3 AWS CloudFormation
- **Infrastructure as Code (IaC)** — model, provision, manage resources using text files (templates).
- Available at **no additional charge** (pay only for AWS resources used).
- **Advantages:** Model it all, Automate and deploy, It's just code (version control).

### 7.4 AWS CloudTrail
- Enables **governance, compliance, auditing** of your AWS account.
- Records actions as **events** (Console, CLI, SDKs, APIs).
- **Auto-enabled** on account creation.
- **Benefits:** Simplified compliance, Security analysis, Visibility, Security automation.

### 7.5 AWS Chatbot
- Interactive agent for **monitoring and operating AWS resources** in Slack/Teams.
- **Benefits:** Easy to use, Cost-effective, Flexible, Reliable, Secure.

---

## 8. Amazon EKS (Elastic Kubernetes Service)

### What is Kubernetes (K8s)?
- Open source system for **automating deployment, scaling, management** of containerized applications.

#### Kubernetes Basic Objects
| Object | Description |
|---|---|
| **Pod** | Group of one or more containers |
| **Service** | Defines logical set of pods + access policy |
| **Volume** | Persists data (containers are ephemeral) |
| **Namespace** | Segment of cluster for specific purpose/team |

#### Kubernetes Features
- **Service discovery & load balancing** — DNS, IP-based, auto load balance
- **Storage orchestration** — auto mount storage systems
- **Automated rollouts & rollbacks** — desired state management
- **Automatic bin packing** — efficient node usage
- **Self-healing** — restarts/replaces failed containers
- **Secret management** — store passwords, OAuth tokens, SSH keys

### Amazon EKS
- Managed service to **run Kubernetes on AWS** without maintaining control plane.
- Automates **deployment, scaling, maintenance** of containerized apps.

#### EKS Integrations
| Service | Purpose |
|---|---|
| **ECR** (Elastic Container Registry) | Container images |
| **Elastic Load Balancer** | Traffic distribution |
| **IAM** | Authentication & authorization |
| **VPC** | Resource isolation |

#### EKS Workflow (4 Steps)
1. **Provision** EKS cluster (Console, CLI, or SDK)
2. **Deploy** worker nodes (predefined template)
3. **Configure** kubectl to communicate with cluster
4. **Deploy** application on cluster

---

## 📋 Abbreviation Table

| Short Form | Full Form |
|---|---|
| ACM | AWS Certificate Manager |
| AMI | Amazon Machine Image |
| API | Application Programming Interface |
| AZ | Availability Zone |
| CCBD | Cloud Computing & Basics of DevOps |
| CDN | Content Delivery Network |
| CLI | Command Line Interface |
| CORS | Cross-Origin Resource Sharing |
| DNS | Domain Name System |
| DRS | Elastic Disaster Recovery |
| DynamoDB | Amazon DynamoDB (NoSQL database) |
| EBS | Elastic Block Store |
| EC2 | Elastic Compute Cloud |
| ECR | Elastic Container Registry |
| EFS | Elastic File System |
| EKS | Elastic Kubernetes Service |
| IAM | Identity and Access Management |
| IaC | Infrastructure as Code |
| JWT | JSON Web Token |
| K8s | Kubernetes |
| MFA | Multi-Factor Authentication |
| NIST | National Institute of Standards and Technology |
| RDS | Relational Database Service |
| REST | Representational State Transfer |
| S3 | Simple Storage Service |
| SDK | Software Development Kit |
| SOAP | Simple Object Access Protocol |
| SQS | Simple Queue Service |
| SSL | Secure Sockets Layer |
| TLS | Transport Layer Security |
| UPS | Uninterruptible Power Supply |
| VPC | Virtual Private Cloud |
| VPN | Virtual Private Network |
| VPS | Virtual Private Server |
| WORM | Write Once Read Many |

---

---

# 📝 MCQ Bank — Unit 4: Amazon Web Services (200 Questions)

---

## Section A: AWS Basics & Compute (Q1–Q50)

**Q1.** AWS CloudFormation uses ______ to describe resources.
- A) Images
- B) Templates (text files)
- C) Audio files
- D) Videos

**Correct Answer: B**

---

**Q2.** A stack in AWS CloudFormation is:
- A) A single server
- B) A collection of AWS resources deployed together
- C) A physical rack
- D) A storage device

**Correct Answer: B**

---

**Q3.** EC2 stands for:
- A) Elastic Cloud Computing
- B) Elastic Compute Cloud
- C) Electronic Cloud Computer
- D) Enterprise Compute Center

**Correct Answer: B**

---

**Q4.** EC2 provides:
- A) Secure compute capacity
- B) Resizable compute capacity
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q5.** AZ stands for:
- A) Amazon Zone
- B) Availability Zone
- C) Access Zone
- D) Application Zone

**Correct Answer: B**

---

**Q6.** AZs are designed to be:
- A) Connected with high latency
- B) Insulated from failures in other AZs
- C) On the same physical location
- D) Not connected to each other

**Correct Answer: B**

---

**Q7.** AMI stands for:
- A) Amazon Machine Image
- B) Amazon Management Interface
- C) Application Machine Instance
- D) Amazon Module Integration

**Correct Answer: A**

---

**Q8.** Which EC2 feature provides secure login information?
- A) Tags
- B) Security Groups
- C) Key Pairs
- D) Elastic IP

**Correct Answer: C**

---

**Q9.** Instance Store Volumes are:
- A) Persistent storage
- B) Temporary storage deleted on stop/terminate
- C) Cloud storage
- D) Network storage

**Correct Answer: B**

---

**Q10.** EBS volumes provide:
- A) Temporary storage
- B) Persistent storage
- C) No storage
- D) Only cache storage

**Correct Answer: B**

---

**Q11.** Security Groups in EC2 act as:
- A) Physical firewall
- B) Virtual firewall
- C) Antivirus
- D) Password manager

**Correct Answer: B**

---

**Q12.** Which is NOT an advantage of EC2?
- A) Flexibility
- B) Cost Savings
- C) Guaranteed free forever
- D) Scalability

**Correct Answer: C**

---

**Q13.** EC2 uses ______ pricing model.
- A) Fixed monthly
- B) Pay-as-you-go
- C) One-time purchase
- D) Free for all

**Correct Answer: B**

---

**Q14.** EC2 Image Builder is offered at:
- A) High cost
- B) No cost (only pay for underlying resources)
- C) Monthly subscription
- D) Annual fee

**Correct Answer: B**

---

**Q15.** AWS Auto Scaling:
- A) Manually adjusts capacity
- B) Automatically adjusts capacity
- C) Never changes capacity
- D) Only increases capacity

**Correct Answer: B**

---

**Q16.** Auto Scaling works with:
- A) EC2 instances
- B) DynamoDB tables
- C) Aurora Replicas
- D) All of the above

**Correct Answer: D**

---

**Q17.** The first step of Auto Scaling is:
- A) Scaling Policy
- B) Auto Scaling Group
- C) Launch Configuration
- D) Monitoring

**Correct Answer: C**

---

**Q18.** Amazon Lightsail is the easiest way to launch:
- A) A physical server
- B) A VPS (Virtual Private Server)
- C) A mainframe
- D) A supercomputer

**Correct Answer: B**

---

**Q19.** Which is NOT a benefit of Amazon Lightsail?
- A) Simplified UI
- B) Speed
- C) Complex setup
- D) Affordable

**Correct Answer: C**

---

**Q20.** AWS App Runner is for deploying:
- A) Physical servers
- B) Containerized web apps and APIs
- C) Desktop applications
- D) Mobile games only

**Correct Answer: B**

---

**Q21.** AWS Lambda is a ______ computing service.
- A) Server-based
- B) Serverless
- C) Physical
- D) Desktop

**Correct Answer: B**

---

**Q22.** "Serverless" means:
- A) No computers exist
- B) You don't need to maintain servers
- C) No internet required
- D) No electricity needed

**Correct Answer: B**

---

**Q23.** Which is a Pro of AWS Lambda?
- A) Cold Start Time
- B) Limited Runtimes
- C) Pay per Use
- D) High cost always

**Correct Answer: C**

---

**Q24.** Which is a Con of AWS Lambda?
- A) Managed Infrastructure
- B) Cold Start Time
- C) Pay per Use
- D) AWS Integration

**Correct Answer: B**

---

**Q25.** Lambda Cold Start latency can last:
- A) 1-2 seconds
- B) 5-10 seconds
- C) 1-2 minutes
- D) No latency

**Correct Answer: B**

---

**Q26.** Cold Start happens when function was not used for:
- A) 5 minutes
- B) 10 minutes
- C) Over 15 minutes
- D) 1 hour

**Correct Answer: C**

---

**Q27.** Lambda integrates with:
- A) S3
- B) DynamoDB
- C) API Gateway
- D) All of the above

**Correct Answer: D**

---

**Q28.** AWS Outposts delivers AWS infrastructure to:
- A) Cloud only
- B) On-premises or edge locations
- C) Space stations
- D) Underwater data centers

**Correct Answer: B**

---

**Q29.** AWS Outposts is available in form factors including:
- A) 1U and 2U servers
- B) 42U racks
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q30.** Which is NOT an application of AWS Outposts?
- A) Low latency compute
- B) Data residency
- C) Social media posting
- D) Local data processing

**Correct Answer: C**

---

**Q31.** Auto Scaling Group acts as:
- A) A recipe for servers
- B) A container for EC2 instances
- C) A database
- D) A network cable

**Correct Answer: B**

---

**Q32.** Launch Configuration defines:
- A) The type of EC2 instance
- B) Operating System
- C) Software Configuration
- D) All of the above

**Correct Answer: D**

---

**Q33.** Elastic IP provides:
- A) Dynamic IP only
- B) Static IP for dynamic cloud computing
- C) No IP address
- D) Physical address

**Correct Answer: B**

---

**Q34.** Tags in EC2 are used for:
- A) Physical labeling
- B) Metadata for EC2 resources
- C) Pricing
- D) Encryption

**Correct Answer: B**

---

**Q35.** App Runner deploys apps without prior:
- A) Programming knowledge
- B) Infrastructure or container experience
- C) Internet connection
- D) AWS account

**Correct Answer: B**

---

**Q36.** App Runner VPC endpoint allows connection:
- A) Only through internet
- B) Without letting traffic flow through internet
- C) Through physical cables only
- D) Via satellite

**Correct Answer: B**

---

**Q37.** Lambda applications include:
- A) Process data at scale
- B) ML insights
- C) Event-driven applications
- D) All of the above

**Correct Answer: D**

---

**Q38.** EC2 provides ______ control of computing resources.
- A) No
- B) Limited
- C) Complete
- D) Partial

**Correct Answer: C**

---

**Q39.** Each AWS Region can consist of:
- A) Only one AZ
- B) One or more AZs
- C) No AZs
- D) Exactly two AZs

**Correct Answer: B**

---

**Q40.** Lightsail features include:
- A) Instances and Containers
- B) Load balancers and Managed databases
- C) Access to AWS services
- D) All of the above

**Correct Answer: D**

---

**Q41.** Which service is fully managed and serverless?
- A) EC2
- B) Lightsail
- C) Lambda
- D) Outposts

**Correct Answer: C**

---

**Q42.** AWS Lambda Pros include:
- A) Entirely managed infrastructure
- B) Pay per Use
- C) Tight integration with AWS
- D) All of the above

**Correct Answer: D**

---

**Q43.** Lambda Cons include:
- A) Cold Start Time
- B) Not always cost-effective
- C) Limited supported runtimes
- D) All of the above

**Correct Answer: D**

---

**Q44.** EC2 reliability features include:
- A) Automatic failover
- B) Load balancing
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q45.** VPS stands for:
- A) Virtual Private Server
- B) Virtual Public Server
- C) Virtual Protocol Service
- D) Visual Private System

**Correct Answer: A**

---

**Q46.** Outposts supports workloads requiring:
- A) Low latency access
- B) Local data processing
- C) Data residency
- D) All of the above

**Correct Answer: D**

---

**Q47.** AWS Auto Scaling maintains:
- A) Unpredictable performance at high cost
- B) Steady, predictable performance at lowest cost
- C) Only high cost
- D) No performance monitoring

**Correct Answer: B**

---

**Q48.** EC2 Image Builder removes:
- A) Any manual steps for updating an image
- B) All data
- C) All users
- D) All security

**Correct Answer: A**

---

**Q49.** How many advantages of EC2 are discussed?
- A) 4
- B) 5
- C) 6
- D) 7

**Correct Answer: C**

---

**Q50.** EC2 Security features include:
- A) VPC networking
- B) Security groups
- C) IAM policies
- D) All of the above

**Correct Answer: D**

---

## Section B: AWS Storage (Q51–Q90)

**Q51.** S3 stands for:
- A) Simple Storage Service
- B) Secure Storage System
- C) Server Storage Solution
- D) Standard Storage Service

**Correct Answer: A**

---

**Q52.** In S3, the fundamental container for data storage is:
- A) Object
- B) Bucket
- C) Volume
- D) Drive

**Correct Answer: B**

---

**Q53.** Each S3 object can contain up to:
- A) 1 TB
- B) 5 TB
- C) 10 TB
- D) Unlimited

**Correct Answer: B**

---

**Q54.** S3 supports which interfaces?
- A) REST
- B) SOAP
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q55.** REST stands for:
- A) Representational State Transfer
- B) Remote Execution Service Tool
- C) Resource Exchange System Transfer
- D) Real-time Execution Standard

**Correct Answer: A**

---

**Q56.** SOAP stands for:
- A) Simple Object Access Protocol
- B) Secure Object Application Protocol
- C) System Oriented Access Program
- D) Standard Object Archive Protocol

**Correct Answer: A**

---

**Q57.** SOAP support over HTTP is:
- A) Fully supported
- B) Deprecated but available over HTTPS
- C) Never existed
- D) Only for mobile apps

**Correct Answer: B**

---

**Q58.** S3 Data Protection includes:
- A) Encryption
- B) Versioning
- C) Cross-region Replication
- D) All of the above

**Correct Answer: D**

---

**Q59.** Client-side encryption protects data:
- A) In motion
- B) At rest
- C) In both states
- D) Not at all

**Correct Answer: B**

---

**Q60.** Server-side encryption protects data:
- A) At rest
- B) In motion
- C) Never
- D) Only in cache

**Correct Answer: B**

---

**Q61.** S3 Glacier is used for:
- A) Real-time processing
- B) Data backup and archival
- C) Gaming
- D) Social media

**Correct Answer: B**

---

**Q62.** S3 Glacier durability is:
- A) 99.9%
- B) 99.99%
- C) 99.999999999% (11 nines)
- D) 100%

**Correct Answer: C**

---

**Q63.** Glacier Expedited retrieval takes:
- A) 1-5 minutes
- B) 3-5 hours
- C) 5-12 hours
- D) 1-2 days

**Correct Answer: A**

---

**Q64.** Glacier Standard retrieval takes:
- A) 1-5 minutes
- B) 3-5 hours
- C) 5-12 hours
- D) Instant

**Correct Answer: B**

---

**Q65.** Glacier Bulk retrieval takes:
- A) 1-5 minutes
- B) 3-5 hours
- C) 5-12 hours
- D) 24 hours

**Correct Answer: C**

---

**Q66.** How many Glacier retrieval speed options are there?
- A) 1
- B) 2
- C) 3
- D) 4

**Correct Answer: C**

---

**Q67.** How many S3 Glacier storage classes are there?
- A) 1
- B) 2
- C) 3
- D) 4

**Correct Answer: C**

---

**Q68.** DEEP_ARCHIVE is accessed:
- A) Every day
- B) Every hour
- C) Once or twice a year
- D) Every minute

**Correct Answer: C**

---

**Q69.** GLACIER_IR provides retrieval in:
- A) Hours
- B) Days
- C) Milliseconds (instant)
- D) Weeks

**Correct Answer: C**

---

**Q70.** Vault Lock is used for:
- A) Gaming
- B) Compliance storage
- C) Social media
- D) Email

**Correct Answer: B**

---

**Q71.** EBS stands for:
- A) Elastic Block Store
- B) Extended Block Service
- C) Enterprise Backup Storage
- D) Elastic Backup System

**Correct Answer: A**

---

**Q72.** EBS availability is:
- A) 99.9%
- B) 99.99%
- C) 99.999%
- D) 100%

**Correct Answer: C**

---

**Q73.** One EBS volume can be attached to:
- A) Multiple instances
- B) Only one instance at a time
- C) No instance
- D) Unlimited instances

**Correct Answer: B**

---

**Q74.** A snapshot in EBS is equivalent to:
- A) A virus
- B) A backup
- C) A deletion
- D) A crash

**Correct Answer: B**

---

**Q75.** EBS is different from Instance Store because:
- A) EBS is persistent, Instance Store is temporary
- B) Both are temporary
- C) Both are persistent
- D) Instance Store is persistent

**Correct Answer: A**

---

**Q76.** EFS stands for:
- A) Elastic File System
- B) Extended File Storage
- C) Enterprise File Service
- D) Elastic Full Storage

**Correct Answer: A**

---

**Q77.** EFS automatically:
- A) Grows and shrinks as files are added/removed
- B) Stays fixed size
- C) Only grows
- D) Only shrinks

**Correct Answer: A**

---

**Q78.** EFS can reduce costs up to:
- A) 50%
- B) 75%
- C) 92%
- D) 100%

**Correct Answer: C**

---

**Q79.** DRS stands for:
- A) Data Recovery Service
- B) Elastic Disaster Recovery
- C) Digital Restore System
- D) Dynamic Recovery Storage

**Correct Answer: B**

---

**Q80.** AWS Storage Gateway provides:
- A) On-premises access to cloud storage
- B) Only cloud access
- C) Only physical storage
- D) No storage

**Correct Answer: A**

---

**Q81.** WORM stands for:
- A) Write Often Read Many
- B) Write Once Read Many
- C) Web Only Read Module
- D) Wide Open Resource Manager

**Correct Answer: B**

---

**Q82.** Transfer Acceleration enables:
- A) Slow file transfers
- B) Fast file transfers over long distances
- C) No transfers
- D) Only local transfers

**Correct Answer: B**

---

**Q83.** Cross-region Replication provides:
- A) Manual copying to same region
- B) Automatic copying to different AWS regions
- C) No copying
- D) Deletion of objects

**Correct Answer: B**

---

**Q84.** An S3 object consists of:
- A) Data only
- B) Data, key, and metadata
- C) Key only
- D) Metadata only

**Correct Answer: B**

---

**Q85.** Amazon SimpleDB is a ______ database.
- A) Relational
- B) NoSQL
- C) Graph
- D) Time-series

**Correct Answer: B**

---

**Q86.** SimpleDB was developed in:
- A) Java
- B) Python
- C) Erlang
- D) Go

**Correct Answer: C**

---

**Q87.** SimpleDB is also known as:
- A) Graph data store
- B) Key-value data store
- C) Column data store
- D) Document data store

**Correct Answer: B**

---

**Q88.** Amazon DynamoDB is:
- A) Relational database
- B) Serverless key-value NoSQL database
- C) Graph database
- D) Physical database

**Correct Answer: B**

---

**Q89.** Amazon RDS supports how many database engines?
- A) 3
- B) 5
- C) 7
- D) 10

**Correct Answer: C**

---

**Q90.** Redshift delivers ______ faster performance than other data warehouses.
- A) 2x
- B) 5x
- C) 10x
- D) 100x

**Correct Answer: C**

---

## Section C: AWS Networking & CDN (Q91–Q110)

**Q91.** VPC stands for:
- A) Virtual Public Cloud
- B) Virtual Private Cloud
- C) Virtual Protected Computer
- D) Verified Private Cloud

**Correct Answer: B**

---

**Q92.** VPC is like a:
- A) Physical server
- B) VPN — secure on public infrastructure
- C) Cable
- D) Monitor

**Correct Answer: B**

---

**Q93.** Which is NOT a VPC advantage?
- A) Scalability
- B) Better performance
- C) More expensive than physical servers
- D) Better security

**Correct Answer: C**

---

**Q94.** CDN stands for:
- A) Cloud Data Network
- B) Content Delivery Network
- C) Computer Distributed Network
- D) Central Data Node

**Correct Answer: B**

---

**Q95.** Amazon CloudFront is a ______ service.
- A) Database
- B) CDN
- C) Compute
- D) Storage

**Correct Answer: B**

---

**Q96.** Route 53 is a ______ service.
- A) Storage
- B) Compute
- C) DNS
- D) Database

**Correct Answer: C**

---

**Q97.** Route 53 Private DNS works within:
- A) Public internet
- B) VPCs
- C) Physical servers
- D) USB drives

**Correct Answer: B**

---

**Q98.** API Gateway supports:
- A) RESTful APIs
- B) WebSocket APIs
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q99.** API Gateway has:
- A) High minimum fees
- B) No minimum fees or startup costs
- C) Fixed monthly fee
- D) Annual subscription

**Correct Answer: B**

---

**Q100.** APIs act as the ______ for applications.
- A) Back door
- B) Front door
- C) Side door
- D) No door

**Correct Answer: B**

---

**Q101.** CORS stands for:
- A) Cross-Origin Resource Sharing
- B) Cloud Origin Resource System
- C) Central Operating Resource Service
- D) Content Origin Retrieval System

**Correct Answer: A**

---

**Q102.** Amazon CloudFront applications include:
- A) Fast secure websites
- B) Live and on-demand video
- C) Dynamic content delivery
- D) All of the above

**Correct Answer: D**

---

**Q103.** VPC gives best of both worlds:
- A) Private cloud security + Public cloud cost savings
- B) High cost + Low security
- C) Physical hardware + More cables
- D) No benefit

**Correct Answer: A**

---

**Q104.** DNS stands for:
- A) Domain Name System
- B) Data Network Service
- C) Digital Name Standard
- D) Direct Network System

**Correct Answer: A**

---

**Q105.** App Mesh provides:
- A) Consistent visibility and network traffic controls
- B) Only storage
- C) Only compute
- D) Only databases

**Correct Answer: A**

---

**Q106.** SQS stands for:
- A) Simple Queue Service
- B) Secure Query System
- C) Standard Queue Storage
- D) Simple Query Service

**Correct Answer: A**

---

**Q107.** SQS is used to decouple:
- A) Microservices
- B) Distributed systems
- C) Serverless applications
- D) All of the above

**Correct Answer: D**

---

**Q108.** AWS CloudWatch is for:
- A) Monitoring and observability
- B) Storage
- C) Database
- D) Networking only

**Correct Answer: A**

---

**Q109.** CloudFormation treats infrastructure as:
- A) Hardware
- B) Code (IaC)
- C) Cables
- D) Buildings

**Correct Answer: B**

---

**Q110.** CloudFormation is available at:
- A) High cost
- B) No additional charge
- C) Monthly fee
- D) Annual fee

**Correct Answer: B**

---

## Section D: AWS Security & IAM (Q111–Q155)

**Q111.** IAM stands for:
- A) Internet Access Manager
- B) Identity and Access Management
- C) Internal Application Module
- D) Information and Asset Management

**Correct Answer: B**

---

**Q112.** IAM controls:
- A) Who can access AWS services
- B) What permissions they have
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q113.** Authentication in IAM is like:
- A) A boarding pass
- B) A passport
- C) A ticket
- D) A key card

**Correct Answer: B**

---

**Q114.** Authorization in IAM is like:
- A) A passport
- B) A boarding pass
- C) A visa
- D) A photo ID

**Correct Answer: B**

---

**Q115.** How many elements are in the IAM workflow?
- A) 4
- B) 5
- C) 6
- D) 7

**Correct Answer: C**

---

**Q116.** The first element in IAM workflow is:
- A) Authentication
- B) Principal
- C) Request
- D) Authorization

**Correct Answer: B**

---

**Q117.** A Principal can be:
- A) A user
- B) A role
- C) An application
- D) All of the above

**Correct Answer: D**

---

**Q118.** By default in IAM, all resources are:
- A) Allowed
- B) Denied
- C) Public
- D) Encrypted

**Correct Answer: B**

---

**Q119.** The Root User has:
- A) Limited access
- B) No access
- C) Complete access to all AWS services
- D) Only read access

**Correct Answer: C**

---

**Q120.** Root User is accessed by:
- A) Phone number
- B) Email and password used to create account
- C) Fingerprint
- D) Social media login

**Correct Answer: B**

---

**Q121.** IAM Groups are:
- A) Individual users
- B) Collections of IAM users managed as a unit
- C) Physical groups of servers
- D) Network groups

**Correct Answer: B**

---

**Q122.** MFA stands for:
- A) Multi-Factor Authentication
- B) Multiple File Access
- C) Main Function Application
- D) Managed Feature Authorization

**Correct Answer: A**

---

**Q123.** How many types of MFA are there?
- A) 1
- B) 2
- C) 3
- D) 4

**Correct Answer: B**

---

**Q124.** The two types of MFA are:
- A) Virtual MFA and Hardware MFA
- B) Software MFA and Cloud MFA
- C) Physical MFA and Digital MFA
- D) Internal MFA and External MFA

**Correct Answer: A**

---

**Q125.** MFA supplements:
- A) Username and password with a one-time code
- B) Only email
- C) Only phone number
- D) Only fingerprint

**Correct Answer: A**

---

**Q126.** IAM password policy can require:
- A) Uppercase letters
- B) Lowercase letters
- C) Numbers and special characters
- D) All of the above

**Correct Answer: D**

---

**Q127.** Benefits of IAM Groups include:
- A) Easier to assign same permissions to multiple users
- B) Simpler to reassign permissions on role change
- C) One change updates permissions for multiple users
- D) All of the above

**Correct Answer: D**

---

**Q128.** AWS Physical Security includes:
- A) Fire Detection
- B) Power management
- C) Climate Control
- D) All of the above

**Correct Answer: D**

---

**Q129.** UPS stands for:
- A) Uninterruptible Power Supply
- B) Universal Power System
- C) United Protocol Service
- D) Unmanaged Power Storage

**Correct Answer: A**

---

**Q130.** Storage decommissioning follows ______ guidelines.
- A) ISO 9001
- B) NIST 800-88
- C) IEEE 802.11
- D) RFC 2616

**Correct Answer: B**

---

**Q131.** AWS API Security mechanisms include:
- A) IAM Permissions
- B) Custom Authorizers
- C) Cognito User Pools
- D) All of the above

**Correct Answer: D**

---

**Q132.** Custom Authorizers in API Gateway are:
- A) Physical devices
- B) Lambda functions
- C) Database queries
- D) Network protocols

**Correct Answer: B**

---

**Q133.** SSL stands for:
- A) Secure Sockets Layer
- B) Standard Security Level
- C) System Service Layer
- D) Server Side Login

**Correct Answer: A**

---

**Q134.** TLS stands for:
- A) Transfer Layer Service
- B) Transport Layer Security
- C) Technical Level Standard
- D) Token Login System

**Correct Answer: B**

---

**Q135.** ACM is used for managing:
- A) SSL/TLS certificates
- B) Physical keys
- C) Password lists
- D) Server hardware

**Correct Answer: A**

---

**Q136.** JWT stands for:
- A) Java Web Token
- B) JSON Web Token
- C) JavaScript Web Transfer
- D) Joint Web Technology

**Correct Answer: B**

---

**Q137.** IAM Users can use ______ to interact with AWS.
- A) Management Console
- B) API or CLI
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q138.** An IAM User can have up to ______ access keys.
- A) 1
- B) 2
- C) 5
- D) Unlimited

**Correct Answer: B**

---

**Q139.** Actions in IAM include:
- A) View
- B) Create
- C) Edit and Delete
- D) All of the above

**Correct Answer: D**

---

**Q140.** Data center power systems are designed to be:
- A) Partially redundant
- B) Fully redundant
- C) Non-redundant
- D) Semi-redundant

**Correct Answer: B**

---

**Q141.** Climate control prevents:
- A) Server overheating
- B) Data corruption only
- C) Network issues only
- D) Physical theft

**Correct Answer: A**

---

**Q142.** Client-Side SSL Certificates verify requests from:
- A) Users directly
- B) API Gateway to backend
- C) Social media
- D) Email

**Correct Answer: B**

---

**Q143.** Usage Plans allow tracking:
- A) API usage by clients
- B) Storage usage
- C) Network cables
- D) Physical servers

**Correct Answer: A**

---

**Q144.** NIST stands for:
- A) National Institute of Standards and Technology
- B) Network Information Security Tool
- C) New Internet Standard Technology
- D) National Internet Service Team

**Correct Answer: A**

---

**Q145.** OAuth is used for:
- A) Token-based authentication
- B) Physical access
- C) Cable management
- D) Power supply

**Correct Answer: A**

---

**Q146.** IAM Policies either ______ or ______ access.
- A) Allow or Deny
- B) Create or Delete
- C) Send or Receive
- D) Upload or Download

**Correct Answer: A**

---

**Q147.** Fire detection uses:
- A) Smoke detection sensors
- B) Temperature sensors only
- C) Sound sensors
- D) Light sensors

**Correct Answer: A**

---

**Q148.** Data centers use ______ for backup power.
- A) Solar panels
- B) Generators
- C) Wind turbines
- D) Batteries only

**Correct Answer: B**

---

**Q149.** Cognito User Pools are used for:
- A) Storage management
- B) Authentication for API access
- C) Physical security
- D) Cable management

**Correct Answer: B**

---

**Q150.** Which is NOT an IAM identity?
- A) User
- B) Group
- C) Role
- D) Server

**Correct Answer: D**

---

**Q151.** Role-based access control regulates access based on:
- A) Physical location
- B) Roles of individual users
- C) Server type
- D) Cable type

**Correct Answer: B**

---

**Q152.** Single sign-on is a system used in:
- A) IAM only
- B) Identity and access management
- C) Physical security
- D) Storage management

**Correct Answer: B**

---

**Q153.** IAM can be deployed:
- A) On premises
- B) Cloud-based subscription
- C) Hybrid cloud
- D) All of the above

**Correct Answer: D**

---

**Q154.** Sprinkler systems in data centers include:
- A) Wet-pipe systems
- B) Double interlocked pre-action
- C) Gaseous systems
- D) All of the above

**Correct Answer: D**

---

**Q155.** ACM stands for:
- A) AWS Certificate Manager
- B) Amazon Cloud Module
- C) Access Control Manager
- D) Application Configuration Module

**Correct Answer: A**

---

## Section E: AWS Management, EKS & Kubernetes (Q156–Q200)

**Q156.** CloudTrail records actions as:
- A) Files
- B) Events
- C) Images
- D) Videos

**Correct Answer: B**

---

**Q157.** CloudTrail is ______ on account creation.
- A) Disabled
- B) Auto-enabled
- C) Deleted
- D) Hidden

**Correct Answer: B**

---

**Q158.** Which is NOT a benefit of CloudTrail?
- A) Simplified compliance
- B) Security analysis
- C) Increased cost
- D) Visibility into activity

**Correct Answer: C**

---

**Q159.** CloudFormation advantages include:
- A) Model it all
- B) Automate and deploy
- C) It's just code
- D) All of the above

**Correct Answer: D**

---

**Q160.** IaC stands for:
- A) Infrastructure as Code
- B) Internet as Cloud
- C) Information and Cloud
- D) Integrated and Connected

**Correct Answer: A**

---

**Q161.** AWS Chatbot works with:
- A) Slack
- B) Microsoft Teams
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q162.** Which is NOT a benefit of AWS Chatbot?
- A) Easy to use
- B) High cost
- C) Flexible
- D) Secure

**Correct Answer: B**

---

**Q163.** Kubernetes is also known as:
- A) K5s
- B) K8s
- C) K10s
- D) K3s

**Correct Answer: B**

---

**Q164.** Kubernetes is an ______ system.
- A) Closed source
- B) Open source
- C) Proprietary
- D) Licensed

**Correct Answer: B**

---

**Q165.** How many basic Kubernetes objects are discussed?
- A) 2
- B) 3
- C) 4
- D) 5

**Correct Answer: C**

---

**Q166.** A Pod in Kubernetes is:
- A) A storage device
- B) A group of one or more containers
- C) A network cable
- D) A physical server

**Correct Answer: B**

---

**Q167.** A Volume in Kubernetes lets us:
- A) Delete data
- B) Persist data
- C) Encrypt data
- D) Compress data

**Correct Answer: B**

---

**Q168.** Volumes are necessary because containers are:
- A) Permanent
- B) Ephemeral (data deleted when container deleted)
- C) Physical
- D) Always running

**Correct Answer: B**

---

**Q169.** A Namespace is a segment dedicated to:
- A) All users equally
- B) A certain purpose, project, or team
- C) Only administrators
- D) Only databases

**Correct Answer: B**

---

**Q170.** Kubernetes provides:
- A) Service discovery & load balancing
- B) Storage orchestration
- C) Self-healing
- D) All of the above

**Correct Answer: D**

---

**Q171.** Self-healing in Kubernetes:
- A) Restarts failed containers
- B) Replaces containers
- C) Kills unresponsive containers
- D) All of the above

**Correct Answer: D**

---

**Q172.** Kubernetes manages sensitive info like:
- A) Passwords
- B) OAuth tokens
- C) SSH keys
- D) All of the above

**Correct Answer: D**

---

**Q173.** EKS stands for:
- A) Elastic Kubernetes Service
- B) Enterprise Kubernetes System
- C) Extended Kubernetes Server
- D) Elastic Key Service

**Correct Answer: A**

---

**Q174.** EKS is a ______ service.
- A) Unmanaged
- B) Managed
- C) Physical
- D) Desktop

**Correct Answer: B**

---

**Q175.** With EKS, users don't have to maintain:
- A) Their code
- B) Kubernetes control plane
- C) Their laptop
- D) Internet connection

**Correct Answer: B**

---

**Q176.** ECR stands for:
- A) Elastic Container Registry
- B) Enterprise Cloud Resource
- C) Extended Container Runtime
- D) Elastic Compute Registry

**Correct Answer: A**

---

**Q177.** ECR is used for:
- A) Container images
- B) Database storage
- C) Network management
- D) Power supply

**Correct Answer: A**

---

**Q178.** How many steps in EKS Workflow?
- A) 2
- B) 3
- C) 4
- D) 5

**Correct Answer: C**

---

**Q179.** The first step in EKS Workflow is:
- A) Deploy worker nodes
- B) Provision EKS cluster
- C) Configure kubectl
- D) Deploy application

**Correct Answer: B**

---

**Q180.** kubectl is used to:
- A) Communicate with Kubernetes cluster
- B) Store data
- C) Manage databases
- D) Configure firewalls

**Correct Answer: A**

---

**Q181.** How many steps to create EKS cluster via GUI?
- A) 4
- B) 6
- C) 8
- D) 10

**Correct Answer: C**

---

**Q182.** EKS integrates with:
- A) ECR
- B) IAM
- C) VPC
- D) All of the above

**Correct Answer: D**

---

**Q183.** Amazon DocumentDB is compatible with:
- A) MySQL
- B) MongoDB
- C) PostgreSQL
- D) Oracle

**Correct Answer: B**

---

**Q184.** RDS stands for:
- A) Relational Database Service
- B) Remote Data Storage
- C) Reliable Database System
- D) Real-time Data Service

**Correct Answer: A**

---

**Q185.** Redshift uses ______ to achieve 10x performance.
- A) Machine learning
- B) Parallel query execution
- C) Columnar storage
- D) All of the above

**Correct Answer: D**

---

**Q186.** SDK stands for:
- A) Software Development Kit
- B) Server Data Key
- C) Storage Device Kit
- D) System Design Kit

**Correct Answer: A**

---

**Q187.** CLI stands for:
- A) Cloud Level Interface
- B) Command Line Interface
- C) Central Login Identity
- D) Compute Layer Integration

**Correct Answer: B**

---

**Q188.** A Service in Kubernetes defines:
- A) Logical set of pods + access policy
- B) Physical servers
- C) Network cables
- D) Storage devices

**Correct Answer: A**

---

**Q189.** Automated rollouts & rollbacks means Kubernetes can:
- A) Only add new containers
- B) Change actual state to desired state at controlled rate
- C) Only delete containers
- D) Only restart containers

**Correct Answer: B**

---

**Q190.** Automatic bin packing provides:
- A) Efficient node usage for running containerized tasks
- B) Physical packaging
- C) File compression
- D) Data encryption

**Correct Answer: A**

---

**Q191.** CloudTrail events include actions in:
- A) AWS Management Console
- B) AWS CLI
- C) AWS SDKs and APIs
- D) All of the above

**Correct Answer: D**

---

**Q192.** CloudWatch is for monitoring while CloudTrail is for:
- A) Monitoring
- B) Auditing
- C) Storage
- D) Computing

**Correct Answer: B**

---

**Q193.** Which AWS service is serverless?
- A) EC2
- B) Lambda
- C) Outposts
- D) Lightsail

**Correct Answer: B**

---

**Q194.** S3 Glacier is ______ cost than S3 Standard.
- A) Higher
- B) Same
- C) Lower
- D) Free

**Correct Answer: C**

---

**Q195.** Elastic Load Balancer in EKS is used for:
- A) Storing data
- B) Distributing traffic
- C) Creating containers
- D) Managing databases

**Correct Answer: B**

---

**Q196.** VPN stands for:
- A) Virtual Private Network
- B) Virtual Public Network
- C) Verified Protocol Network
- D) Visual Private Node

**Correct Answer: A**

---

**Q197.** RDS supports which of the following engines?
- A) MySQL and PostgreSQL
- B) Oracle and SQL Server
- C) Aurora and MariaDB
- D) All of the above

**Correct Answer: D**

---

**Q198.** EBS replicates within:
- A) Multiple regions
- B) The Availability Zone (AZ)
- C) No replication
- D) Global level

**Correct Answer: B**

---

**Q199.** Redshift can query data across:
- A) Only data warehouse
- B) Only data lake
- C) Both data warehouse and data lake
- D) Neither

**Correct Answer: C**

---

**Q200.** Which is true about AWS?
- A) EC2 provides compute, S3 provides storage, IAM provides security
- B) All services are free
- C) AWS has no security features
- D) AWS only works offline

**Correct Answer: A**

---

> 🎯 **Quick Revision:**
> - **Compute:** EC2, Lambda (serverless), Lightsail (VPS), App Runner, Auto Scaling, Outposts
> - **Storage:** S3 (Buckets/Objects, 5TB max), Glacier (3 classes, 3 retrieval speeds), EBS (persistent), EFS (auto grow/shrink)
> - **Database:** SimpleDB (NoSQL, Erlang), DynamoDB (serverless NoSQL), RDS (7 engines), Redshift (10x warehouse)
> - **Networking:** VPC, API Gateway (REST + WebSocket), CloudFront (CDN), Route 53 (DNS)
> - **Security:** IAM (6-step workflow, MFA, Root User, Groups/Roles/Policies), NIST 800-88, SSL/TLS, ACM
> - **Management:** CloudFormation (IaC), CloudTrail (audit), CloudWatch (monitor), Chatbot (Slack/Teams)
> - **EKS:** K8s objects (Pod, Service, Volume, Namespace), 4-step workflow, 8-step GUI setup
