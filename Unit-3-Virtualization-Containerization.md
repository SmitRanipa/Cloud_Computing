# Unit 3 — Virtualization and Containerization

> **Subject:** CCBD (Cloud Computing & Basics of DevOps) | **Code:** 2301CS738

---

## 1. What is Virtualization?

### Definition
- Virtualization primarily refers to **sharing all hardware resources** while running **several operating systems on a single machine**.
- It is the creation of a **virtual environment** of pre-existing environments such as network resources, operating systems, servers, storage devices, and desktops.
- This increases the **productivity and efficiency** of both professional and personal requirements.

### What is a Virtual Machine (VM)?
- VMs are **software containers** with an operating system and application inside.
- When multiple VMs run on one computer, **more than one OS and application** can run on the **same server/host**.
- A **hypervisor** decouples VMs from the host and **dynamically assigns computing resources** to each VM.
- **Guest OS** = the OS installed using the virtual machine.
- **Host OS** = the physical system's OS where the virtual machine is executed.

---

## 2. Virtualization and Cloud Computing

- Virtualization enables a single computer to host **multiple independent VMs** that share the host's hardware.
- Virtualization software **separates actual physical hardware** from the VM instances.
- An image of a VM can be **saved as a file** and re-started when required.
- Cloud providers employ virtualization to create environments that fulfill each **customer's demands**.
- As more users come in → cloud providers **spin up more virtual instances**.
- As people leave → systems can be **quickly powered down**.

> 🔑 **Key Point:** "Virtualization is the **foundation** which supports cloud computing."

### Key Benefits of Virtualization in Cloud

| Benefit | Description |
|---|---|
| **Protection from Failure & Disaster** | If one part crashes, the entire system doesn't fail. VMs protect IT environment from bugs, viruses, and crashes during testing |
| **Ease of Data Transfer** | Transfer data easily between virtualized devices; can transfer entire machines without moving physical infrastructure — saves time, energy, money |
| **Security** | VMs stay separate from other systems → harder for viruses/malware to spread. Cloud providers offer **encryption using high-end protocols** |
| **Efficiency & Productivity** | Fewer servers to maintain; install updates for all VMs on one server; data always available in virtual server |
| **Development & Testing** | Developers can quickly **spin up segmented environments** without affecting production; can **clone VMs** and run tests |
| **Cost-Effectiveness** | No need to buy physical hardware; reduces waste, electricity, and maintenance costs; saves server space |

---

## 3. Pros and Cons of Virtualization

### Pros ✅
1. **Utilization of hardware efficiently** — maximum use of physical resources
2. **Availability increases** — redundancy and failover
3. **Disaster recovery** is efficient and easy
4. **Saves energy** — fewer physical machines running
5. **Quick and easy setup** — spin up VMs in minutes
6. **Cloud migration becomes easy** — move workloads seamlessly

### Cons ❌
1. **Data can be at risk** — data hosted on third-party shared hardware resources
2. **Learning new infrastructure** — virtual servers and their management software may be unfamiliar to IT team
3. **High initial investment** — initial setup costs for storage and servers can be higher than traditional setup (though saves in long run)

---

## 4. Types of Virtualization (7 Types)

### 4.1 Desktop Virtualization

- **Most common** type of virtualization in the IT industry; widely used in workplace environments.
- User's OS is **remotely stored on a server** in the data center.
- Allows users to access their desktop **virtually, from any location** using a different machine.
- End-users can work on **more than one OS** based on business needs.
- Provides **portability, user mobility, easy software management** with patches and updates.

#### Use Cases:
- Running Linux + Windows on same machine using separate VMs
- Employees logging in **remotely** during natural disaster or health issues
- **VDI (Virtual Desktop Infrastructure)** — centralized management of desktops

### 4.2 Server Virtualization

- Process of **dividing a physical server into multiple unique and isolated virtual servers** using software.
- Each virtual server can run its **own OS independently**.
- **Central server (physical)** is divided by changing identity number and processors.
- Each sub-server knows the identity of the central server.

#### Benefits:
- Increases performance
- Reduces **operating cost** via deployment of main server resources into sub-servers
- Beneficial in: virtual migration, reduced energy consumption, reduced infrastructural cost
- Without server virtualization, physical servers use only a **small amount** of their processing capacity → devices sit idle.

#### Example:
- Running email server, CRM (Customer Relationship Management) system, and databases on **separate virtual servers** within **one physical server** — maximizing hardware utilization.

### 4.3 Storage Virtualization

- Instead of physical storage, **virtual storage uses software** to store data in the cloud.
- All storage disk arrays placed in **same virtual pool** → made into virtual disks → sent to host server.
- Multiple physical storages from **numerous network storage devices** grouped to work as a **single storage device**.
- **Usage:** Mainly for **backup and recovery** purposes.
- Servers aren't aware of exactly **where data is stored** — they function like worker bees in a hive.

#### Two Kinds:
| Kind | Description |
|---|---|
| **Internal** | Only available within a vendor's software; limited data reach |
| **External** | Also powered by vendor but fewer limitations on data source/storage |

#### Two Types:
| Type | Description |
|---|---|
| **Block Storage Virtualization** | Takes over at the **disk level** after replacing controllers; functions before file system comes into picture |
| **File Storage Virtualization** | Server must have software installed to enable usage at the **file system level** |

### 4.4 Network Virtualization

- Running **multiple virtual networks** on the **same physical network** — each with a **separate control and data plan**.
- Physical network is divided into **sub-networks** that co-exist yet have **individual functioning**.
- **Security is NOT compromised** — issues on one network have no domino effect on others.
- Provides facility to create **logical switches, routers, firewalls, load balancers, VPNs (Virtual Private Networks)** within days.
- Main aim: improve **efficiency and productivity** of the network.

#### Two Types:
| Type | Description |
|---|---|
| **Internal Network Virtualization** | Extends network-like functionality to a **single system** |
| **External Network Virtualization** | Combines **multiple networks** or their parts into a **single virtual unit** |

#### Real-World Example:
- **SDN (Software-Defined Networking)** technologies like **Cisco ACI (Application Centric Infrastructure)** allow administrators to control and optimize network traffic through virtualization.

### 4.5 Application Virtualization

- Pulls out functions of applications to run on **OS other than the ones they were designed for**.
- Example: Running a **Windows application on a Linux machine** without changing configuration.
- Runs application software **without installing it directly** on the user's OS.
- Only the **application runs in a virtual environment** — the end user's OS runs as usual.
- Differs from desktop virtualization — here only the **app is virtualized**, not the entire desktop.

#### Three Types:
| Type | Description |
|---|---|
| **Local Application Virtualization** | App code shipped with its own environment to run on **all OS without changes** |
| **Application Streaming** | App lives on a server; sends **small components** to run on end user's device when needed |
| **Server-based Application Virtualization** | Users access remote app from **browser or client interface** without installing it |

### 4.6 Data Virtualization

