# Unit 5 — CI/CD with Jenkins

> **Subject:** CCBD (Cloud Computing & Basics of DevOps) | **Code:** 2101CS742

---

## 1. DevOps — Introduction

- **DevOps** promotes **collaboration between Development (Dev) and Operations (Ops)** teams to deploy code to production faster in an automated & repeatable way.
- Combines cultural philosophies, practices and tools — increases chances of delivering **quality with high velocity**.
- A single team handles the **entire application lifecycle** — development → testing → deployment → operations.
- Reduces disconnection between developers, QA engineers, and system administrators.

### DevOps Key Points:
- Focus on **collaboration and communication** between Dev and Ops
- Activities occur **in tandem** (parallel), not serially
- Developers **own application's reliability and performance**
- Leaders must encourage a **DevOps culture**

---

## 2. What is CI/CD?

- **CI/CD** = Continuous Integration and Continuous Deployment (or Delivery).
- Core aspect of DevOps that **automates multiple stages** in the DevOps workflow.
- Considered the **heartbeat** of a well-oiled DevOps process.
- Enables automation and **high-velocity software delivery** with improved reliability.

### CI/CD Pipeline
- A series of **interconnected steps**: code commit → testing → staging → deployment testing → production deployment.
- Most stages are **automated** to create seamless software delivery.

### Core Components of CI/CD Pipeline:
| Component | Purpose |
|---|---|
| **Build Scripts** | Automate tasks to build a release |
| **Infrastructure Elements** | Dev environments, platforms, hosting services |
| **Test Elements** | Scripts to automate testing |
| **Release Elements** | Automate the release process |
| **Validation Elements** | Automate testing before release |

---

## 3. Continuous Integration (CI)

- Practice of **integrating code changes** from developers into a **shared repository**, several times a day.
- **Automatic build and test** of code changes when committed.
- Test suites execute **automatically** → bugs discovered close to the source.

### How CI Works:
1. Developers **commit code** to shared repository regularly
2. **Version control** system is monitored
3. When commit detected → **build triggered automatically**
4. If build is **not green** (fails) → developers notified immediately

### CI Benefits:
- **Improved quality** and velocity
- **Near real-time feedback** from developers and stakeholders
- **Increased visibility** within team and organization

### CI Tools:
- Version control: **Git, Mercurial**
- CI servers: **Jenkins, TeamCity**

---

## 4. Continuous Deployment

- Automates the process of **releasing applications** to production.
- After code is successfully integrated → system **automatically deploys** new version to production.
- New versions released **as quickly as possible** after integration and testing.

### Benefits:
- **Faster release cycles**
- Culture of **continuous improvement**
- **Improved productivity**

---

## 5. Continuous Delivery (CD)

- Software **release automation** process — enables faster deployment of changes.
- Extension of CI focused on **automating the software delivery** process.
- Code base should always be in a **ready-to-ship state** at any time.
- Automates steps between **code commit and production decision**.

### CD Benefits:
- **Faster time to market**
- **Reduced deployment failures**
- Improved visibility and collaboration between **dev, ops, and IT**
- **Improved productivity** and efficiency
- Developers have more time for **creative tasks**

### CD Tools:
- Deployment automation: **Chef, Puppet**

---

## 6. Continuous Monitoring (CM)

- Process of routinely scanning for performance degradations.
- Monitors: **Application Performance, Security, Compliance**.

### CM Benefits:
- Improved security through automation
- **Early detection** of performance issues
- **Reduced downtime**
- Better business performance, improved user experience
- Increased **clarity and collaboration**

---

## 7. CI vs CD — Key Differences

| Feature | CI (Continuous Integration) | CD (Continuous Delivery/Deployment) |
|---|---|---|
| **Focus** | Integrating & testing code changes | Automating deployment to production |
| **Stage** | Earlier step in process | Latter step in process |
| **Goal** | Software-defined cycle, catch bugs early | Fully automated release process |
| **Tools** | Git, Jenkins, TeamCity | Chef, Puppet, Jenkins |

### How CI/CD Relates to DevOps:
- CI/CD **supports DevOps** teams.
- Enables **automation across development lifecycle**.
- Rapidly **validates and delivers** applications to end-users.
- DevOps requires: automation, programmable infrastructure, iterative development, cross-functional teams.

---

## 8. Traditional Way vs CI/CD

| Traditional | CI/CD |
|---|---|
| All code merged in **single integration** at end | Code merged **frequently** (several times/day) |
| Bugs found **late** | Bugs caught **early** |
| **Manual** testing and deployment | **Automated** testing and deployment |
| **Slow** release cycles | **Fast** release cycles |
| High risk of **integration issues** | Low risk with **continuous feedback** |

---

## 9. What is Jenkins?

- **Open-source automation server** written in **Java**.
- Used to implement **CI/CD pipelines**.
- Supports building, deploying, and automating software development.
- Has **1000+ plugins** to extend functionality.
- **Free of cost** and **portable** (runs on all major platforms since built with Java).

### Why Use Jenkins for CI?
Before Jenkins → had to test complete code before identifying bugs → coordination was tedious.

### Jenkins CI Architecture (How it Works):
1. Changes **committed** to source code repository
2. Jenkins CI server **pulls** the most recent update
3. **Executable file** developed by Build Server
4. If fails → **feedback sent**
5. Build application **deployed to test server**
6. Developer alerted if **failure**
7. Tested application **deployed on production server**

### Advantages of Jenkins:
- **Open-source** with great community support
- **Easy to install**
- **1000+ plugins** available
- **Free of cost**
- Built with **Java** → portable to all major platforms

### Jenkins Use Cases:
- CI/CD
- Automated testing
- Continuous deployment
- Build automation
- Code analysis

---

## 10. Jenkins Pipeline

- Pipeline adds powerful **automation tools** onto Jenkins.
- A sequence of **stages** that define steps to build, test, and deploy code changes.
- Supports simple CI to comprehensive **CD pipelines**.

### How to Create CI/CD Pipeline:
1. **Download and Install** Jenkins
2. **Start and Configure** Jenkins
3. **Create CI/CD Pipeline** in Jenkins

### Creating Pipeline:
- Navigate to **"New Item"** → select **"Pipeline"** → name it → click "OK"

