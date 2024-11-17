# Microservices Architecture

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [Software Services](#software-services)
    1. [Modern Web Services](#modern-web-services)
2. [Microservices](#microservices)
    1. [*Example - System Authentification Features*](#example---system-authentification-features)
    2. [*Example - Authentification Microservices*](#example---authentification-microservices)
    3. [Characteristics of Microservices](#characteristics-of-microservices)
    4. [Microservice Communication](#microservice-communication)
    5. [Cohesion and Coupling](#cohesion-and-coupling)
    6. [Single Responibility Principle](#single-responsibility-principle)
3. [Microservices Architecture](#microservices-architecture-1)
    1. [Benefits of Microservices Architecture](#benefits-of-microservices-architecture)
    2. [*Example - Photo-Printing System for Mobile Devices*](#example---photo-printing-system-for-mobile-devices)
    3. [Key Design Questions](#key-design-questions)
4. [Decomposition Guidelines](#decomposition-guidelines)
5. [Service Communications](#service-communications)
    1. [Synchronous and Asynchronous Microservice Interaction](#synchronous-and-asynchronous-microservice-interaction)
    2. [Direct and Indirect Service Communication](#direct-and-indirect-service-communication)
6. [Microservice Data Design](#microservice-data-design)
    1. [Service Coordination: Orchestration and Choreography](#service-coordination-orchestration-and-choreography)
7. [RESTful Services](#restful-services)
    1. [RESTful Service Principles](#restful-service-principles)
    2. [RESTful Service Operations](#restful-service-operations)
    3. [*Example Scenario: Road Information System*](#example-scenario-road-information-system)
    4. [A RESTful Road Information System](#a-restful-road-information-system)
    5. [Service Operations](#service-operations)
    6. [HTTP Request and Response Processing](#http-request-and-response-processing)
    7. [HTTP Request and Response Message Organization](#http-request-and-response-message-organization)
    8. [*Example - XML and JSON Descriptions*](#example---xml-and-json-descriptions)
    9. [*Example - GET Request and Associated Response*](#example---get-request-and-associated-response)
8. [Service Deployment Overview](#service-deployment-overview)
    1. [Automating Deployment: High-Level](#automating-deployment-high-level)
    2. [Deployment Automation Steps](#deployment-automation-steps)

## Software Services

- **Software Service**
    - a software component that can be accessed from remote computers over the internet; *Given an input*, a service produces a corresponding outpit, *without side effects*
- *Given an input*: service accessed through defined interface, implementation details hidden (abstraction!)
- *Without side effects*: services <ins>do not</ins> maintain internal state, state stored outside the service 

### Modern Web Services

- After various experiments in the 1990s with service-oriented computing, the idea of "big" Web Services emerged in the early 2000s
- Based on XML-based protocols and standards, e.g., SOAP for service interaction [SOAP Interaction](https://www.w3.org/TR/soap/), WSDL for interface description [WSDL Interface Description](https://www.w3.org/TR/wsdl/)
- Heavy-weight, very general protocols - most services do not need anything this complex (but many nice tools work with these, so do not disregard them completely!)
- Modern service-oriented systems tend towards lighter-weight solution, we will focus on those

## Microservices

- **Microservice**
    - *small-scale, stateless* service that has a single responsibility
- They are completely independent with their own database and UI management code
- Microservices are not an entire application - applications are created by combining microservices
- Software products that use microservices have a *microservices architecture*

### *Example - System Authentification Features*

- User registration, where users provide information about their identity, security information, mobile (cell) phone number, and email address
- Authentification using UID/password
- Two-factor authentification using code sent to mobile phone
- User information management *e.g. change password or mobile phone number*
- Reset forgotten password

### *Example - Authentification Microservices*

![Authentification Microservice Exampe](https://i.sstatic.net/ZFeNK.png)

### Characteristics of Microservices

| **Characteristic**            | **Explanation**                                                                                                                                  |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `Self-contained`                 | Microservices do not have external dependencies. They manage their own data and implement their own user interface.                             |
| `Lightweight`                    | Microservices communicate using lightweight protocols, so that service communication overheads are low.                                          |
| `Implementation independent`    | Microservices may be implemented using different programming languages and may use different technologies (e.g., different types of database) in their implementation. |
| `Independently Deployable`      | Each microservice runs in its own process and is independently deployable, using automated systems.                                            |
| `Business-oriented`              | Microservices should implement business capabilities and needs, rather than simply provide a technical service.                                 |

### Microservice Communication

- Microservices communicate by <ins>exchanging messages</ins>
- A message that is sent between services includes some administrative information, a service request, and the data required to deliver the requested service
- Services return a response to service request messages
    - An authentification service may send a message to a login service that includes the name input by the user
    - The response may be a token associated with a valid username or might be an error saying that there is no registered user

### Cohesion and Coupling

- A well-designed microservice should have *high cohesion* and *low coupling*
- **Cohesion**
    - a measure of the number of relationships that parts of a component have with each other
- **Coupling**
    - a measure of the number of relationships that one component has with other components in the system
- Why do we want high cohesion? Why do we want how coupling? What does this mean?

### Single Responsibility Principle

- Each microservice should only have a single responsibility, *i.e., it should do one thing only, and it should do it well*
- Challenge: how do we define "one thing only" in a general way? Can we?
- *Note: responsibility does not always mean a single, functional activity - it could be based around related activities that do not make sense being separated, or around shared data*

## Microservices Architecture

- A microservices architecture is an *architectural style* - a tried and tested way of implementing a logical software architecture (layered, pipe, filter, etc.)
- This architectural style addresses two problems with monolithic applications:
    - The whole system has to be rebuilt, re-tested, and re-deployed when any change is made; This can be a slow process as changes to one part of the system can adversely affect other components 
    - As the demand on the system increases, the whole system has to be scaled, even if the demand is localized to a small number of system components that implement the most popular system functions 

### Benefits of Microservices Architecture

- Microservices are self-contained and run in separate processes 
- In cloud-based systems, each microservice may be deployed in its own container; This means a microservice can be stopped and restarted without affecting other parts of the system 
- If the demand on a service increases, service replicas can be quickly created and deployed; These do not require a more powerful server so "scaling-out" is, typically, much cheaper than "scaling up"

### *Example - Photo-Printing System for Mobile Devices*

- **Scenario**:
    - Imagine that you are developing a photo-printing service for mobile devices. 
- **Description**:
    - Users can upload photos to your server from their phone or specify photos from their Instagram account that they would like to be printed; Prints can be made at different sizes and on different media
- **Application**
    - Users can choose a print size and choose medium. *For instance, they may decide to print a picture onto a mug or a t-shirt; The prints or other media are prepared and then posted to their home; They pay for prints either using a payment service such as **Android** or **Apply Pay** or by registering a credit card with the printing service provider* 

![Microservice Architecture Example](https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcTjOk-UIoO5QjM9zmMp2DvXqCB2HSLkSBkIi0tuwnMO384p46qC)

### Key Design Questions

- *What are the microservices that make up the system?*
- *How should microservices communicate with each other?*
- *How should service failure be detected, reported, and managed?*
- *How should the microservices in the system be coordinated?*
- *How should data be distributed and shared?*

## Decomposition Guidelines

- Balance fine-grain functionality and system performance
    - Single-function services mean that changes are limited to fewer services but require service communications to implement user functionality; This slows down a system because of the need for each service to bundle and unbundle messages sent from other services 
- Follow the *Common Closure Principle*
    - Elements of a system that are likely to be changed at the same time should be located within the same service; Most new and changed requirements should therefore only affect a single service 
- Associate services with business capabilities
    - A business capability is a discrete area of business functionality that is the responsibility of an individual or group; You should identify the services that are required to support each business capability 
- Design services so that they only have access to the data that they need 
    - If there is an overlap between the data used by different services, you need a mechanism to propogate data changes to all services using the same data 

## Service Communications

- When you are designing a microservices architecture, you have to establish a standard for communications that all microservices should follow 
- Key decisions: 
    - *Should service interaction be synchronous or asynchronous?*
    - *Should services communicate directly or via message broker middleware?*
    - *What protocol should be used for messages exchanged between services?*

### Synchronous and Asynchronous Microservice Interaction

![Microservice Interaction Diagram](https://miro.medium.com/v2/resize:fit:1400/0*BlOCAJi8PokbfCLh.png)

### Direct and Indirect Service Communication

![Direct/Indirect Service Communication Diagram](https://images.doclify.net/gleek-web/d/61f05c34-d61b-435c-93cf-0432bf59a371.png?w=1200&format=webp) <br>
- Direct service communication requires that interacting services know each other's address 
- The services interact by sending requests directly to those addresses 
- Indirect communication involves naming the services that is required and sending that request to a message broker (sometimes called a message bus) 
- The message broker is then responsible for finding the service that can fulfull the service request 

## Microservice Data Design

- You should isolate data within each system service with as little data sharing as possible 
- If data sharing is unavoidable, you should design microservices so that most sharing is read-only, with a minimal number of services responsible for data updates 
- If services are replicated in your system, you must include a mechanism that can keep the database copies used by replica services consistent 

### Service Coordination: Orchestration and Choreography

![Service Coordination Diagram](https://alok-mishra.com/wp-content/uploads/2022/07/orchestration-or-choreography.png)

## RESTful Services

### RESTful Service Principles

### RESTful Service Operations

### *Example Scenario: Road Information System*

### A RESTful Road Information System

### Service Operations

### HTTP Request and Response Processing

### HTTP Request and Response Message Organization

### *Example - XML and JSON Descriptions*

### *Example - GET Request and Associated Response*

## Service Deployment Overview

- When a system is composed of tens or even hundreds of microservices, deployment of teh system is more complex than for monolithic systems 
- The service development teams decide which programming language, database, libraries, and other support software should be used to implement their service; Consequently, there is no standard deployment configuration for all services 
- It is not normal practice for microservice development teams to be responsible for deployment and service management as well as software development and to use continuous deployment 
- Continuous deployment means that as soon as a change to a service has been made and validated, the modified service is redeployed 

### Automating Deployment: High-Level

- Continuous deployment depends on automation so that as soon as a change is committed, a series of automated activities is triggered to test the software 
- If the software passes these tests, it then enters another automation pipeline that packages and deploys the software 

### Deployment Automation Steps 

- The deployment of a new service starts with the programmer committing the code changes to a code management system such as Git 
- This triggers a set of automated tests that run using a modified service; If all service tests run successfully, a new version of the system that incorporates the changed service is created 
- Another set of automated system tests are then executed; If these run successfully, the service is ready for deployment 