- **Step 1:** Data collected from **various sources** and managed at a single place without knowing technical details (how collected, stored, formatted).
- **Step 2:** Data arranged logically so its **virtual view can be accessed** by stakeholders remotely through cloud services.
- Providers: **Oracle, IBM, Atscale, CData**, etc.

#### Tasks:
- Data integration, Business integration
- **SOA (Service-Oriented Architecture)** data services
- Searching organizational data

#### Key Features:
- Centrally manage and alter data from **several sources** (Excel files, Google Analytics, HubSpot reports)
- Provides a **holistic/single view** of data.
- Primarily used for: **BI (Business Intelligence)**, Cloud Computing, Data Management.

#### Example:
- A retail business using data virtualization for **unified view of sales data** from physical store, online store's SQL database, and cloud data → enables data-driven decisions for promotions and inventory.

### 4.7 Operating System Virtualization

- When **VMM (Virtual Machine Manager)** is installed on the **Host OS** instead of directly on hardware.
- **Usage:** Mainly for testing applications on **different OS platforms**.
- Process: Disk Image Build → Stored → Streaming → Virtualized.

---

## 5. Implementing Virtualization — Five Levels

Running a different OS on the same hardware is not directly feasible. Virtualization solves this. There are **5 levels**:

### 5.1 ISA (Instruction Set Architecture) Level

| Aspect | Detail |
|---|---|
| **How it works** | Through **ISA emulation** using code interpretation |
| **Basic method** | Interpreter interprets source instructions to target instructions **one by one** |
| **Performance** | Basic emulation is **slow** (1 source → tens/hundreds of target instructions) |
| **Better approach** | **Dynamic binary translation** — translates basic blocks of dynamic source instructions |
| **Use case** | Running **legacy code** originally written for different hardware |
| **Examples** | BIRD, Dynamo |
| **Benefit** | Makes VM **hardware-agnostic** |

### 5.2 HAL (Hardware Abstraction Level)

| Aspect | Detail |
|---|---|
| **How it works** | Uses a **bare hypervisor** for functioning |
| **What it does** | Forms VMs and manages hardware; virtualizes **each hardware component** (I/O, processors, memory) |
| **Multi-user** | Multiple users can use same hardware with **numerous instances** simultaneously |
| **History** | IBM first implemented on **IBM VM/370 in 1960** |
| **Current usage** | **Xen hypervisors** using HAL to run Linux on x86 machines |
| **Examples** | VMware, Virtual PC |
| **Advantage** | Higher performance and **good application isolation** |
| **Limitation** | **Very expensive** to implement (complexity) |

### 5.3 Operating System Level

| Aspect | Detail |
|---|---|
| **How it works** | Creates abstract layer between applications and OS; like an **isolated container** on physical server |
| **Use case** | High number of users, no one willing to share hardware → each gets own virtual environment |
| **Common use** | Creating **virtual hosting environments** to allocate hardware among **mutually distrusting users** |
| **Examples** | Virtual Environment, FVM |
| **Advantage** | Minimum **startup/shutdown costs**; easy synchronization with environment |
| **Limitation** | All VMs must have **same kind of guest OS**; poor application flexibility and isolation |

### 5.4 Library Level

| Aspect | Detail |
|---|---|
| **How it works** | Controls communication between applications and system through **API hooks** |
| **Examples** | **WINE** (Windows apps on UNIX hosts), **vCUDA** (GPU hardware acceleration in VMs) |
| **Advantage** | Very **low implementation effort** |
| **Limitation** | Poor application flexibility and isolation |

### 5.5 Application Level

| Aspect | Detail |
|---|---|
| **How it works** | Virtualizes **only an application**, not entire platform; apps work as one process (**process-level virtualization**) |
| **Use case** | Running VMs with **high-level languages** |
| **Structure** | Application → Virtualization Layer → Application Program → OS |
| **Examples** | **JVM (Java Virtual Machine)**, **.NET CLR (Common Language Runtime)** |
| **Advantage** | **Best application isolation** |
| **Limitation** | Low performance, low flexibility, **high implementation complexity** |

### Summary Table of 5 Levels

| Level | Examples | Advantage | Limitation |
|---|---|---|---|
| **ISA** | BIRD, Dynamo | Hardware-agnostic | Slow (basic emulation) |
| **HAL** | VMware, Virtual PC | High performance, good isolation | Very expensive |
| **OS Level** | Virtual Environment, FVM | Low startup cost, easy sync | Same guest OS required |
| **Library** | WINE, vCUDA | Low implementation effort | Poor flexibility & isolation |
| **Application** | JVM, .NET CLR | Best isolation | Low performance, high complexity |

---

## 6. Hypervisor (Virtual Machine Monitor — VMM)

### What is a Hypervisor?
- Software that creates a **virtual layer over hardware** and manages interaction between VMs and hardware resources.
- Also known as **VMM (Virtual Machine Monitor)**.
- Allows **one host computer** to support **multiple guest VMs** by virtually sharing resources (memory, processing).
- Manages so that VMs don't **interfere with each other's memory and computing resources**.
- Controls and allocates **what portion of hardware** each OS gets.

### Type 1: Bare Metal Hypervisor
- Runs **directly on system hardware** (bare metal) — no host OS in between.
- Structure: **Hardware → Hypervisor → Guest OS(es)**
- Also called **native hypervisor**.
- First implemented: **CP/CMS hypervisor by IBM**.
- **Examples:** VMware ESX/ESXi, Microsoft Hyper-V, Citrix XenServer, Oracle VM
- **Performance:** Higher (no host OS overhead)
- **Use:** Data centers, enterprise environments

### Type 2: Hosted Hypervisor
- Runs **over a host operating system** — hypervisor is the second layer over hardware.
- Structure: **Hardware → Host OS → Hypervisor → Guest OS(es)**
- The host OS is usually **unaware of the virtualization**.
- Provides virtualization services like **I/O device support and memory management**.
- **Examples:** VMware Workstation/Fusion/Player, Microsoft Virtual PC, Oracle VM VirtualBox, Red Hat Enterprise Virtualization
- **Performance:** Lower than Type 1 (host OS overhead)
- **Use:** Personal use, development, testing

### Type 1 vs Type 2 Comparison

| Aspect | Type 1 (Bare Metal) | Type 2 (Hosted) |
|---|---|---|
| Runs on | Directly on **hardware** | On top of **host OS** |
| Performance | **Higher** | Lower (OS overhead) |
| Examples | VMware ESXi, Hyper-V, XenServer | VirtualBox, VMware Workstation |
| Use Case | Enterprise, data centers | Personal, testing |
| OS Awareness | No host OS | Host OS present |

### Benefits of Hypervisors
1. **Speed** — VMs created instantly; easy to provision resources for dynamic workloads
2. **Efficiency** — multiple VMs on one machine = more efficient utilization; cost and energy efficient
3. **Flexibility** — bare-metal hypervisors allow OS to run on variety of hardware
4. **Portability** — VMs are independent from physical machine → can be moved easily

---

## 7. Docker