### Triggering Builds Automatically (3 Ways):
| Method | Description |
|---|---|
| **Polling SCM** | Jenkins regularly checks SCM for changes, triggers build if found |
| **Webhooks** | SCM sends notification to Jenkins on new commit (can integrate with Slack) |
| **Scheduled Builds** | Schedule builds at specific intervals using **cron syntax** |

### Managing and Monitoring Builds:
- **Console output** — troubleshoot build issues
- **Build history** — identify patterns or recurring issues
- **Notifications** — email or Slack messages for build results

---

## 11. Freestyle vs Pipeline Projects

| Feature | Freestyle Project | Pipeline Project |
|---|---|---|
| **Complexity** | Simple, GUI-based | Complex, code-based (Jenkinsfile) |
| **Flexibility** | Limited | Highly flexible |
| **Version Control** | Not easily versioned | Can be stored in SCM |
| **Stages** | No built-in stages | Multiple stages supported |
| **Best For** | Simple tasks | Complex CI/CD workflows |

---

## 12. Jenkins Plugins and Extensions

- Plugins are small, independent programs that **extend Jenkins** functionality.
- Over **1,900+ plugins** available and growing.
- Install from **Jenkins Update Centre** (centralized repository maintained by Jenkins community).
- Navigate: **Dashboard → Manage Jenkins → Plugins → Plugin Manager**.

### Benefits of Jenkins Plugins:
- **Automate tasks** — reduce manual effort
- **Simplify testing** — automate testing and analysis
- **Reduce human error** — automation reduces mistakes
- **Increase agility** — easier to release changes and fix bugs

### Top Jenkins Plugins:

| Plugin | Purpose |
|---|---|
| **Git Plugin** | Git operations (pull, fetch, checkout, branch, merge, push) |
| **Jira Plugin** | Integrate with Atlassian Jira Software |
| **Kubernetes Plugin** | Automate scaling of Jenkins slaves in K8s environment |
| **SonarQube Plugin** | Identify bugs, vulnerabilities, ensure code quality |
| **Docker Plugin** | Spawn Docker containers, run builds automatically |
| **Maven Integration** | Maven build jobs |
| **Amazon EC2 Plugin** | Initiate/terminate agents on EC2 |
| **Build Pipeline Plugin** | View upstream/downstream connected jobs |
| **Blue Ocean Plugin** | Enhanced UI, improved visibility |
| **Mailer Plugin** | Email notifications for build results |

---

## 13. Jenkins Test Automation

- Automating **test cases in CI/CD pipelines** using Jenkins.
- Integrates with various **testing tools and frameworks**.
- Runs tests like **unit, integration, and regression** tests.

### When to Use Jenkins for Test Automation:
| Scenario | Why Jenkins |
|---|---|
| **Frequent Code Changes** | Ensures every change passes automated testing |
| **Continuous Integration** | Code merged several times/day, catch bugs early |
| **Cross-platform Testing** | Automate tests across multiple environments |
| **Scaling Test Automation** | Integrate with **Selenium or Appium** for functional testing |

---

## 14. Jenkins Security

- Jenkins interacts with **multiple servers and components** → security is crucial.
- **Jenkins Security Advisory** = list of security issues identified periodically (includes vulnerability description, risks, severities, workarounds).

### Security Best Practices:

| Practice | Description |
|---|---|
| **Access Control** | Authenticate users, set appropriate permissions |
| **Security Realm** | Determines users, passwords, groups |
| **Authorization** | Who has access to what |
| **CSRF Protection** | Prevent Cross-Site Request Forgery attacks |
| **XSS Prevention** | Markup Formatter filters unsafe HTML metacharacters |
| **Controller Isolation** | Control commands executed during build |
| **Environment Variables** | Sanitize to prevent risks |

### Environment Variable Plugins:
- **Safe Batch Environment Filter** — fails build if Batch metacharacters found
- **Generic Build Step Environment Filters** — standard filtering
- **Pipeline: Keep Environment Step** — detects unused env variables

### Security Measures:
| Measure | Description |
|---|---|
| **Enable Global Security** | Configure security realms and authorization strategies |
| **Authentication** | Jenkins supports **LDAP, Active Directory, custom DB** |
| **Authorization** | Limit permissions based on roles; plugins like **Role-based Authorization Strategy** |
| **Secure Passwords** | Store API keys, SSH keys securely |
| **OWASP Plugin** | Sanitize rich-text inputs |
| **Regular Updates** | Patch security vulnerabilities |
| **Use HTTPS** | Encrypt traffic between Jenkins and clients |
| **Build Parameters Safety** | Mask sensitive parameters in console log |
| **Network Access Control** | Limit access to trusted networks |

### Access Control Axes:
1. **Security Realm** — determines users, passwords, groups
2. **Authorization Strategy** — determines who has access to what

### Authorization Options:
- Anyone can do anything
- Legacy mode
- Logged-in users can do anything
- **Matrix-based security** (fine-grained permissions)

---

## 15. Jenkins Administration

| Task | Description |
|---|---|
| **Security** | Configure authentication, authorization, accounting |
| **Monitoring** | Monitor environment, receive alerts for updates |
| **Maintenance** | Backup/restore Jenkins, manage system services |
| **Configuration** | Global settings, paths, reverse proxy |
| **User Management** | Create, modify, set user access |
| **Notifications** | Configure alerts for failing/unstable jobs |
| **Nodes** | Manage nodes/agents, set executors per build node |

- Managed through **Manage Jenkins** section of dashboard.
- Dashboard includes tiles: **System Configuration, Security, Status Information**.

---

## 📋 Abbreviation Table

| Short Form | Full Form |
|---|---|
| API | Application Programming Interface |
| CD | Continuous Delivery / Continuous Deployment |
| CI | Continuous Integration |
| CI/CD | Continuous Integration / Continuous Deployment |
| CM | Continuous Monitoring |
| CSRF | Cross-Site Request Forgery |
| DevOps | Development + Operations |
| EC2 | Elastic Compute Cloud |
| GUI | Graphical User Interface |
| HTTPS | Hypertext Transfer Protocol Secure |
| K8s | Kubernetes |
| LDAP | Lightweight Directory Access Protocol |
| OWASP | Open Web Application Security Project |
| QA | Quality Assurance |
| SCM | Source Control Management |
| SSH | Secure Shell |
| UI | User Interface |
| XSS | Cross-Site Scripting |

