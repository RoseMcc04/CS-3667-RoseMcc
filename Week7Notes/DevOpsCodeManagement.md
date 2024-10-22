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

#### Repository Cloning in Git

### Distributed Code Management Benefits

### Branching and Merging

## DevOps Automation

### Aspects of DevOps Automation

## Systems Integration

### Continuous Integration

## Continuous Delivery and Deployment

### Benefits of Continuous Deployment

## DevOps Measurement

### Automating Measurement
