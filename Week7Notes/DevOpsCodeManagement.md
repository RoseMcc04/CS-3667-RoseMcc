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
6. [Systems Integration](#systems-integration)
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

![Image](data:image/jpeg;base64,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)

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

## Systems Integration

### Continuous Integration

## Continuous Delivery and Deployment

### Benefits of Continuous Deployment

## DevOps Measurement

### Automating Measurement