---

---

# 📝 MCQ Bank — Unit 5: CI/CD with Jenkins (200 Questions)

---

## Section A: DevOps & CI/CD Basics (Q1–Q55)

**Q1.** DevOps promotes collaboration between:
- A) Hardware and Software teams
- B) Development and Operations teams
- C) Marketing and Sales teams
- D) HR and Finance teams

**Correct Answer: B**

---

**Q2.** DevOps combines:
- A) Cultural philosophies, practices and tools
- B) Only hardware
- C) Only documentation
- D) Only testing

**Correct Answer: A**

---

**Q3.** CI/CD stands for:
- A) Cloud Integration / Cloud Deployment
- B) Continuous Integration / Continuous Deployment
- C) Computer Interface / Computer Design
- D) Central Integration / Central Distribution

**Correct Answer: B**

---

**Q4.** CI/CD is considered the ______ of DevOps.
- A) Tail
- B) Heartbeat
- C) Footer
- D) Background

**Correct Answer: B**

---

**Q5.** A CI/CD pipeline is a series of:
- A) Physical cables
- B) Interconnected steps from code commit to deployment
- C) Random processes
- D) Manual tasks only

**Correct Answer: B**

---

**Q6.** How many core components of CI/CD pipeline are there?
- A) 3
- B) 4
- C) 5
- D) 6

**Correct Answer: C**

---

**Q7.** Build Scripts automate tasks to:
- A) Delete code
- B) Build a release
- C) Format disk
- D) Install OS

**Correct Answer: B**

---

**Q8.** CI focuses on:
- A) Deployment only
- B) Integrating and testing code changes
- C) Only documentation
- D) Only design

**Correct Answer: B**

---

**Q9.** CD focuses on:
- A) Writing code only
- B) Automating deployment to production
- C) Manual testing
- D) Physical installation

**Correct Answer: B**

---

**Q10.** CI is the ______ step, CD is the ______ step.
- A) Latter, Earlier
- B) Earlier, Latter
- C) Same, Same
- D) Last, First

**Correct Answer: B**

---

**Q11.** In CI, developers commit code to:
- A) Personal USB drive
- B) Shared repository
- C) Paper documents
- D) Physical server

**Correct Answer: B**

---

**Q12.** In CI, when commit is detected:
- A) Nothing happens
- B) Build triggered automatically
- C) System shuts down
- D) Code is deleted

**Correct Answer: B**

---

**Q13.** If build is not green (fails), developers are:
- A) Ignored
- B) Notified immediately
- C) Rewarded
- D) Fired

**Correct Answer: B**

---

**Q14.** CI Benefits include:
- A) Improved quality and velocity
- B) Near real-time feedback
- C) Increased visibility
- D) All of the above

**Correct Answer: D**

---

**Q15.** Git and Mercurial are examples of:
- A) Deployment tools
- B) Version control systems
- C) Databases
- D) Operating systems

**Correct Answer: B**

---

**Q16.** Jenkins and TeamCity are examples of:
- A) Databases
- B) CI servers
- C) Operating systems
- D) Browsers

**Correct Answer: B**

---

**Q17.** Chef and Puppet are used for:
- A) CI
- B) CD (deployment automation)
- C) Code writing
- D) Hardware repair

**Correct Answer: B**

---

**Q18.** Continuous Deployment automatically deploys after:
- A) Manual approval only
- B) Successful integration and testing
- C) No testing
- D) Random selection

**Correct Answer: B**

---

**Q19.** Benefits of Continuous Deployment include:
- A) Faster release cycles
- B) Culture of continuous improvement
- C) Improved productivity
- D) All of the above

**Correct Answer: D**

---

**Q20.** Continuous Delivery ensures code is always in:
- A) Broken state
- B) Ready-to-ship state
- C) Deleted state
- D) Encrypted state

**Correct Answer: B**

---

**Q21.** CD Benefits include:
- A) Faster time to market
- B) Reduced deployment failures
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q22.** CM stands for:
- A) Cloud Management
- B) Continuous Monitoring
- C) Computer Module
- D) Central Manager

**Correct Answer: B**

---

**Q23.** CM monitors:
- A) Application Performance
- B) Security
- C) Compliance
- D) All of the above

**Correct Answer: D**

---

**Q24.** CM Benefits include:
- A) Improved security
- B) Early detection of performance issues
- C) Reduced downtime
- D) All of the above

**Correct Answer: D**

---

**Q25.** In Traditional way, all code is merged in:
- A) Multiple small integrations
- B) Single integration at the end
- C) Continuous integration
- D) No integration

**Correct Answer: B**

---

**Q26.** With CI/CD, bugs are caught:
- A) Very late
- B) Early
- C) Never
- D) After release only

**Correct Answer: B**

---

**Q27.** DevOps requires activities to occur:
- A) Serially (one after another)
- B) In tandem (parallel)
- C) Never
- D) Randomly

**Correct Answer: B**

---

**Q28.** In DevOps, developers own:
- A) Only code writing
- B) Application's reliability and performance
- C) Only testing
- D) Only deployment

**Correct Answer: B**

---

**Q29.** DevOps helps reduce disconnection between:
- A) Developers, QA engineers, system administrators
- B) Only managers
- C) Only clients
- D) Only designers

**Correct Answer: A**

---

**Q30.** QA stands for:
- A) Quality Assurance
- B) Quick Access
- C) Quantum Analysis
- D) Query Application

**Correct Answer: A**

---

**Q31.** Which is NOT a core component of CI/CD pipeline?
- A) Build Scripts
- B) Test Elements
- C) Physical Hardware Installation
- D) Release Elements

**Correct Answer: C**

---

**Q32.** CI/CD enables:
- A) Manual-only deployment
- B) Automation and high-velocity software delivery
- C) Slow delivery
- D) No deployment

**Correct Answer: B**

---

**Q33.** Test elements enable developers to:
- A) Delete code
- B) Create scripts to automate testing
- C) Write documentation only
- D) Install hardware