### What is Docker?
- An **open platform** for **developing, shipping, and running applications**.
- Enables you to **separate applications from infrastructure** → deliver software quickly.
- A **containerization platform** that allows developers to **package programs into containers**.
- Written in **Go language** (developed by Google).
- In simpler words: Docker lets you run your **operating system as a container**.

### The Container Analogy (Shipping Container)
- Before 1960: transporting goods via train, ship, truck was **complex and inefficient**.
- **Solution:** Standard containers — loaded, sealed, transported anywhere via any means.

Similarly, Docker containers provide:
- **Portability** for applications
- **Standard format** across environments
- Include **all dependencies**
- **Workload isolation** at runtime

### Why Docker?
- Different languages, architectures, frameworks create enormous complexity.
- Docker **simplifies and accelerates** the workflow.
- Docker = **shipping container for code**.

### Docker vs VMs — Memory
- VMs: blocked memory **cannot be allotted** to new VM (e.g., 7 GB blocked)
- Docker: unused memory **can be allotted** to new container (e.g., 7 GB available)

---

## 8. Containerization

### What is a Container?
- **Virtual compartments** that run software applications.
- Small, **self-contained boxes** holding everything an app needs.
- Always runs **on top of the host OS**.
- **Isolated** but share: **OS, binaries, libraries**, and the application.
- **Much lighter and faster** than VMs.

### Container vs Virtual Machine

| Feature | Container | Virtual Machine |
|---|---|---|
| **OS** | Shares host OS kernel | Each has **own full OS** |
| **Size** | Lightweight (MBs) | Heavy (GBs) |
| **Startup** | **Seconds** | **Minutes** |
| **Isolation** | Process-level | Full hardware-level |
| **Resource Usage** | Minimal | Significant |
| **Portability** | Highly portable | Less portable |
| **Performance** | Near-native | Slight overhead |
| **Examples** | Docker, Kubernetes | VMware, VirtualBox, Hyper-V |

---

## 9. Docker Commands Reference

| Command | Usage | Function |
|---|---|---|
| `docker --version` | `docker --version` | Get Docker version |
| `docker pull` | `docker pull <image>` | Pull images from Docker Hub |
| `docker images` | `docker images` | List all locally stored images |
| `docker run` | `docker run -it -d <image>` | Create a container from an image |
| `docker ps` | `docker ps` | List running containers |
| `docker ps -a` | `docker ps -a` | Show all running + exited containers |
| `docker exec` | `docker exec -it <id> bash` | Access a running container |
| `docker stop` | `docker stop <id>` | Stop container (graceful shutdown) |
| `docker kill` | `docker kill <id>` | Kill container immediately |
| `docker commit` | `docker commit <id> <user/image>` | Create new image of edited container |
| `docker login` | `docker login` | Login to Docker Hub |

> 🔑 **docker stop vs docker kill:** `stop` = **graceful shutdown**; `kill` = **immediate stop**.

---

## 📋 Abbreviation Table

| Short Form | Full Form |
|---|---|
| ACI | Application Centric Infrastructure |
| API | Application Programming Interface |
| BI | Business Intelligence |
| CCBD | Cloud Computing & Basics of DevOps |
| CLR | Common Language Runtime |
| CP/CMS | Control Program / Conversational Monitor System |
| CRM | Customer Relationship Management |
| FVM | Featherweight Virtual Machine |
| HAL | Hardware Abstraction Level |
| I/O | Input/Output |
| ISA | Instruction Set Architecture |
| JVM | Java Virtual Machine |
| OS | Operating System |
| SDN | Software-Defined Networking |
| SOA | Service-Oriented Architecture |
| vCUDA | Virtual Compute Unified Device Architecture |
| VDI | Virtual Desktop Infrastructure |
| VM | Virtual Machine |
| VMM | Virtual Machine Monitor |
| VPN | Virtual Private Network |
| WINE | Wine Is Not an Emulator |

---

> 🎯 **Exam Tips:** Focus on — 7 Types of Virtualization (definitions + subtypes), 5 Levels of Implementation (ISA/HAL/OS/Library/Application with examples & advantages/limitations), Type 1 vs Type 2 Hypervisor (differences + examples), Docker concept & container analogy, Container vs VM comparison, Docker commands, and Pros/Cons of Virtualization.


---

# 📝 MCQ Bank — Unit 3: Virtualization & Containerization (200 Questions)

---

## Section A: Virtualization Basics (Q1–Q30)

**Q1.** Virtualization primarily refers to:
- A) Running one OS on one machine
- B) Sharing all hardware resources while running several OS on a single machine
- C) Buying multiple physical servers
- D) None of the given

**Correct Answer: B**

---

**Q2.** What is a Virtual Machine (VM)?
- A) A physical computer
- B) A software container with an OS and application inside
- C) A type of hard drive
- D) A networking cable

**Correct Answer: B**

---

**Q3.** Which of the following is true about VMs?
- A) Multiple VMs can run on one computer
- B) A hypervisor dynamically assigns computing resources to each VM
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q4.** The OS installed using the virtual machine is called:
- A) Host OS
- B) Guest OS
- C) Virtual OS
- D) Cloud OS

**Correct Answer: B**

---

**Q5.** The physical system's OS where the virtual machine is executed is called:
- A) Guest OS
- B) Cloud OS
- C) Host OS
- D) Virtual OS

**Correct Answer: C**

---

**Q6.** "Virtualization is the foundation which supports ______."
- A) Networking
- B) Cloud Computing
- C) Data Mining
- D) Artificial Intelligence

**Correct Answer: B**

---

**Q7.** An image of a VM can be:
- A) Saved as a file
- B) Re-started when required
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q8.** Which of the following is NOT a benefit of virtualization in cloud?
- A) Protection from failure
- B) Increased hardware cost
- C) Security
- D) Ease of data transfer

**Correct Answer: B**

---

**Q9.** Cloud providers offer ______ using high-end protocols to protect data.
- A) Compression
- B) Encryption
- C) Decompression
- D) Fragmentation

**Correct Answer: B**

---

**Q10.** Developers can quickly ______ a virtual machine and run tests on it.
- A) Delete
- B) Clone
- C) Sell
- D) Format

**Correct Answer: B**

---

**Q11.** Which of the following is a Pro of Virtualization?
- A) Data can be at risk
- B) High initial investment
- C) Disaster recovery is efficient and easy
- D) Learning new infrastructure

**Correct Answer: C**

---

**Q12.** Which of the following is a Con of Virtualization?
- A) Hardware utilized efficiently
- B) Saves energy
- C) Quick and easy setup
- D) Data can be at risk

**Correct Answer: D**

---

**Q13.** Which of the following are Pros of Virtualization?
- A) Saves energy
- B) Cloud migration becomes easy
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q14.** "High initial investment" is a ______ of virtualization.
- A) Pro
- B) Con
- C) Feature
- D) Benefit

**Correct Answer: B**

---

**Q15.** How many Pros of Virtualization are discussed?
- A) 4
- B) 5
- C) 6
- D) 7

**Correct Answer: C**

---

**Q16.** How many Cons of Virtualization are discussed?
- A) 2
- B) 3
- C) 4
- D) 5

