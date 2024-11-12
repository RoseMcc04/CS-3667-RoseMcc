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

### Software as a Service (SaaS)

#### Benefits of SaaS for Product Providers

#### Customizations for SaaS

## Scalability and Resilience

### Resilience

## System Structure

## Cloud Platforms
