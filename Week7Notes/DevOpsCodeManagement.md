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

### Why use Code Management?

### A Code Management problem...

### Code Management and DevOps

### Code Management Fundamentals

### Code Repository

### Features of Code Management Systems

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