**Correct Answer: B**

---

**Q17.** Virtualization software separates ______ from VM instances.
- A) Application software
- B) Actual physical hardware
- C) Cloud services
- D) Network cables

**Correct Answer: B**

---

**Q18.** Which is NOT a key benefit of virtualization in cloud?
- A) Development & Testing
- B) Cost-Effectiveness
- C) Increased physical server usage
- D) Security

**Correct Answer: C**

---

**Q19.** Which component decouples VMs from the host?
- A) Router
- B) Switch
- C) Hypervisor
- D) Firewall

**Correct Answer: C**

---

**Q20.** Virtualization increases ______ and ______ of requirements.
- A) Cost and complexity
- B) Productivity and efficiency
- C) Risk and failure
- D) Size and weight

**Correct Answer: B**

---

**Q21.** Which of the following can be virtualized?
- A) Network resources
- B) Servers
- C) Storage devices
- D) All of the above

**Correct Answer: D**

---

**Q22.** When more users come in, cloud providers:
- A) Buy new physical servers
- B) Spin up more virtual instances
- C) Shut down the system
- D) Reduce resources

**Correct Answer: B**

---

**Q23.** VMs protect IT environment from:
- A) Bugs
- B) Viruses
- C) Crashes during testing
- D) All of the above

**Correct Answer: D**

---

**Q24.** Virtualization helps in ______ by reducing waste, electricity, and maintenance costs.
- A) Cost-Effectiveness
- B) Complexity
- C) Risk Management
- D) Data Loss

**Correct Answer: A**

---

**Q25.** Which of the following is true?
- A) Guest OS runs inside the virtual machine
- B) Host OS is the physical system's OS
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q26.** "Learning new infrastructure" is a ______ of virtualization.
- A) Pro
- B) Feature
- C) Benefit
- D) Con

**Correct Answer: D**

---

**Q27.** Cloud migration becomes easy due to:
- A) Virtualization
- B) Manual server setup
- C) Physical hardware purchase
- D) Cable management

**Correct Answer: A**

---

**Q28.** Disaster recovery in virtualization is:
- A) Difficult and expensive
- B) Efficient and easy
- C) Not possible
- D) Only for large companies

**Correct Answer: B**

---

**Q29.** In virtualization, data transfer between devices is:
- A) Very difficult
- B) Easy without moving physical infrastructure
- C) Only possible with cables
- D) Not supported

**Correct Answer: B**

---

**Q30.** Availability ______ with virtualization.
- A) Decreases
- B) Remains same
- C) Increases
- D) Is not affected

**Correct Answer: C**

---

## Section B: Types of Virtualization (Q31–Q75)

**Q31.** How many types of virtualization are discussed?
- A) 5
- B) 6
- C) 7
- D) 8

**Correct Answer: C**

---

**Q32.** Which is the most common type of virtualization in the IT industry?
- A) Server Virtualization
- B) Desktop Virtualization
- C) Network Virtualization
- D) Data Virtualization

**Correct Answer: B**

---

**Q33.** In Desktop Virtualization, user's OS is remotely stored on a:
- A) USB drive
- B) Server in the data center
- C) Local hard disk
- D) CD-ROM

**Correct Answer: B**

---

**Q34.** Desktop Virtualization provides:
- A) Portability
- B) User mobility
- C) Easy software management
- D) All of the above

**Correct Answer: D**

---

**Q35.** VDI stands for:
- A) Virtual Desktop Interface
- B) Virtual Desktop Infrastructure
- C) Virtualized Data Integration
- D) Virtual Device Interface

**Correct Answer: B**

---

**Q36.** Server Virtualization divides a physical server into:
- A) Multiple unique and isolated virtual servers
- B) Multiple physical servers
- C) Multiple hard drives
- D) Multiple network cables

**Correct Answer: A**

---

**Q37.** In Server Virtualization, each virtual server can run:
- A) Only the same OS as host
- B) Its own OS independently
- C) Only Linux
- D) Only Windows

**Correct Answer: B**

---

**Q38.** Without server virtualization, physical servers use only ______ of their processing capacity.
- A) All
- B) Most
- C) A small amount
- D) Half

**Correct Answer: C**

---

**Q39.** Which of the following is an example of Server Virtualization use case?
- A) Running email server, CRM, and databases on separate virtual servers within one physical server
- B) Running one application on one server
- C) Using a single monitor
- D) Printing documents

**Correct Answer: A**

---

**Q40.** CRM stands for:
- A) Customer Resource Management
- B) Customer Relationship Management
- C) Cloud Resource Management
- D) Central Resource Manager

**Correct Answer: B**

---

**Q41.** Storage Virtualization uses ______ to store data in the cloud.
- A) Hardware
- B) Physical disks only
- C) Software
- D) Cables

**Correct Answer: C**

---

**Q42.** Storage Virtualization is mainly used for:
- A) Gaming
- B) Backup and recovery
- C) Video editing
- D) Music streaming

**Correct Answer: B**

---

**Q43.** How many kinds of Storage Virtualization are there?
- A) 1
- B) 2
- C) 3
- D) 4

**Correct Answer: B**

---

**Q44.** How many types of Storage Virtualization are there?
- A) 1
- B) 2
- C) 3
- D) 4

**Correct Answer: B**

---

**Q45.** Which type of Storage Virtualization takes over at the disk level?
- A) File Storage Virtualization
- B) Block Storage Virtualization
- C) Internal Storage Virtualization
- D) External Storage Virtualization

**Correct Answer: B**

---

**Q46.** In Storage Virtualization, servers function like:
- A) Lions in a jungle
- B) Worker bees in a hive
- C) Fish in water
- D) Birds in the sky

**Correct Answer: B**

---

**Q47.** Internal Storage Virtualization is:
- A) Available everywhere
- B) Only available within a vendor's software with limited data reach
- C) Free to use
- D) Available on all platforms

**Correct Answer: B**

---

**Q48.** Network Virtualization runs multiple virtual networks on:
- A) Multiple physical networks
- B) The same physical network
- C) No network
- D) Only wireless networks

**Correct Answer: B**

---

**Q49.** In Network Virtualization, each virtual network has:
- A) Same control plan
- B) No control plan
- C) Separate control and data plan
- D) Shared data plan only

**Correct Answer: C**

---

**Q50.** Network Virtualization provides facility to create:
- A) Logical switches and routers
- B) Firewalls and load balancers
- C) VPNs
- D) All of the above

**Correct Answer: D**

---

**Q51.** How many types of Network Virtualization are there?
- A) 1
- B) 2
- C) 3
- D) 4

**Correct Answer: B**

---

**Q52.** SDN stands for:
- A) Software-Defined Networking
- B) Server-Defined Networking
- C) Storage-Defined Networking
- D) System-Defined Networking

**Correct Answer: A**

---

**Q53.** ACI stands for:
- A) Application Cloud Infrastructure
- B) Application Centric Infrastructure
- C) Advanced Cloud Integration
- D) Automated Centric Interface

