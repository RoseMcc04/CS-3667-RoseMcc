# Cloud-Based Software

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [The Cloud](#the-cloud)
2. [Benefits for Software Development](#benefits-for-software-development)
3. [Scalability, Elasticity, and Resilience](#scalability-elasticity-and-resilience)
4. [Virtual Cloud Servers](#virtual-cloud-servers)
    1. [Container-Based Virtualization](#container-based-virtualization)
    2. [Docker](#docker)
    3. [Elements of Docker Container System](#elements-of-docker-container-system)
        1. [Docker Images](#docker-images)
    4. [Benefits of Containers](#benefits-of-containers)
4. [Types of Cloud Services](#types-of-cloud-services)
    1. [Software as a Service (SaaS)](#software-as-a-service-saas)
        1. [Benefits of SaaS for Product Providers](#benefits-of-saas-for-product-providers)
        2. [Customizations for SaaS](#customizations-for-saas)
5. [Scalability and Resilience](#scalability-and-resilience)
    1. [Resilience](#resilience)
6. [System Structure]()
7. [Cloud Platforms](#cloud-platforms)

## The Cloud

- The Cloud == "computing as a utility"
- Made up of a very large number of remote virtual servers and other computing resourcesl, offered for rent
- You can rent as many servers as you need, run your software on these servers, and make them available to your customers
- Cloud is "elastic", can scale up or down as needed
- You may rent a server and install your own software, or you may pay for access to software products that are available on the cloud 

## Benefits for Software Development

| Factor                | Benefit                                                                                           |
|-----------------------|---------------------------------------------------------------------------------------------------|
| Cost                  | You avoid the initial capital costs of hardware procurement.                                      |
| Startup time          | You don’t have to wait for hardware to be delivered before you can start work. Using the cloud, you can have servers up and running in a few minutes. |
| Server choice         | If you find that the servers you are renting are not powerful enough, you can upgrade to more powerful systems. You can add servers for short-term requirements, such as load testing. |
| Distributed development | If you have a distributed development team working from different locations, all team members have the same development environment and can seamlessly share all information. |

## Scalability, Elasticity, and Resilience

- **Scalability**
    - ability of your software to cope with increasing numbers of users
- **Elasticity**
    - related to scalability, allows for scaling up or down
- **Resilience**
    - you can design your software architecture to tolerate server failures

## Virtual Cloud Servers

- A virtual server runs on an underlying physical computer and is made up of an operating system plus a set of software packages that provide the server the functionality required
- **Virtual Server**
    - a stand-alone system that can run on any hardware in the cloud
        - This "run anywhere" characteristic is possible because the virtual server has no external dependencies
- Virtual machines (VMs), running on physical server hardware, can be used to implement virtual servers
    - A hypervisor provides the hardware emulation that simulates the operation of the underlying hardware
- Generally, a single physical server could host multiple virtual servers, and a virtual server could be running on different physical servers at different points in time
- *Example: Google cloud platform, this is Compute Engine*

### Container-Based Virtualization

- If you are running a cloud-based system with many instances of applications or services, you may be able to use a simpler virtualization technology called *containers*
- Using containers accelerates the process of deploying virtual servers on the cloud
    - Containers are usually megabytes (MBs) in size whereas VMS are usually gigabytes (GBs)
    - Containers can be started and shut down in a few seconds rather than the few minutes required for a VM
- Containers are an operating system virtualization technology that allows independent servers to share a single operating system
    - They are particularly useful for providing isolated application services where each user sees their own version of an application
- *Most common example: Docker*

### Docker

- Containers became a mainstream technology around 2015, but they had been developed earlier
- Open-source Docker project provided a standard means of container management that is fast and easy to use
- Docker is a container management system that allows users to define the software to be included in a container as a Docker image
- It also includes a run-time system that can create and manage containers using these Docker images

### Elements of Docker Container System

| Element         | Function                                                                                                                                                                                                                                  |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Docker daemon   | This is a process that runs on a host server and is used to set up, start, stop, and monitor containers, as well as building and managing local images.                                            |
| Docker client   | This software is used by developers and system managers to define and control containers.                                                                                                          |
| Dockerfiles     | Dockerfiles define runnable applications (images) as a series of setup commands that specify the software to be included in a container. Each container must be defined by an associated Dockerfile. |
| Image           | A Dockerfile is interpreted to create a Docker image, which is a set of directories with the specified software and data installed in the right places. Images are set up to be runnable Docker applications. |
| Docker hub      | This is a registry of images that has been created. These may be reused to set up containers or as a starting point for defining new images.                                                       |
| Containers      | Containers are executing images. An image is loaded into a container, and the application defined by the image starts execution. Containers may be moved from server to server without modification and replicated across many servers. You can make changes to a Docker container (e.g., by modifying files) but must commit these changes to create a new image. |

#### Docker Images

- Docker images are directories that can be archived, shared, and run on different Docker hosts; Everything that is needed to run a software system - binaries, libraries, system tools, etc., is included in the directory
- A Docker image is a base layer, usually taken from the Docker registry, with your own software and data added as a layer on top of this
    - The layered model means that updating Docker applications is fast and efficient; Each update to the filesystem is a layer on top of the existing system
    - To change an application, all you have to do is to ship the changes that you have made to its image, often just a small number of files

### Benefits of Containers

- They solve the problem of software dependencies; You do not have to worry about the libraries and other software on the application server being different from those on your development server
    - Instead of shipping your product as stand-alone software, you can ship a container that includes all of the support software that your product needs
- They provide a mechanism for software portability across different clouds; Docker containers can run on any system or cloud provider where the Docker daemon is available
- They provide an efficient mechanism for implementing software services and so support the development of service-oriented architectures
- They simplify the adoption of DevOps due to easier infrastructure management

## Types of Cloud Services

- **Infrastructure as a Service (IaaS)**
    - Cloud providers offer different kinds of infrastructure service such as a compute service, a network service, and a storage service that you can use to implement virtual servers
- **Platform as a Service (PaaS)**
    - This is an intermediate level where you use libraries and frameworks provided by the cloud provider to implement your software; These provide access to a range of functions including SQL and NoSQL databases
- **Software as a Service (SaaS)**
    - Your software product runs on the cloud and is accessed by users through a browser or mobile app

### Software as a Service (SaaS)

#### Benefits of SaaS for Product Providers

| Benefit              | Explanation                                                                                                                                                                                                                                       |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cash flow            | Customers either pay a regular subscription or pay as they use the software. This provides a regular cash flow with payments throughout the year, avoiding large cash injections only at purchase times and minimal income between releases.       |
| Update management    | You control product updates, so all customers receive the update simultaneously. This avoids the need to maintain multiple versions, reducing costs and simplifying maintenance of a consistent software code base.                              |
| Continuous deployment | You can deploy new versions of your software as soon as changes are made and tested, allowing quick bug fixes and continuous improvement in software reliability.                                                                                  |
| Payment flexibility  | Offering multiple payment options attracts a broader customer range, as small companies or individuals can avoid large upfront costs, making the software more accessible.                                                                       |
| Try before you buy   | Early free or low-cost versions can be provided for customer feedback on bugs and potential improvements, enhancing the product based on real user input.                                                                                         |
| Data collection      | You can easily gather data on product usage to identify improvement areas and may also collect customer data for marketing other products to these users.                                                                                        |

#### Customizations for SaaS

| Customization     | Business Need                                                                                                                                                                                         |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Authentication    | Businesses may want users to authenticate using their business credentials rather than the account credentials set up by the software provider (see chapter 7 for more details).                      |
| Branding          | Businesses may want a user interface that is branded to reflect their own organization.                                                                                                               |
| Business rules    | Businesses may want to be able to define their own business rules and workflows that apply to their own data.                                                                                         |
| Data schemas      | Businesses may want to be able to extend the standard data model used in the system database to meet their own business needs.                                                                        |
| Access control    | Businesses may want to be able to define their own access control model that specifies the data that specific users or user groups can access and the allowed operations on that data.                |

## Scalability and Resilience

- The scalability of a system reflects its ability to adapt automatically to changes in the load on that system
- The resilience of a system reflects its ability to continue to deliver critical services in the event of system failure or malicious system use
- You achieve scalability in a system by making it possible to add new virtual servers (scaling-out) or increase the power of a system server (scaling-up) in response to increasing load
    - In cloud-based systems, scaling-out rather than scaling-up is the normal approach used; Your software has to be organized so that individual software components can be replicated and run in parallel
- To achieve resilience, you need to be able to restart your software quickly after a hardware or software failure

### Resilience

- Resilience relies on redundancy:
    - Replicas of the software and data are managed in different locations
    - Database updates are mirrored so that the standby database is a working copy of the operational database
    - A system monitor continually checks the system status; It can switch to the standby system automatically if the operational system fails
- You should use redundant virtual servers that are not hosted on the same physical computer and locate servers in different locations
    - Ideally, these servers should be located in different data centers
    - If a physical server fails or if there is a wider data center failure, then operation can be switched automatically to the software copies elsewhere

## System Structure

- An object-oriented approach to software engineering has been that extensively used for the development of client-server sustems built around a shared database
- The system itself is, logically, a monolithic system with distribution across multiple servers running large software components; The traditional multi-tier client-server architecture is based on this distributed system model
- The alternative to a monolithic approach to software organization is a service-oriented approach where the system is decomposed into fine-grain, stateless services
    - Because it is stateless, each service is independent and can be replicated, distributed, and migrated from one server to another
    - The service-oriented approacj is particularly suitable for cloud-based software, with services deployed in containers

## Cloud Platforms

- Cloud platforms include general-purpose clouds such as Amazon Web Services (AWS), Microsoft Azure, or Google Cloud Platform
- Lesser known platforms oriented around a specific application exist, such as the SAP Cloud Platform
- There are also smaller national providers that provide more limited services but who may be more willing to adapt their services to the needs of different customers
- There is no "best" platform and you should choose a cloud provider based on your background and experience, the type of product that you are developing and the expectations of your customers
- You need to consider both technical issues and business issues when choosing a cloud platform for your product
