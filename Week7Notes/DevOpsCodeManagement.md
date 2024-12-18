# DevOps and Code Management

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [Software Support]()
2. [Development, Release, and Support](#development-release-and-support)
3. [DevOps](#devops)
    1. [DevOps Principles](#devops-principles)
    2. [Benefits of DevOps](#benefits-of-devops)
4. [Code Management](#code-management)
    1. [Why use Code Management?](#why-use-code-management)
    2. [A Code Management problem...](#a-code-management-problem)
    3. [Code Management and DevOps](#code-management-and-devops)
    4. [Code Management Fundamentals](#code-management-fundamentals)
    5. [Code Repository](#code-repository)
    6. [Features of Code Management Systems](#features-of-code-management-systems)
    7. [Git](#git)
        1. [Repository Cloning in Git](#repository-cloning-in-git)
    8. [Distributed Code Management Benefits](#distributed-code-management-benefits)
    9. [Branching and Merging](#branching-and-merging)
5. [DevOps Automation](#devops-automation)
    1. [Aspects of DevOps Automation](#aspects-of-devops-automation)
6. [System Integration](#system-integration)
    1. [Continuous Integration](#continuous-integration)
7. [Continuous Delivery and Deployment](#continuous-delivery-and-deployment)
    1. [Benefits of Continuous Deployment](#benefits-of-continuous-deployment)
8. [DevOps Measurement](#devops-measurement)
    1. [Automating Measurement](#automating-measurement)

## Software Support

- Traditionally, separate teams were respinsible for software development, software
  release, and software support 
- The development team passed over a "final" version of the software to a release 
  team; This team then built a release version, tested this, an prepared release 
  documentation before releasing the software to customers
- A third team was responsible for providing customer support 
    - The original development team were sometimes also responsible for implementing 
      software changes
    - Alternatively, the software may have been maintained by a separate "maintenance 
      team"

## Development, Release, and Support

![Diagram](https://devopscube.com/wp-content/uploads/2020/04/releast-management-architecture-min-1024x634.png)

## DevOps

- DevOps (Development + Operations) was developed to speed the release and support process up
- Three factors led to the development and adoption of DevOps:
    - Agile software engineering reduced the development time for software, but the traditional release process introduced a bottleneck between development and deployment
    - Amazin re-engineered their software around services and introduced an approach in which a service was developed and supported by the same team; Amazon's claim that this led to significant improvements in reliability was widely publicized
    - It became possible to release software as a service (SaaS), running on a public or private cloud; Software products did not have to be released to users on physical media or downloads

### DevOps Principles

| Principle                                | Explanation                                                                                                        |
|------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| Everyone is responsible for everything.  | All team members have joint responsibility for developing, delivering, and supporting the software.                 |
| Everything that can be automated should be automated. | All activities involved in testing, deployment, and support should be automated if it is possible to do so. There should be minimal manual involvement in deploying software. |
| Measure first, change later.             | DevOps should be driven by a measurement program where you collect data about the system and its operation. You then use the collected data to inform decisions about changing DevOps processes and tools. |

### Benefits of DevOps

| Benefit                | Explanation                                                                                                                                          |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Faster deployment       | Software can be deployed to production more quickly because communication delays between the people involved in the process are dramatically reduced. |
| Reduced risk            | The increment of functionality in each release is small, so there is less chance of feature interactions and other changes that cause system failures and outages. |
| Faster repair           | DevOps teams work together to get the software up and running again as soon as possible. There is no need to discover which team was responsible for the problem and to wait for them to fix it. |
| More productive teams   | DevOps teams are happier and more productive than the teams involved in the separate activities. Because team members are happier, they are less likely to leave to find jobs elsewhere. |

## Code Management

- During the development of a software product, the development team will probably create tens of thousands of lines of code and automated tests
- These will be organized into hundreds of files; Dozens of libraries may be used, and several, different programs may be involved in creating and running the code
- Code management is a set of software-supported practices that is used to manage an evolving codebase

### Why use Code Management?

- You need code management to ensure that changes made by different developers do not interfere with each other, and to create different product versions
- Code management tools make it easy to create an executable product from its source code files and to run automated tests on that product

### A Code Management problem...

*Alice and Bob worked for a company called FinanceMadeSimple and were team members
involved in developing a personal finance product. Alice discovered a bug in a module called
TaxReturnPreparation. The bug was that a tax return was reported as filed but sometimes it
was not actually sent to the tax office. She edited the module to fix the bug. Bob was
working on the user interface for the system and was also working on TaxReturnPreparation.
Unfortunately, he took a copy before Alice had fixed the bug and, after making his changes,
he saved the module.This overwrote Alice’s changes, but she was not aware of this. The product tests did not reveal the bug, as it was an intermittent failure that depended on
the sections of the tax return form that had been completed. The product was launched
with the bug. For most users, everything worked OK. However, for a small number of users,
their tax returns were not filed, and they were fined by the revenue service. The subsequent
investigation showed the software company was negligent. This was widely publicized and,
as well as a fine from the tax authorities, users lost confidence in the software. Many
switched to a rival product. FinanceMadeSimple failed and both Bob and Alice lost their
jobs.*

### Code Management and DevOps

- Source code management, combined with automated system building, is essential for professional software engineering
- In companies that use DevOps, a modern code management system is a fundamental requirement for "automating everything"
- Not only does it store the project code that is ultimately deployed, it also stores all other information that is used in DevOps processes
- DevOps automation and measurement tools all interact with the code management system  

![Image](https://image.slidesharecdn.com/10-190210203814/85/Engineering-Software-Products-10-Devops-and-code-management-11-320.jpg) 

### Code Management Fundamentals

- Code management systems provide a set of features that support four general areas: 
    - **Code transfer**: Developers take code into their personal file store to work on it then return it to the shared code management system
    - **Version storage and retrieval**: Files may be stored in several different versions and specific versions of these files can be retrieved
    - **Merging and branching**: Parallel development branches may be created for concurrent working; Changes made by developers in different branches may be merged
    - **Version information**: Information about the different versions maintained in the system may be stored and retrieved

### Code Repository

- All source code management systems have the general form shown in Figure 10.3 with a shared repository and a set of features to manage the files in that repository: 
    - All source code files and file versions are stored in the repository, as are other artifacts such as configuration files, build scripts, shared libraries, and versions of tools used
    - The repository includes a database of information about the stored files such as version information, information about who has changed the files, what changes were made at what times, and so on
- Files can be transferred to and from the repository and information about the different versions of files and their relationships may be updated
    - Specific versions of files and information about these versions can always be retrieved from the repository

### Features of Code Management Systems

| Feature                       | Description                                                                                                                                                     |
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Version and release identification | Managed versions of a code file are uniquely identified when they are submitted to the system and can be retrieved using their identifier and other file attributes. |
| Change history recording       | The reasons changes to a code file have been made are recorded and maintained.                                                                                   |
| Independent development        | Several developers can work on the same code file at the same time. When this is submitted to the code management system, a new version is created.              |
| Project support                | All of the files associated with a project may be checked out at the same time. There is no need to check out files one at a time.                                |
| Storage management             | The code management system includes efficient storage mechanisms so that it doesn’t keep multiple copies of files that have only small differences.              |

### Git

- In 2005, Linus Torvalds, the developer of Linux, revolutionized source code management by developing a distributed version control system (DVCS) called Git to manage the code of the Linux kernel
- This was geared toward large-scale open-source development; It took advantage of the fact that storage costs had fallen to such an extent that most users did not have to be concerned with local storage management
- Instead of only keeping the copies of the files that users are working on, Git maintains a clone of the repository on every user's computer

#### Repository Cloning in Git

![Image](https://preview.redd.it/nm1w0gnf2zh11.png?width=1080&crop=smart&auto=webp&s=f793be53fbc0246cecc4d865b2ea479d5ea57e94)

### Distributed Code Management Benefits

- Resilience
    - Everyone working on a project has their own copy of the repository; If the shared repository is damaged or subjected to a cyberattack, work can continue, and the clones can be used to restore the shared repository; People can work offline if they do not have a networking connection
- Speed
    - Committing changes to the repository is a fast, local operation and does not need data to be transferred over the network
- Flexibility
    - Local experimentation is much simpler; Developers can safely experiment and try different approaches without exposing these to other project members; With a centralized system, this may only be possible by working outside the code management system

### Branching and Merging

- Branching and merging are fundamental ideas that are supported by all code management systems
- A branch is an independent, stand-alone version that is created when a developer wishes to change a file
- The changes made by developers in their own branchs may be merged to create a new shared branch
- The repository ensures that branch files that have been changed cannot overwrite repository files without a merge operation
    - If Alice or Bob make mistakes on the branch they are working on, they can easily revert to the main file
    - If they commit changes, while working, they can revert to earlier versions of the work they have done; When they have finished and tested their code, they can then replace the main file by merging the work they have done with the main/master branch

![Image](https://wac-cdn.atlassian.com/dam/jcr:c6db91c1-1343-4d45-8c93-bdba910b9506/02%20Branch-1%20kopiera.png?cdnVersion=2353)

## DevOps Automation

- By using DevOps with automated support, you can dramatically reduce the time and costs for integration, deployment, and delivery
- *Everything that can be, should be automated* is a fundamental principle of DevOps
As well as reducing costs and time required for integration, deployment, and delivery, process automation also makes these processes more reliable and reproducible
- Automation information is encoded in scripts and system models that can be checked, reviewed, versioned, and stored in the project repository

### Aspects of DevOps Automation

| Aspect                    | Description                                                                                                                                                           |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Continuous integration     | Each time a developer commits a change to the project’s main branch, an executable version of the system is built and tested.                                           |
| Continuous delivery        | A simulation of the product’s operating environment is created and the executable software version is tested.                                                          |
| Continuous deployment      | A new release of the system is made available to users every time a change is made to the main branch of the software.                                                 |
| Infrastructure as code     | Machine-readable models of the infrastructure (network, servers, routers, etc.) on which the product executes are used by configuration management tools to build the software’s execution platform. The software to be installed, such as compilers and libraries and a DBMS, are included in the infrastructure model. |

## System Integration

- System integration (system building) is the process of gathering all the elements required in a working system, moving them into the right directories, and putting them together to create an operational system
- Typical activities that are part of the system integration process include:
    - Installing database software, setting up the appropriate schema
    - Loading test data into the database
    - Compiling the files that make up the product
    - Linking the compiled code with the libraries and other components used
    - Checking that external services used are operational
    - Deleting old configuration files and moving configuration files to the correct locations
    - Running a set of system tests to check that the integration has been successful
- Continuous integration is only effective if the integration process is fast and developers do not have to wait for the results of their tests of the integrated system
- However, some activities in the build process, such as populating a database or compiling hundreds of system files, are inherently slow
- It is therefore essential to have an automated build process that minimizes the time spent on these activities
- Fast system building is achieved using a process of incremental building, where only those parts of the system that have been changed are rebuilt

### Continuous Integration

- Continuous integration simply means that an integrated version of the system is created and tested every time a change is pushed to the system's shared repository
- On completion of the push operation, the repository sends a message to an integration server to build a new version of the product
- The advantage of continuous integration compared to less frequent integration is that it is faster to find and fix bugs in the system
- If you make a small change and some system tests then fail, the problem almost certainly lies in the new code that you have pushed to the project repository
- You can focus on this code to find the bug that is causing the problem

![Image](https://www.globalapptesting.com/hs-fs/hubfs/Frame%20147.png?width=1000&height=387&name=Frame%20147.png)

## Continuous Delivery and Deployment

- Continuous integration means creating an executable version of a software system whenever a change is made to the repository; The CI tool builds the system and runs tests on youe development computer or project integration server
- However, the real environment in which software runs will inevitably be different from your own development system
- When your software runs in its real, operational environment, bugs may be revealed that did not show up in the test environment
- Continuous delivery means that, after making changes to a system, you ensure that the changed system is ready for delivery to customers
- This means that you have to test it in a production environment to make sure that environmental factors do not cause system failures or slow down its performance

![Image](https://www.researchgate.net/publication/287723351/figure/fig2/AS:580514571407361@1515416867820/Architecture-of-information-server-cluster-based-on-network-sensors_Q320.jpg)

### Benefits of Continuous Deployment

| Benefit                | Explanation                                                                                                                                                             |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Reduced costs          | If you use continuous deployment, you have no option but to invest in a completely automated deployment pipeline. Manual deployment is a time-consuming and error-prone process. Setting up an automated system is expensive and takes time, but you can recover these costs quickly if you make regular updates to your product. |
| Faster problem solving  | If a problem occurs, it will probably affect only a small part of the system and the source of that problem will be obvious. If you bundle many changes into a single release, finding and fixing problems are more difficult. |
| Faster customer feedback | You can deploy new features when they are ready for customer use. You can ask them for feedback on these features and use this feedback to identify improvements that you need to make. |
| A/B testing            | This is an option if you have a large customer base and use several servers for deployment. You can deploy a new version of the software on some servers and leave the older version running on others. You then use the load balancer to divert some customers to the new version while others use the older version. You can measure and assess how new features are used to see if they do what you expect. |

## DevOps Measurement

- After you have adopted DevOps, you should try to continuously improve your DevOps process to achieve faster deployment of better-quality software
- There are four types of software development measurement:
    - **Process measurement**: You collect and analyze data about your development, testing, and deployment processes
    - **Service measurement**: You collect and analyze data about the software's performance, reliability, and acceptability to customers
    - **Usage measurement**: You collect and analyze data about how customers use your product
    - **Business success measurement**: You collect and analyze data about how your product contributes to the overall success of the business

### Automating Measurement

- As far as possible, the DevOps principle of automating everything should be applied to software measurement
- You should instrument your software to collect data about itself and you should use a monitoring system to collect data about your software's performance and availability
- Some process measurements can also be automated
    - However, there are problems in process measurement because people are involved; They work in different ways, may record information differently, and are affected by outside influences that affect the way they work