**Correct Answer: B**

---

**Q54.** Internal Network Virtualization extends network-like functionality to:
- A) Multiple systems
- B) A single system
- C) All systems in the world
- D) No system

**Correct Answer: B**

---

**Q55.** External Network Virtualization combines multiple networks into:
- A) Multiple virtual units
- B) A single virtual unit
- C) Physical cables
- D) None of the given

**Correct Answer: B**

---

**Q56.** Application Virtualization runs app software without:
- A) Any network
- B) Any user
- C) Installing it directly on user's OS
- D) Any power supply

**Correct Answer: C**

---

**Q57.** In Application Virtualization, which runs in a virtual environment?
- A) The entire OS
- B) Only the application
- C) Both OS and application
- D) Neither

**Correct Answer: B**

---

**Q58.** How many types of Application Virtualization are there?
- A) 2
- B) 3
- C) 4
- D) 5

**Correct Answer: B**

---

**Q59.** In Application Streaming, the app lives on a ______ and sends small components to the end user's device.
- A) Local disk
- B) USB drive
- C) Server
- D) CD-ROM

**Correct Answer: C**

---

**Q60.** Which type of Application Virtualization lets users access apps from a browser?
- A) Local Application Virtualization
- B) Application Streaming
- C) Server-based Application Virtualization
- D) Desktop Virtualization

**Correct Answer: C**

---

**Q61.** Data Virtualization provides a ______ view of data from multiple sources.
- A) Fragmented
- B) Holistic/single
- C) Encrypted
- D) Hidden

**Correct Answer: B**

---

**Q62.** Which of the following is a Data Virtualization provider?
- A) Oracle
- B) IBM
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q63.** Data Virtualization is primarily used for:
- A) BI (Business Intelligence)
- B) Cloud Computing
- C) Data Management
- D) All of the above

**Correct Answer: D**

---

**Q64.** BI stands for:
- A) Basic Intelligence
- B) Business Intelligence
- C) Binary Integration
- D) Browser Interface

**Correct Answer: B**

---

**Q65.** SOA stands for:
- A) Service-Oriented Architecture
- B) System-Oriented Application
- C) Software-Oriented Access
- D) Server-Oriented Architecture

**Correct Answer: A**

---

**Q66.** Operating System Virtualization is mainly used for:
- A) Gaming
- B) Testing applications on different OS platforms
- C) Music production
- D) Video editing

**Correct Answer: B**

---

**Q67.** In OS Virtualization, VMM is installed on:
- A) Directly on hardware
- B) The Host OS
- C) The Guest OS
- D) The cloud

**Correct Answer: B**

---

**Q68.** Which of the following is true about Desktop Virtualization?
- A) End-users can work on more than one OS
- B) Users can access desktop from any location
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q69.** Which virtualization type allows employees to log in remotely during disasters?
- A) Storage Virtualization
- B) Network Virtualization
- C) Desktop Virtualization
- D) Data Virtualization

**Correct Answer: C**

---

**Q70.** Server Virtualization reduces:
- A) Operating cost
- B) Energy consumption
- C) Infrastructural cost
- D) All of the above

**Correct Answer: D**

---

**Q71.** Block Storage Virtualization functions ______ the file system comes into picture.
- A) After
- B) Before
- C) Same time as
- D) Never

**Correct Answer: B**

---

**Q72.** Which is NOT a type of Virtualization?
- A) Desktop Virtualization
- B) Keyboard Virtualization
- C) Server Virtualization
- D) Network Virtualization

**Correct Answer: B**

---

**Q73.** In Network Virtualization, issues on one network have ______ effect on others.
- A) Major
- B) Minor
- C) No domino
- D) Complete

**Correct Answer: C**

---

**Q74.** Application Virtualization differs from Desktop Virtualization because:
- A) Only the app is virtualized, not the entire desktop
- B) The entire desktop is virtualized
- C) No virtualization happens
- D) Both are exactly same

**Correct Answer: A**

---

**Q75.** The process of OS Virtualization is:
- A) Build → Store → Stream → Virtualize
- B) Store → Build → Virtualize → Stream
- C) Virtualize → Store → Build → Stream
- D) Stream → Build → Store → Virtualize

**Correct Answer: A**

---

## Section C: Five Levels of Implementing Virtualization (Q76–Q115)

**Q76.** How many levels of virtualization implementation are there?
- A) 3
- B) 4
- C) 5
- D) 6

**Correct Answer: C**

---

**Q77.** ISA stands for:
- A) Integrated System Architecture
- B) Instruction Set Architecture
- C) Internal System Access
- D) Internet Service Architecture

**Correct Answer: B**

---

**Q78.** HAL stands for:
- A) Hardware Abstraction Level
- B) High Application Layer
- C) Host Abstraction Level
- D) Hardware Access Layer

**Correct Answer: A**

---

**Q79.** At ISA level, virtualization works through:
- A) Hardware modification
- B) ISA emulation
- C) Software deletion
- D) Cable management

**Correct Answer: B**

---

**Q80.** The basic emulation method at ISA level is through:
- A) Hardware installation
- B) Code interpretation
- C) Network configuration
- D) Cloud deployment

**Correct Answer: B**

---

**Q81.** At ISA level, basic emulation is:
- A) Very fast
- B) Moderately fast
- C) Relatively slow
- D) Instant

**Correct Answer: C**

---

**Q82.** For better performance at ISA level, ______ is desired.
- A) Static binary translation
- B) Dynamic binary translation
- C) Code deletion
- D) Manual compilation

**Correct Answer: B**

---

**Q83.** ISA level makes the VM:
- A) Hardware-dependent
- B) Hardware-agnostic
- C) Software-dependent
- D) OS-dependent

**Correct Answer: B**

---

**Q84.** Which are examples of ISA level virtualization?
- A) BIRD and Dynamo
- B) VMware and VirtualBox
- C) JVM and .NET CLR
- D) WINE and vCUDA

**Correct Answer: A**

---

**Q85.** HAL level uses a ______ for its functioning.
- A) Hosted hypervisor
- B) Bare hypervisor
- C) Application layer
- D) Network protocol

**Correct Answer: B**

---

**Q86.** HAL level virtualizes each hardware component such as:
- A) I/O devices
- B) Processors
- C) Memory
- D) All of the above

**Correct Answer: D**

---

**Q87.** IBM first implemented HAL on:
- A) IBM PC in 1981
- B) IBM VM/370 in 1960
- C) IBM Mainframe in 2000
- D) IBM Cloud in 2010

**Correct Answer: B**

---

**Q88.** Which hypervisors currently use HAL to run Linux on x86 machines?
- A) VMware
- B) Xen hypervisors
- C) VirtualBox
- D) Hyper-V

**Correct Answer: B**

---

**Q89.** What is the advantage of HAL level?
- A) Low cost
- B) Higher performance and good application isolation
- C) Easy to implement
- D) No hardware needed

**Correct Answer: B**

---

**Q90.** What is the limitation of HAL level?
- A) Poor performance
- B) No isolation
- C) Very expensive to implement (complexity)
- D) Cannot run VMs