**Correct Answer: B**

---

**Q34.** Validation elements automate testing:
- A) After release
- B) Before release
- C) Never
- D) Randomly

**Correct Answer: B**

---

**Q35.** SCM stands for:
- A) Source Control Management
- B) System Configuration Module
- C) Software Cloud Manager
- D) Server Computing Method

**Correct Answer: A**

---

**Q36.** In the traditional way, bugs are found:
- A) Early
- B) Late
- C) Never
- D) Instantly

**Correct Answer: B**

---

**Q37.** CI/CD supports which team efforts?
- A) DevOps
- B) Only marketing
- C) Only sales
- D) Only HR

**Correct Answer: A**

---

**Q38.** Continuous Delivery automates steps between:
- A) Code writing and documentation
- B) Code commit and production decision
- C) Design and planning
- D) Nothing

**Correct Answer: B**

---

**Q39.** DevOps approach merges skills of:
- A) Development with Operations
- B) Marketing with Sales
- C) HR with Finance
- D) Design with Art

**Correct Answer: A**

---

**Q40.** CI/CD pipeline steps in order are:
- A) Deploy → Test → Commit
- B) Commit → Testing → Staging → Deployment Testing → Production
- C) Production → Commit → Test
- D) Random order

**Correct Answer: B**

---

**Q41.** Which is NOT a CI benefit?
- A) Improved quality
- B) Slower delivery
- C) Near real-time feedback
- D) Increased visibility

**Correct Answer: B**

---

**Q42.** Infrastructure elements include:
- A) Development environments
- B) Platforms and hosting services
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q43.** Release elements allow for automation of:
- A) Testing only
- B) Release process
- C) Design only
- D) Nothing

**Correct Answer: B**

---

**Q44.** Continuous Deployment releases new versions:
- A) As slowly as possible
- B) As quickly as possible after testing
- C) Never
- D) Only annually

**Correct Answer: B**

---

**Q45.** CD allows teams to deploy applications into:
- A) Personal computers only
- B) Production-like environments
- C) Paper documents
- D) Physical warehouses

**Correct Answer: B**

---

**Q46.** CD changes deployments from:
- A) Frequent to infrequent
- B) Infrequent, big, risky to frequent, small, safe
- C) Small to big
- D) Safe to risky

**Correct Answer: B**

---

**Q47.** DevOps requires establishing:
- A) Single-function teams
- B) Cross-functional teams
- C) No teams
- D) Competing teams

**Correct Answer: B**

---

**Q48.** CI/CD automates:
- A) Only one stage
- B) Multiple stages in DevOps workflow
- C) No stages
- D) Only manual stages

**Correct Answer: B**

---

**Q49.** The code integration process is the ______ of CI/CD pipeline.
- A) End
- B) Heart
- C) Footer
- D) Side

**Correct Answer: B**

---

**Q50.** CI/CD testing includes:
- A) Unit tests
- B) Integration tests
- C) End-to-end tests
- D) All of the above

**Correct Answer: D**

---

**Q51.** Automated monitoring ensures:
- A) Errors are never found
- B) Application is running correctly and errors are identified quickly
- C) System crashes
- D) No monitoring happens

**Correct Answer: B**

---

**Q52.** DevOps lifecycle is handled by:
- A) Multiple separate teams
- B) Single team (development to operations)
- C) Only management
- D) Only clients

**Correct Answer: B**

---

**Q53.** CI involves testing each code change:
- A) Manually
- B) Automatically
- C) Never
- D) Only once

**Correct Answer: B**

---

**Q54.** Continuous Monitoring scans for:
- A) Performance degradations
- B) Performance improvements only
- C) Nothing
- D) Hardware damage only

**Correct Answer: A**

---

**Q55.** CI/CD requires which of these?
- A) Automation
- B) Version control
- C) Testing
- D) All of the above

**Correct Answer: D**

---

## Section B: Jenkins Basics & Pipeline (Q56–Q110)

**Q56.** Jenkins is written in:
- A) Python
- B) Java
- C) C++
- D) Ruby

**Correct Answer: B**

---

**Q57.** Jenkins is:
- A) Proprietary software
- B) Open-source automation server
- C) Hardware device
- D) Operating system

**Correct Answer: B**

---

**Q58.** Jenkins has over ______ plugins.
- A) 100
- B) 500
- C) 1000+
- D) 50

**Correct Answer: C**

---

**Q59.** Jenkins is:
- A) Expensive
- B) Free of cost
- C) Subscription-based
- D) Pay per use

**Correct Answer: B**

---

**Q60.** Jenkins is portable because it is built with:
- A) C
- B) Python
- C) Java
- D) PHP

**Correct Answer: C**

---

**Q61.** Which is NOT an advantage of Jenkins?
- A) Open-source
- B) Easy to install
- C) Requires paid license
- D) 1000+ plugins

**Correct Answer: C**

---

**Q62.** Jenkins Use Cases include:
- A) CI/CD and Automated testing
- B) Build automation and Code analysis
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q63.** In Jenkins CI, first step is:
- A) Deploy to production
- B) Changes committed to source code repository
- C) System shuts down
- D) Manual testing

**Correct Answer: B**

---

**Q64.** Jenkins CI server:
- A) Ignores code changes
- B) Pulls most recent update
- C) Deletes old code
- D) Formats disk

**Correct Answer: B**

---

**Q65.** If Jenkins build fails:
- A) No notification
- B) Feedback is sent to developer
- C) System celebrates
- D) Code is deployed anyway

**Correct Answer: B**

---

**Q66.** Jenkins Pipeline is:
- A) Physical pipe
- B) Sequence of stages for build, test, deploy
- C) Network cable
- D) Storage device

**Correct Answer: B**

---

**Q67.** To create new pipeline in Jenkins, navigate to:
- A) Settings
- B) "New Item" → select "Pipeline"
- C) Control Panel
- D) File Manager

**Correct Answer: B**

---

**Q68.** How many ways to trigger builds automatically?
- A) 1
- B) 2
- C) 3
- D) 4

**Correct Answer: C**

---

**Q69.** Three ways to trigger builds are:
- A) Polling SCM, Webhooks, Scheduled Builds
- B) Email, Phone, Fax
- C) Print, Copy, Paste
- D) Read, Write, Delete

