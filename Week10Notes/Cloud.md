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
    - you can design your software architecture to tolerate server failuures

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

### Elements of Docker Container System

#### Docker Images

### Benefits of Containers

## Types of Cloud Services

### Software as a Service (SaaS)

#### Benefits of SaaS for Product Providers

#### Customizations for SaaS

## Scalability and Resilience

### Resilience

## System Structure

## Cloud Platforms