**Correct Answer: C**

---

**Q91.** Which are examples of HAL level virtualization?
- A) BIRD and Dynamo
- B) VMware and Virtual PC
- C) JVM and .NET CLR
- D) WINE and vCUDA

**Correct Answer: B**

---

**Q92.** At OS level, virtualization creates ______ between applications and OS.
- A) A physical barrier
- B) An abstract layer
- C) A network connection
- D) A hardware bridge

**Correct Answer: B**

---

**Q93.** OS level virtualization is commonly used for creating:
- A) Gaming environments
- B) Virtual hosting environments
- C) Music studios
- D) Video servers

**Correct Answer: B**

---

**Q94.** What is the advantage of OS level virtualization?
- A) Maximum startup costs
- B) Minimum startup/shutdown costs
- C) Very expensive
- D) Poor synchronization

**Correct Answer: B**

---

**Q95.** What is a limitation of OS level virtualization?
- A) All VMs must have the same kind of guest OS
- B) High cost
- C) Slow speed
- D) No VMs supported

**Correct Answer: A**

---

**Q96.** Which are examples of OS level virtualization?
- A) Virtual Environment and FVM
- B) VMware and VirtualBox
- C) JVM and CLR
- D) BIRD and Dynamo

**Correct Answer: A**

---

**Q97.** FVM stands for:
- A) Fast Virtual Machine
- B) Featherweight Virtual Machine
- C) Full Virtual Manager
- D) Flexible Virtual Module

**Correct Answer: B**

---

**Q98.** Library level controls communication through:
- A) Physical cables
- B) API hooks
- C) Radio signals
- D) Bluetooth

**Correct Answer: B**

---

**Q99.** WINE is an example of ______ level virtualization.
- A) ISA
- B) HAL
- C) Library
- D) Application

**Correct Answer: C**

---

**Q100.** WINE stands for:
- A) Windows Internet Explorer
- B) Wine Is Not an Emulator
- C) Wireless Network Environment
- D) Wide Integrated Network

**Correct Answer: B**

---

**Q101.** WINE allows running ______ applications on ______ hosts.
- A) Linux on Windows
- B) Windows on UNIX
- C) Mac on Linux
- D) Android on iOS

**Correct Answer: B**

---

**Q102.** vCUDA allows applications to leverage:
- A) CPU acceleration
- B) GPU hardware acceleration
- C) RAM acceleration
- D) Disk acceleration

**Correct Answer: B**

---

**Q103.** The advantage of Library level is:
- A) Very high cost
- B) Very low implementation effort
- C) Best isolation
- D) Highest performance

**Correct Answer: B**

---

**Q104.** Application level virtualization is also known as:
- A) System-level virtualization
- B) Network-level virtualization
- C) Process-level virtualization
- D) Hardware-level virtualization

**Correct Answer: C**

---

**Q105.** JVM stands for:
- A) Java Virtual Machine
- B) Java Version Manager
- C) Joint Virtual Module
- D) Java Verified Method

**Correct Answer: A**

---

**Q106.** CLR stands for:
- A) Cloud Layer Runtime
- B) Common Language Runtime
- C) Central Layer Resource
- D) Common Library Resource

**Correct Answer: B**

---

**Q107.** Which are examples of Application level virtualization?
- A) JVM and .NET CLR
- B) VMware and VirtualBox
- C) BIRD and Dynamo
- D) WINE and vCUDA

**Correct Answer: A**

---

**Q108.** The advantage of Application level is:
- A) Lowest isolation
- B) Best application isolation
- C) Fastest performance
- D) Cheapest to implement

**Correct Answer: B**

---

**Q109.** Which level has the limitation of "high implementation complexity"?
- A) ISA
- B) HAL
- C) Library
- D) Application

**Correct Answer: D**

---

**Q110.** Which level has the advantage of "hardware-agnostic" VMs?
- A) ISA
- B) HAL
- C) OS Level
- D) Application

**Correct Answer: A**

---

**Q111.** Which level uses "mutually distrusting users"?
- A) ISA
- B) HAL
- C) OS Level
- D) Library

**Correct Answer: C**

---

**Q112.** At Application level, applications sit:
- A) Directly on hardware
- B) On top of the virtualization layer
- C) Inside the OS kernel
- D) On network cables

**Correct Answer: B**

---

**Q113.** Which level is the most expensive to implement?
- A) ISA
- B) HAL
- C) Library
- D) Application

**Correct Answer: B**

---

**Q114.** Which level has the lowest implementation effort?
- A) ISA
- B) HAL
- C) Library
- D) Application

**Correct Answer: C**

---

**Q115.** Match: "Poor application flexibility and isolation" is a limitation of:
- A) ISA and HAL
- B) OS Level and Library
- C) HAL and Application
- D) ISA and Application

**Correct Answer: B**

---

## Section D: Hypervisor / VMM (Q116–Q150)

**Q116.** A hypervisor is also known as:
- A) Virtual Machine Manager
- B) Virtual Machine Monitor
- C) VMM
- D) All of the above

**Correct Answer: D**

---

**Q117.** How many types of hypervisors are there?
- A) 1
- B) 2
- C) 3
- D) 4

**Correct Answer: B**

---

**Q118.** Type 1 hypervisor runs:
- A) On top of host OS
- B) Directly on system hardware
- C) Inside applications
- D) On cloud only

**Correct Answer: B**

---

**Q119.** Type 1 hypervisor is also called:
- A) Hosted hypervisor
- B) Bare metal hypervisor
- C) Cloud hypervisor
- D) Application hypervisor

**Correct Answer: B**

---

**Q120.** The structure of Type 1 hypervisor is:
- A) Hardware → Host OS → Hypervisor → Guest OS
- B) Hardware → Hypervisor → Guest OS
- C) Hardware → Guest OS → Hypervisor
- D) Guest OS → Hardware → Hypervisor

**Correct Answer: B**

---

**Q121.** The structure of Type 2 hypervisor is:
- A) Hardware → Hypervisor → Guest OS
- B) Hardware → Guest OS → Host OS
- C) Hardware → Host OS → Hypervisor → Guest OS
- D) Host OS → Hardware → Guest OS

**Correct Answer: C**

---

**Q122.** Which is an example of Type 1 (Bare Metal) hypervisor?
- A) Oracle VM VirtualBox
- B) VMware Workstation
- C) VMware ESXi
- D) Microsoft Virtual PC

**Correct Answer: C**

---

**Q123.** Which is an example of Type 2 (Hosted) hypervisor?
- A) Microsoft Hyper-V
- B) Citrix XenServer
- C) Oracle VM VirtualBox
- D) VMware ESXi

**Correct Answer: C**

---

**Q124.** Which of the following are Type 1 hypervisors?
- A) VMware ESXi and Microsoft Hyper-V
- B) Citrix XenServer and Oracle VM
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q125.** Which of the following are Type 2 hypervisors?
- A) VMware Workstation and VirtualBox
- B) Microsoft Virtual PC
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q126.** The first hypervisor was:
- A) VMware
- B) CP/CMS by IBM
- C) VirtualBox
- D) Hyper-V