**Correct Answer: A**

---

**Q70.** Polling SCM means Jenkins:
- A) Ignores SCM
- B) Regularly checks SCM for changes
- C) Deletes SCM
- D) Never checks

**Correct Answer: B**

---

**Q71.** Webhooks trigger build when:
- A) Timer expires
- B) SCM sends notification on new commit
- C) Manually clicked
- D) Power is turned on

**Correct Answer: B**

---

**Q72.** Scheduled Builds use:
- A) Random timing
- B) Cron syntax
- C) Manual clicks
- D) No scheduling

**Correct Answer: B**

---

**Q73.** Build monitoring tools include:
- A) Console output
- B) Build history
- C) Notifications
- D) All of the above

**Correct Answer: D**

---

**Q74.** Console output is used to:
- A) Deploy code
- B) Troubleshoot build issues
- C) Write code
- D) Design UI

**Correct Answer: B**

---

**Q75.** Build history helps identify:
- A) Patterns or recurring issues
- B) New features
- C) User profiles
- D) Physical location

**Correct Answer: A**

---

**Q76.** Notifications can be sent via:
- A) Email
- B) Slack messages
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q77.** Freestyle Project is:
- A) Complex, code-based
- B) Simple, GUI-based
- C) Only for experts
- D) Deprecated

**Correct Answer: B**

---

**Q78.** Pipeline Project is:
- A) Simple, GUI-based
- B) Complex, code-based (Jenkinsfile)
- C) Only for beginners
- D) No coding needed

**Correct Answer: B**

---

**Q79.** Pipeline Project can be stored in:
- A) Physical locker
- B) SCM (version controlled)
- C) Paper files
- D) USB only

**Correct Answer: B**

---

**Q80.** How many steps to create CI/CD Pipeline in Jenkins?
- A) 1
- B) 2
- C) 3
- D) 4

**Correct Answer: C**

---

**Q81.** Three steps to create pipeline are:
- A) Download/Install, Start/Configure, Create Pipeline
- B) Delete, Format, Reinstall
- C) Read, Write, Execute
- D) Plan, Design, Deploy

**Correct Answer: A**

---

**Q82.** Jenkins Continuous Integration tests code:
- A) Only once
- B) Repeatedly after every commit
- C) Never
- D) Only at the end

**Correct Answer: B**

---

**Q83.** Before Jenkins, developers had to:
- A) Test complete code before finding bugs
- B) Never test
- C) Write no code
- D) Only design

**Correct Answer: A**

---

**Q84.** Before Jenkins, coordination was:
- A) Easy and fast
- B) Tedious and time-consuming
- C) Not needed
- D) Automated

**Correct Answer: B**

---

**Q85.** Webhooks can integrate with:
- A) Slack
- B) Other collaboration tools
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q86.** Polling SCM is critical for deploying:
- A) New features only
- B) Hotfixes on production
- C) Documentation
- D) Hardware

**Correct Answer: B**

---

**Q87.** Pipeline Project supports:
- A) No stages
- B) Multiple stages
- C) Only one stage
- D) Physical stages

**Correct Answer: B**

---

**Q88.** Freestyle Project is best for:
- A) Complex CI/CD workflows
- B) Simple tasks
- C) Enterprise applications
- D) Database management

**Correct Answer: B**

---

**Q89.** Pipeline Project is best for:
- A) Simple tasks only
- B) Complex CI/CD workflows
- C) Only documentation
- D) Only design

**Correct Answer: B**

---

**Q90.** Tested application is finally deployed on:
- A) Test server
- B) Production server
- C) Personal computer
- D) USB drive

**Correct Answer: B**

---

**Q91.** Jenkins is fundamentally an:
- A) Database engine
- B) Automation engine
- C) Graphics engine
- D) Physics engine

**Correct Answer: B**

---

**Q92.** Executable file is developed by:
- A) Test Server
- B) Build Server
- C) Database Server
- D) Mail Server

**Correct Answer: B**

---

**Q93.** Pipeline adds ______ tools onto Jenkins.
- A) Manual
- B) Powerful automation
- C) Physical
- D) Design

**Correct Answer: B**

---

**Q94.** GUI stands for:
- A) General User Interface
- B) Graphical User Interface
- C) Global Unified Integration
- D) Grand User Input

**Correct Answer: B**

---

**Q95.** Jenkins supports use cases spanning from:
- A) Simple CI to comprehensive CD pipelines
- B) Only simple tasks
- C) Only complex tasks
- D) No tasks

**Correct Answer: A**

---

**Q96.** Build application is first deployed to:
- A) Production directly
- B) Test server
- C) Public internet
- D) Physical storage

**Correct Answer: B**

---

**Q97.** How many steps in Jenkins CI Architecture?
- A) 3
- B) 5
- C) 7
- D) 9

**Correct Answer: C**

---

**Q98.** Jenkins is:
- A) Only for small projects
- B) Suitable for small-scale to large-scale enterprise projects
- C) Only for large projects
- D) Not suitable for any project

**Correct Answer: B**

---

**Q99.** If plugin doesn't exist, you can:
- A) Give up
- B) Code it and share with community
- C) Buy from store
- D) Wait forever

**Correct Answer: B**

---

**Q100.** Jenkins community provides:
- A) No support
- B) Great community support
- C) Only paid support
- D) Phone support only

**Correct Answer: B**

---

**Q101.** Code analysis is a ______ of Jenkins.
- A) Limitation
- B) Use case
- C) Bug
- D) Error

**Correct Answer: B**

---

**Q102.** Jenkins runs on:
- A) Only Windows
- B) Only Linux
- C) All major platforms
- D) Only Mac

**Correct Answer: C**

---

**Q103.** "Not green" build means:
- A) Success
- B) Failure
- C) Pending
- D) No action

**Correct Answer: B**

---

**Q104.** Version control system is:
- A) Never monitored
- B) Continuously monitored in CI
- C) Deleted after use
- D) Only used once

**Correct Answer: B**

---

**Q105.** Cron syntax is used for:
- A) Coding
- B) Scheduling builds at specific intervals
- C) Designing UI
- D) Writing documentation

**Correct Answer: B**

---

**Q106.** Jenkins makes software delivery:
- A) Slower
- B) Faster and automated
- C) Manual only
- D) Impossible

**Correct Answer: B**

---

**Q107.** Freestyle Project version control is:
- A) Easy to version
- B) Not easily versioned
- C) Automatic
- D) Built-in

**Correct Answer: B**

---

**Q108.** Pipeline Project uses:
- A) GUI clicks only
- B) Jenkinsfile (code-based)
- C) Physical buttons
- D) Voice commands

**Correct Answer: B**

---

**Q109.** Build automation is a ______ of Jenkins.
- A) Weakness
- B) Use case
- C) Problem
- D) Bug

**Correct Answer: B**

---

**Q110.** Jenkins is an ______ tool.
- A) Closed-source
- B) Open-source
- C) Proprietary
- D) Licensed

**Correct Answer: B**

---

## Section C: Jenkins Plugins & Test Automation (Q111–Q145)

**Q111.** How many Jenkins plugins are available?
- A) 100+
- B) 500+
- C) 1,900+
- D) 50

**Correct Answer: C**

---

**Q112.** Jenkins plugins are installed from:
- A) App Store
- B) Jenkins Update Centre
- C) Physical store
- D) Email attachment

**Correct Answer: B**

---

**Q113.** Jenkins Update Centre is maintained by:
- A) Google
- B) Jenkins community
- C) Microsoft
- D) Apple

**Correct Answer: B**

---

**Q114.** To install plugins, navigate to:
- A) Dashboard → Settings
- B) Dashboard → Manage Jenkins → Plugins
- C) File → New
- D) Edit → Preferences

**Correct Answer: B**

---

**Q115.** Benefits of plugins include:
- A) Automate tasks
- B) Simplify testing
- C) Reduce human error and Increase agility
- D) All of the above

**Correct Answer: D**

---

**Q116.** Git Plugin offers:
- A) Database operations
- B) Git operations (pull, fetch, checkout, merge, push)
- C) Email operations
- D) Design operations

**Correct Answer: B**

---

**Q117.** Kubernetes Plugin integrates Jenkins with:
- A) Docker only
- B) Kubernetes
- C) AWS only
- D) Azure only

**Correct Answer: B**

---

**Q118.** SonarQube Plugin helps identify:
- A) Physical damage
- B) Bugs, vulnerabilities, and code duplication
- C) Network issues only
- D) Hardware failures

**Correct Answer: B**

---

**Q119.** Docker Plugin allows:
- A) Physical container shipping
- B) Spawning Docker containers and running builds automatically
- C) Email sending
- D) File printing

**Correct Answer: B**

---

**Q120.** Amazon EC2 Plugin enables Jenkins to:
- A) Buy hardware
- B) Initiate and terminate agents on EC2
- C) Design websites
- D) Write code

**Correct Answer: B**

---

**Q121.** Blue Ocean Plugin enhances:
- A) Hardware performance
- B) User experience and visibility
- C) Network speed
- D) Storage capacity

**Correct Answer: B**

---

**Q122.** Mailer Plugin enables:
- A) Physical mail
- B) Email notifications for build results
- C) Chat messages only
- D) No notifications

**Correct Answer: B**

---

**Q123.** Build Pipeline Plugin shows:
- A) Only current build
- B) Upstream and downstream connected jobs
- C) Only failed builds
- D) Only successful builds

**Correct Answer: B**

---

**Q124.** Jira Plugin integrates with:
- A) Google Docs
- B) Atlassian Jira Software
- C) Microsoft Word
- D) Adobe Photoshop

**Correct Answer: B**

---

**Q125.** Maven Integration Plugin requires JVM to be:
- A) Inferior to Java version
- B) Superior or equal to Java version for Jenkins Controller
- C) Any version
- D) No JVM needed

**Correct Answer: B**

---

**Q126.** Jenkins Test Automation runs tests like:
- A) Unit tests
- B) Integration tests
- C) Regression tests
- D) All of the above

**Correct Answer: D**

---

**Q127.** When should Jenkins be used for test automation?
- A) Frequent code changes
- B) Continuous integration needs
- C) Cross-platform testing
- D) All of the above

**Correct Answer: D**

---

**Q128.** For scaling test automation, Jenkins integrates with:
- A) Selenium or Appium
- B) Photoshop
- C) Word
- D) Excel

**Correct Answer: A**

---

**Q129.** Jenkins testing ensures every code change is:
- A) Ignored
- B) Verified through consistent testing
- C) Deleted
- D) Deployed without testing

**Correct Answer: B**

---

**Q130.** Cross-platform testing means testing on:
- A) Single platform
- B) Different platforms or devices
- C) No platform
- D) Only Windows

**Correct Answer: B**

---

**Q131.** K8s stands for:
- A) Kubernetes
- B) Key8servers
- C) Kernel8systems
- D) Kit8services

**Correct Answer: A**

---

**Q132.** Plugins are:
- A) Large, dependent programs
- B) Small, independent programs that extend functionality
- C) Operating systems
- D) Databases

**Correct Answer: B**

---

**Q133.** Plugins help reduce:
- A) Automation
- B) Human error
- C) Quality
- D) Speed

**Correct Answer: B**

---

**Q134.** Jenkins plugins increase:
- A) Complexity only
- B) Agility of software development teams
- C) Cost
- D) Errors

**Correct Answer: B**

---

**Q135.** Top plugins for productive DevOps include:
- A) Git, Docker, Kubernetes plugins
- B) SonarQube, Jira, EC2 plugins
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q136.** Jenkins Testing is beneficial for CI because:
- A) Code merged once a year
- B) Code merged several times a day, catch bugs early
- C) No merging happens
- D) Only manual testing

**Correct Answer: B**

---

**Q137.** Appium is used for:
- A) Web testing only
- B) Automated functional testing (mobile)
- C) Database testing
- D) Network testing

**Correct Answer: B**

---

**Q138.** Selenium is used for:
- A) Mobile testing only
- B) Automated functional testing (web)
- C) Database testing
- D) Hardware testing

**Correct Answer: B**

---

**Q139.** Jenkins Update Centre is a:
- A) Physical store
- B) Centralized repository of plugins
- C) Email service
- D) Cloud storage