**Correct Answer: B**

---

**Q127.** CP/CMS stands for:
- A) Central Processing / Cloud Monitor System
- B) Control Program / Conversational Monitor System
- C) Computer Program / Central Management System
- D) Cloud Platform / Container Management System

**Correct Answer: B**

---

**Q128.** In Type 2 hypervisor, the host OS is usually:
- A) Fully aware of virtualization
- B) Unaware of the virtualization
- C) Removed from the system
- D) Replaced by hypervisor

**Correct Answer: B**

---

**Q129.** Which type of hypervisor has higher performance?
- A) Type 1
- B) Type 2
- C) Both are same
- D) Neither

**Correct Answer: A**

---

**Q130.** Type 2 hypervisor has lower performance because of:
- A) No OS
- B) Host OS overhead
- C) Too much RAM
- D) Network issues

**Correct Answer: B**

---

**Q131.** Type 1 hypervisor is typically used in:
- A) Personal laptops
- B) Data centers and enterprise environments
- C) Mobile phones
- D) Gaming consoles

**Correct Answer: B**

---

**Q132.** Type 2 hypervisor is typically used for:
- A) Enterprise data centers
- B) Personal use, development, and testing
- C) Satellite communication
- D) Industrial automation

**Correct Answer: B**

---

**Q133.** Which is NOT a benefit of hypervisors?
- A) Speed
- B) Efficiency
- C) Increased hardware cost
- D) Portability

**Correct Answer: C**

---

**Q134.** Hypervisors allow VMs to be created:
- A) In weeks
- B) In months
- C) Instantly
- D) Never

**Correct Answer: C**

---

**Q135.** Hypervisors ensure that VMs don't interfere with each other's:
- A) Memory and computing resources
- B) Physical cables
- C) Power supply
- D) Display monitors

**Correct Answer: A**

---

**Q136.** Bare-metal hypervisors allow OS to run on:
- A) Only one specific hardware
- B) A variety of hardware types
- C) No hardware
- D) Only Intel processors

**Correct Answer: B**

---

**Q137.** VMs run by hypervisors are ______ from the physical machine.
- A) Dependent
- B) Independent
- C) Connected permanently
- D) Inseparable

**Correct Answer: B**

---

**Q138.** Red Hat Enterprise Virtualization is a ______ hypervisor.
- A) Type 1
- B) Type 2
- C) Type 3
- D) Type 4

**Correct Answer: B**

---

**Q139.** Microsoft Hyper-V is a ______ hypervisor.
- A) Type 1
- B) Type 2
- C) Type 3
- D) Not a hypervisor

**Correct Answer: A**

---

**Q140.** VMware Workstation is a ______ hypervisor, while VMware ESXi is a ______ hypervisor.
- A) Type 1, Type 2
- B) Type 2, Type 1
- C) Type 1, Type 1
- D) Type 2, Type 2

**Correct Answer: B**

---

**Q141.** Hypervisor is part of the ______ cloud that manages VMs.
- A) Public
- B) Private
- C) Hybrid
- D) Community

**Correct Answer: B**

---

**Q142.** Type 2 hypervisor provides services such as:
- A) I/O device support
- B) Memory management
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q143.** How many benefits of hypervisors are discussed?
- A) 2
- B) 3
- C) 4
- D) 5

**Correct Answer: C**

---

**Q144.** Which of the following is a benefit of hypervisors?
- A) Speed
- B) Efficiency
- C) Flexibility
- D) All of the above

**Correct Answer: D**

---

**Q145.** Citrix XenServer is a ______ hypervisor.
- A) Type 1
- B) Type 2
- C) Type 3
- D) Not a hypervisor

**Correct Answer: A**

---

**Q146.** VMware Fusion is a ______ hypervisor.
- A) Type 1
- B) Type 2
- C) Both
- D) Neither

**Correct Answer: B**

---

**Q147.** Portability in hypervisors means:
- A) VMs cannot be moved
- B) VMs are independent and can be moved easily
- C) Physical servers are portable
- D) Cables are wireless

**Correct Answer: B**

---

**Q148.** A hypervisor allows one host computer to support:
- A) Only one VM
- B) Multiple guest VMs
- C) No VMs
- D) Only two VMs

**Correct Answer: B**

---

**Q149.** The hypervisor controls and allocates:
- A) What portion of hardware each OS gets
- B) Internet speed
- C) Physical cables
- D) Display resolution

**Correct Answer: A**

---

**Q150.** Which is true about Type 1 vs Type 2?
- A) Type 1 runs on hardware, Type 2 runs on host OS
- B) Type 1 has higher performance than Type 2
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

## Section E: Docker & Containerization (Q151–Q200)

**Q151.** Docker is an open platform for:
- A) Developing applications
- B) Shipping applications
- C) Running applications
- D) All of the above

**Correct Answer: D**

---

**Q152.** Docker is written in:
- A) Python
- B) Java
- C) Go language
- D) C++

**Correct Answer: C**

---

**Q153.** Go language was developed by:
- A) Microsoft
- B) Apple
- C) Google
- D) Amazon

**Correct Answer: C**

---

**Q154.** Docker is a ______ platform.
- A) Virtualization
- B) Containerization
- C) Networking
- D) Storage

**Correct Answer: B**

---

**Q155.** Docker enables you to separate ______ from ______.
- A) Hardware from software
- B) Applications from infrastructure
- C) Users from servers
- D) Networks from cables

**Correct Answer: B**

---

**Q156.** Standard shipping containers revolutionized freight transport after:
- A) 1940
- B) 1950
- C) 1960
- D) 1970

**Correct Answer: C**

---

**Q157.** Docker containers provide:
- A) Portability for applications
- B) Standard format across environments
- C) All dependencies included
- D) All of the above

**Correct Answer: D**

---

**Q158.** Which of the following is NOT a characteristic of Docker containers?
- A) Portability
- B) Workload isolation
- C) Requires separate OS for each container
- D) Standard format

**Correct Answer: C**

---

**Q159.** Docker is referred to as a ______ for code.
- A) Shipping container
- B) Physical server
- C) Network cable
- D) Hard drive

**Correct Answer: A**

---

**Q160.** In VMs, blocked memory:
- A) Can be allotted to a new VM
- B) Cannot be allotted to a new VM
- C) Is always available
- D) Does not exist

**Correct Answer: B**

---

**Q161.** In Docker, unused memory:
- A) Cannot be used
- B) Can be allotted to a new container
- C) Is always wasted
- D) Does not exist

**Correct Answer: B**

---

**Q162.** Containers are:
- A) Heavier than VMs
- B) Much lighter and faster than VMs
- C) Same weight as VMs
- D) Not comparable to VMs

**Correct Answer: B**

---

**Q163.** A container always runs on top of:
- A) Another container
- B) The host OS
- C) A virtual machine
- D) Physical hardware directly

**Correct Answer: B**

---