**Correct Answer: B**

---

**Q140.** Plugin installation involves:
- A) Complex coding
- B) Navigating menus and clicking buttons
- C) Physical installation
- D) Hardware changes

**Correct Answer: B**

---

**Q141.** Kubernetes Plugin automates:
- A) Design process
- B) Scaling of Jenkins slaves in K8s environment
- C) Email sending
- D) File printing

**Correct Answer: B**

---

**Q142.** SonarQube ensures:
- A) Code deletion
- B) Code quality before building
- C) Code duplication
- D) System crash

**Correct Answer: B**

---

**Q143.** Docker Plugin runs builds on:
- A) Physical servers only
- B) Docker containers automatically
- C) Paper documents
- D) USB drives

**Correct Answer: B**

---

**Q144.** Regression tests check if:
- A) New code is written
- B) Existing functionality still works after changes
- C) Code is deleted
- D) Hardware is working

**Correct Answer: B**

---

**Q145.** Jenkins test automation improves:
- A) Hardware quality
- B) Software quality
- C) Physical design
- D) Office furniture

**Correct Answer: B**

---

## Section D: Jenkins Security & Administration (Q146–Q200)

**Q146.** Jenkins Security Advisory is a list of:
- A) Feature requests
- B) Security issues identified in Jenkins and plugins
- C) User profiles
- D) Plugin downloads

**Correct Answer: B**

---

**Q147.** CSRF stands for:
- A) Cloud Server Request Form
- B) Cross-Site Request Forgery
- C) Central System Resource Finder
- D) Computer Security Response Function

**Correct Answer: B**

---

**Q148.** XSS stands for:
- A) Cross-Site Scripting
- B) Extra Secure System
- C) eXtended Server Service
- D) XML Standard Security

**Correct Answer: A**

---

**Q149.** Jenkins Markup Formatter protects against:
- A) Hardware failures
- B) XSS attacks (filters unsafe HTML metacharacters)
- C) Network issues
- D) Power failures

**Correct Answer: B**

---

**Q150.** CSRF occurs when user visits:
- A) Safe website
- B) Hostile website or clicks malicious link
- C) Google homepage
- D) Jenkins dashboard

**Correct Answer: B**

---

**Q151.** Access Control in Jenkins is controlled by:
- A) 1 axis
- B) 2 axes (Security Realm + Authorization Strategy)
- C) 3 axes
- D) No axes

**Correct Answer: B**

---

**Q152.** Security Realm determines:
- A) Build status
- B) Users, passwords, and groups
- C) Code quality
- D) Plugin count

**Correct Answer: B**

---

**Q153.** Authorization Strategy determines:
- A) Build speed
- B) Who has access to what
- C) Plugin installation
- D) Code compilation

**Correct Answer: B**

---

**Q154.** Jenkins supports authentication via:
- A) LDAP
- B) Active Directory
- C) Custom user database
- D) All of the above

**Correct Answer: D**

---

**Q155.** LDAP stands for:
- A) Lightweight Directory Access Protocol
- B) Large Data Access Program
- C) Local Domain Authentication Process
- D) Limited Directory Application Protocol

**Correct Answer: A**

---

**Q156.** OWASP stands for:
- A) Open Web Application Security Project
- B) Online Web Access Security Program
- C) Object Web Application Standard Protocol
- D) Open Wireless Access Security Protocol

**Correct Answer: A**

---

**Q157.** OWASP Markup Formatter Plugin sanitizes:
- A) Hardware
- B) Rich-text inputs
- C) Physical documents
- D) Network cables

**Correct Answer: B**

---

**Q158.** Jenkins should serve over:
- A) HTTP only
- B) HTTPS (encrypted traffic)
- C) FTP
- D) SMTP

**Correct Answer: B**

---

**Q159.** HTTPS protects against:
- A) Password snooping
- B) Session cookie hijacking
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q160.** Regular updates help:
- A) Add more bugs
- B) Patch security vulnerabilities
- C) Slow down Jenkins
- D) Delete plugins

**Correct Answer: B**

---

**Q161.** Jenkins provides warnings for:
- A) Good plugins
- B) Known vulnerable plugins
- C) Fast plugins
- D) New plugins

**Correct Answer: B**

---

**Q162.** Sensitive build parameters should be:
- A) Displayed publicly
- B) Masked in Jenkins console log
- C) Shared with everyone
- D) Posted on social media

**Correct Answer: B**

---

**Q163.** Network access to Jenkins should be limited to:
- A) Everyone on internet
- B) Trusted networks only
- C) Random networks
- D) Public WiFi

**Correct Answer: B**

---

**Q164.** Authorization options include:
- A) Anyone can do anything
- B) Matrix-based security
- C) Logged-in users can do anything
- D) All of the above

**Correct Answer: D**

---

**Q165.** Matrix-based security provides:
- A) No permissions
- B) Fine-grained permissions
- C) Full access to everyone
- D) No security

**Correct Answer: B**

---

**Q166.** SSH stands for:
- A) Secure Shell
- B) Standard Server Host
- C) System Security Handler
- D) Simple Server Hook

**Correct Answer: A**

---

**Q167.** API stands for:
- A) Application Programming Interface
- B) Advanced Program Integration
- C) Automated Process Interface
- D) Application Protocol Integration

**Correct Answer: A**

---

**Q168.** Secure Passwords means storing ______ securely.
- A) API keys and SSH keys
- B) Only usernames
- C) Only emails
- D) Nothing

**Correct Answer: A**

---

**Q169.** Safe Batch Environment Filter automatically:
- A) Approves all builds
- B) Fails build steps if Batch metacharacters found
- C) Deletes all variables
- D) Ignores everything

**Correct Answer: B**

---

**Q170.** Controller Isolation controls:
- A) Physical access
- B) Commands executed during build
- C) Network cables
- D) Power supply

**Correct Answer: B**

---

**Q171.** Environment variables can:
- A) Only help
- B) Potentially harm builds by changing script behavior
- C) Never cause issues
- D) Only be positive

**Correct Answer: B**

---

**Q172.** How many environment variable plugins are discussed?
- A) 1
- B) 2
- C) 3
- D) 4

**Correct Answer: C**

---

**Q173.** Jenkins Administration includes:
- A) Security and Monitoring
- B) Maintenance and Configuration
- C) User management, Notifications, Nodes
- D) All of the above

**Correct Answer: D**

---

**Q174.** How many Jenkins administration tasks are discussed?
- A) 3
- B) 5
- C) 7
- D) 9

**Correct Answer: C**

---

**Q175.** Jenkins is managed through:
- A) Command line only
- B) Manage Jenkins section of dashboard
- C) Physical switches
- D) External software only

**Correct Answer: B**

---

**Q176.** Dashboard includes tiles for:
- A) System Configuration
- B) Security
- C) Status Information
- D) All of the above

**Correct Answer: D**

---

**Q177.** Nodes management includes managing:
- A) Agents only
- B) Nodes, agents, and executors per build node
- C) Only servers
- D) Only databases

**Correct Answer: B**

---

**Q178.** Notifications are configured for:
- A) Successful jobs only
- B) Failing and unstable jobs
- C) No jobs
- D) Completed jobs only

**Correct Answer: B**

---

**Q179.** Maintenance includes:
- A) Backup and restore Jenkins
- B) Managing system services
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q180.** User management includes:
- A) Creating users
- B) Modifying users
- C) Setting user access
- D) All of the above

**Correct Answer: D**

---

**Q181.** Authenticating scripted clients uses:
- A) OAuth only
- B) BASIC auth
- C) No authentication
- D) Physical key

**Correct Answer: B**

---

**Q182.** Quick and Simple Security is for running:
- A) Large enterprise
- B) Jenkins with very simple setup (java -jar jenkins.war)
- C) Complex systems
- D) Multiple servers

**Correct Answer: B**

---

**Q183.** Standard Security Setup lets Jenkins run:
- A) No user database
- B) Its own user database with finer-grained access control
- C) External database only
- D) No access control

**Correct Answer: B**

---

**Q184.** Apache frontend for security runs Jenkins:
- A) Standalone
- B) Behind Apache for access control
- C) Without any server
- D) On mobile

**Correct Answer: B**

---

**Q185.** Role-based Authorization Strategy is a:
- A) Built-in feature
- B) Plugin for advanced authorization
- C) Hardware component
- D) Operating system feature

**Correct Answer: B**

---

**Q186.** Jenkins security is crucial because it interacts with:
- A) Single component
- B) Multiple servers and components
- C) No components
- D) Only local files

**Correct Answer: B**

---

**Q187.** Security Advisory includes:
- A) Vulnerability description
- B) Severities and workarounds
- C) Resolutions
- D) All of the above

**Correct Answer: D**

---

**Q188.** Basic authentication mechanism is NOT enough because:
- A) Jenkins is simple
- B) Jenkins has plugin dependency and multi-server interaction
- C) Jenkins is offline
- D) Jenkins needs no security

**Correct Answer: B**

---

**Q189.** HTTPS stands for:
- A) Hypertext Transfer Protocol Secure
- B) High Technology Transfer Protocol Standard
- C) Host Transfer Protocol Service
- D) Hyperlink Text Protocol System

**Correct Answer: A**

---

**Q190.** Enable Global Security is found in:
- A) Build settings
- B) Configure Global Security section of Manage Jenkins
- C) Plugin manager
- D) Dashboard home

**Correct Answer: B**

---

**Q191.** Pipeline: Keep Environment Step detects:
- A) All variables
- B) Unused environment variables in pipelines
- C) Only used variables
- D) No variables

**Correct Answer: B**

---

**Q192.** Generic Build Step Environment Filters use:
- A) Custom implementations
- B) Standard implementations
- C) No implementations
- D) Physical filters

**Correct Answer: B**

---

**Q193.** Monitoring in administration includes:
- A) Receiving alerts for software updates
- B) Receiving alerts for security updates
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q194.** Configuration includes:
- A) Global settings and paths
- B) Reverse proxy configuration
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q195.** Access Control for Builds means users with build access can also:
- A) Only view builds
- B) Create, modify, or delete other builds (by default)
- C) Only run builds
- D) Nothing else

**Correct Answer: B**

---

**Q196.** Legacy mode is a type of:
- A) Build configuration
- B) Authorization option
- C) Plugin
- D) Programming language

**Correct Answer: B**

---

**Q197.** Which is true about Jenkins?
- A) Open-source, Java-based, 1000+ plugins
- B) Free of cost and portable
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q198.** Which is true about CI/CD?
- A) CI integrates code, CD deploys code
- B) Both automate software delivery
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

**Q199.** Which security measure encrypts traffic?
- A) LDAP
- B) HTTPS
- C) Matrix security
- D) Legacy mode

**Correct Answer: B**

---

**Q200.** Which is true about Jenkins administration?
- A) Managed through Manage Jenkins dashboard
- B) Includes security, monitoring, maintenance, nodes
- C) Both A & B
- D) None of the given

**Correct Answer: C**

---

> 🎯 **Quick Revision:**
> - **DevOps:** Dev + Ops collaboration, single team handles full lifecycle, cross-functional teams
> - **CI:** Integrate code to shared repo several times/day, auto build & test, Git/Mercurial, Jenkins/TeamCity
> - **CD:** Auto deploy to production, ready-to-ship state, Chef/Puppet
> - **CM:** Monitor performance, security, compliance
> - **Pipeline:** 5 components (Build, Infra, Test, Release, Validation) | 3 triggers (Polling SCM, Webhooks, Scheduled)
> - **Jenkins:** Open-source, Java, 1000+ plugins, free, portable | 7-step CI architecture | Freestyle (simple) vs Pipeline (complex)
> - **Plugins:** 1900+ plugins | Git, Docker, K8s, SonarQube, Jira, EC2, Maven, Blue Ocean, Mailer, Build Pipeline
> - **Test Automation:** Unit, Integration, Regression tests | Selenium (web), Appium (mobile)
> - **Security:** 2 axes (Security Realm + Authorization) | CSRF, XSS protection | LDAP/AD/Custom DB | HTTPS | Matrix-based security
> - **Admin:** 7 tasks (Security, Monitoring, Maintenance, Config, Users, Notifications, Nodes)