**Q164.** Containers are isolated but share:
- A) OS, binaries, and libraries
- B) Only the OS
- C) Nothing
- D) Only hardware

**Correct Answer: A**

---

**Q165.** Containers start in:
- A) Minutes
- B) Hours
- C) Seconds
- D) Days

**Correct Answer: C**

---

**Q166.** Virtual Machines start in:
- A) Seconds
- B) Minutes
- C) Milliseconds
- D) Instantly

**Correct Answer: B**

---

**Q167.** Container size is measured in:
- A) GBs
- B) TBs
- C) MBs
- D) PBs

**Correct Answer: C**

---

**Q168.** VM size is measured in:
- A) MBs
- B) KBs
- C) GBs
- D) Bytes

**Correct Answer: C**

---

**Q169.** Container provides ______ isolation.
- A) Full hardware-level
- B) Process-level
- C) Network-level
- D) No isolation

**Correct Answer: B**

---

**Q170.** VM provides ______ isolation.
- A) Process-level
- B) No isolation
- C) Full hardware-level
- D) Application-level only

**Correct Answer: C**

---

**Q171.** Container performance is:
- A) Very slow
- B) Near-native
- C) Same as VM
- D) Not measurable

**Correct Answer: B**

---

**Q172.** Which is an example of container technology?
- A) Docker
- B) Kubernetes
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q173.** Which is an example of VM technology?
- A) Docker
- B) VMware
- C) Kubernetes
- D) Go language

**Correct Answer: B**

---

**Q174.** Each VM has its:
- A) Shared OS with other VMs
- B) Own full OS
- C) No OS
- D) Only command line

**Correct Answer: B**

---

**Q175.** Containers share:
- A) Each has its own OS kernel
- B) Host OS kernel
- C) No OS
- D) Multiple OS kernels

**Correct Answer: B**

---

**Q176.** `docker --version` is used to:
- A) Delete Docker
- B) Get currently installed Docker version
- C) Install Docker
- D) Update Docker

**Correct Answer: B**

---

**Q177.** `docker pull` is used to:
- A) Push images to Docker Hub
- B) Pull images from Docker Hub
- C) Delete images
- D) List images

**Correct Answer: B**

---

**Q178.** Docker images are pulled from:
- A) github.com
- B) hub.docker.com
- C) gitlab.com
- D) docker.org

**Correct Answer: B**

---

**Q179.** `docker images` command:
- A) Lists all locally stored Docker images
- B) Deletes all images
- C) Creates new images
- D) Uploads images

**Correct Answer: A**

---

**Q180.** `docker run -it -d <image name>` is used to:
- A) Delete a container
- B) Create a container from an image
- C) Stop a container
- D) List containers

**Correct Answer: B**

---

**Q181.** `docker ps` lists:
- A) All containers
- B) Only running containers
- C) Only stopped containers
- D) Only exited containers

**Correct Answer: B**

---

**Q182.** `docker ps -a` shows:
- A) Only running containers
- B) Only exited containers
- C) All running and exited containers
- D) No containers

**Correct Answer: C**

---

**Q183.** `docker exec -it <container id> bash` is used to:
- A) Stop a container
- B) Delete a container
- C) Access a running container
- D) Create a new container

**Correct Answer: C**

---

**Q184.** `docker stop` gives the container time to:
- A) Start up
- B) Shutdown gracefully
- C) Update
- D) Install software

**Correct Answer: B**

---

**Q185.** `docker kill` stops execution:
- A) Gracefully
- B) After a delay
- C) Immediately
- D) Never

**Correct Answer: C**

---

**Q186.** The difference between `docker stop` and `docker kill` is:
- A) stop is graceful, kill is immediate
- B) Both are same
- C) kill is graceful, stop is immediate
- D) Neither stops the container

**Correct Answer: A**

---

**Q187.** `docker commit` creates:
- A) A new container
- B) A new image of an edited container
- C) A new server
- D) A new network

**Correct Answer: B**

---

**Q188.** `docker login` is used to login to:
- A) GitHub
- B) Docker Hub repository
- C) Google Cloud
- D) AWS

**Correct Answer: B**

---

**Q189.** Which Docker command would you use to see all containers including stopped ones?
- A) docker ps
- B) docker ps -a
- C) docker images
- D) docker run

**Correct Answer: B**

---

**Q190.** Which command creates a container from an image?
- A) docker pull
- B) docker push
- C) docker run
- D) docker commit

**Correct Answer: C**

---

**Q191.** Before containers became popular, ______ were used.
- A) Physical servers only
- B) Virtual Machines (VMs)
- C) Mainframes only
- D) Supercomputers

**Correct Answer: B**

---

**Q192.** Docker simplifies and accelerates:
- A) Hardware installation
- B) Workflow
- C) Cable management
- D) Power supply

**Correct Answer: B**

---

**Q193.** Which of the following is true about containers?
- A) They are lightweight
- B) They start in seconds
- C) They share host OS kernel
- D) All of the above

**Correct Answer: D**

---

**Q194.** Which of the following is true about VMs?
- A) Each has its own full OS
- B) They are heavy (GBs)
- C) They start in minutes
- D) All of the above

**Correct Answer: D**

---

**Q195.** VMM stands for:
- A) Virtual Machine Manager
- B) Virtual Machine Monitor
- C) Both A & B are used
- D) None of the given

**Correct Answer: C**

---

**Q196.** Which of the following is NOT a Docker command?
- A) docker pull
- B) docker compile
- C) docker run
- D) docker stop

**Correct Answer: B**

---

**Q197.** Docker containers provide ______ isolation at runtime.
- A) Hardware
- B) Workload
- C) Physical
- D) No

**Correct Answer: B**

---

**Q198.** VDI stands for:
- A) Virtual Desktop Infrastructure
- B) Virtual Data Integration
- C) Virtualized Device Interface
- D) Virtual Disk Image

**Correct Answer: A**

---

**Q199.** Which is more resource efficient?
- A) Virtual Machine
- B) Container
- C) Physical Server
- D) All are same

**Correct Answer: B**

---

**Q200.** The correct order of virtualization levels from lowest to highest is:
- A) ISA → HAL → OS → Library → Application
- B) Application → Library → OS → HAL → ISA
- C) HAL → ISA → Library → OS → Application
- D) OS → HAL → ISA → Application → Library

**Correct Answer: A**

---

> 🎯 **Quick Revision Before Exam:**
> - **7 Types:** Desktop, Server, Storage, Network, Application, Data, OS
> - **5 Levels:** ISA (BIRD/Dynamo) → HAL (VMware) → OS (FVM) → Library (WINE/vCUDA) → Application (JVM/CLR)
> - **Type 1 Examples:** ESXi, Hyper-V, XenServer, Oracle VM
> - **Type 2 Examples:** VirtualBox, VMware Workstation, Virtual PC
> - **Docker Commands:** version, pull, images, run, ps, ps -a, exec, stop, kill, commit, login
> - **Container vs VM:** Seconds vs Minutes | MBs vs GBs | Shared OS vs Own OS | Process vs Hardware isolation

