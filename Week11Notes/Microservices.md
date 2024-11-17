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

- The REST (REpresentational State Transfer) architectural style is based on the idea of transferring representations of digital resources from a server to a client 
- Resources are accessed via their unique URI and RESTful services operate on these resources 
- This is the fundamental approach used in the web where the resource is a page to be displayed in the user's browser: an HTML representation is generated by the server in response to an HTTP GET request and is transferred to the client for display by a browser or special-purpose app 

### RESTful Service Principles

| **Principle**       | **Explanation**                                                                                                                                       |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Use HTTP verbs`       | The basic methods defined in the HTTP protocol (GET, PUT, POST, DELETE) must be used to access the operations made available by the service.         |
| `Stateless services`   | Services must never maintain internal state. Microservices are stateless, so fit with this principle.                                                |
| `URI addressable`      | All resources must have a URI, with a hierarchical structure, that is used to access subresources.                                                   |
| `Use XML or JSON`      | Resources should normally be represented in JSON or XML or both. Other representations, such as audio and video representations, may be used if appropriate. |

### RESTful Service Operations

| **Action** | **Implementation**                                                                                                                                           |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Create`     | Implemented using HTTP POST, which creates the resource with the given URI. If the resource has already been created, an error is returned.                  |
| `Read`       | Implemented using HTTP GET, which reads the resource and returns its value. GET operations should never update a resource so that successive GET operations with no intervening PUT operations always return the same value. |
| `Update`     | Implemented using HTTP PUT, which modifies an existing resource. PUT should not be used for resource creation.                                               |
| `Delete`     | Implemented using HTTP DELETE, which makes the resource inaccessible using the specified URI. The resource may or may not be physically deleted.             |

### *Example Scenario: Road Information System*

- Imagine a system that maintains information about incidents, such as traffic delays, construction, and accidents on a national road network 
- Users can query the system to discover incidents on the roads on which they are planning to travel 

### A RESTful Road Information System

- When implemented as a RESTful web service, you need to design the resource structure so that incidents are organized hierarchically 
    - *Example: incidents may be recorded according to the road identifier (e.g. I-95), the location (e.g., Rocky Mount), the direction of travel (e.g., North), and an incident number (e.g. 1); Therefore, each incident can be accessed using its URI*
- Most likely use: a website or app that does this for the user 

### Service Operations

- `GET`
    - Accesses returned information about a reported incident or incidents 
- `POST`
    - Accesses added information about a new incident 
- `PUT`
    - Accesses updated information about a reported incident 
- `DELETE`
    - Deletes an incident 

### HTTP Request and Response Processing

![HTTP Example Diagram 1](https://media.geeksforgeeks.org/wp-content/uploads/20210905091508/ImageOfHTTPRequestResponse-660x374.png)

### HTTP Request and Response Message Organization

![HTTP Example Diagram 2](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAATkAAAChCAMAAACLfThZAAABdFBMVEX////tY57//5m54KVnq59de6aX0HdqZ87//52+5qm746fyZaH19fUAAABqamnt7e26usFsg2CXuYXDw8aWk5eLi1VbeqqVlVqX1Hn4/ZTS2H2x3qGYLWKSJ2PARH68QH+Uvoju7onMyXljd11siV2fn1Sp0JXh4YFTTa93rGJqZdRWaVtzfVWwrbKNlVSAPFeAIVfyXqLYWpBDW4U7d3ZmllVeeFDMVYjRz9JRIjaxSnZ2dnZdJz5sLUjk5OSPj49PT09dXV3EUoNbWbGhoaGlRW5FHS6PxHAhLRpjYMB+fn5WVlbY2NiNO14gHz5KZTpSbJIsSUQ+Pj4wMDAiIiI5GCYrKVJOS5czQ1tBQUEYGBhDQYIYGC9XkYclMUJGXX09ZV47TmlSiH4nEBpdgEk0Ryk2NWk7Ui9bfUhIRo0bJDAvTkgaKyg/TDhUVDU3KowwL10SGQ4qOSFpYtuMqnwzdXgPFBwYJyRxcYNOEDE2AClYAD58Y9uWAAASrElEQVR4nO2diV/bSJbHpQ4J6eiwOyK77D3dM5MeMuP1jgZWlizJtpBELFscPiB2uBNIOmR36exuzx7//P5eyTY2GDBOJAir90nKcqmkeu9b79Uh2wX3L98lK2sFLgZRnv1lsvKvHPfdt8nK02wc5LI/Pk5WnmVA7kGS8uTpXCYWct8kKo+fKSm5lFxKLiWXkkvJpeTiI/ckRrnX5J4/jU+eP0mM3I8/xCfjyT15+m+/i03++dukyD1+thCbvP/xEnK/m41LXvwmQXLzj2KS+aWU3JSSkkvJpeTuHbnlra2t5Qm4VJfP0rtKbmVpaeUKpAuszMKXIrf9emtr8/WV0BjZ5U3G+ac7TG7p6P3ap5VHSyt9jqOFVn5m+N5e464Tk1utwpNWyZuqRKZana1SziBjeba6uTUgN0unl2f7Z+8WubWF+Xl43RG8amFhZf7t2iMwXIEXLjCWKy8jgMiijJWFlc8kB1ivj2eXV49Xl2dfbx5vL2+9JpTI2Fye3TzefL28fVztk9uid6envbN3jNzbIwTr/MLL9ytHa2vvVtaOVt4tzC+tPXr3/t3bAbmFtZWf6SzKHC19HrnTUwnBurn8oroJOi82idzsKoi+WN6sbldnl2ePz6IV5PC6Pbu59YIc9W6Rm19Yk96tPFqDT83Pv1tZej8PciD1MuriBuRePppfW3i/NL9yNM7rbhCtL7bAYHVzc3N763h29nWP3Pbm5up2dWtb+mn2dITcKV2zivK/VO8WuZWlR/PMxRCo745eDsjNL738eWmY3Cci9+7o6OjnzyQ3O3t8DDovMBKAzuny1vGL6jYRnd2qIne1enyBXFT8rvnc0RJilcgtrZ353NIaPPDRJ+rYXs7PU4GI3Hv45dhhdvKxlQaD7eUq+rmt2Z9WT+nw9HQbPdnp6k+zm6cYd18T3WVpdXUV/rjFfA5lVs8PyLdObuXo5aejlfn37xZerq29XFj4eWHh09q7tUdHa1E/Jx0dfVrqRyv1c28/i1y1n1SjhBysOpwxKFOt9ssOTtwtcjSQspRe2bB6dhCdpYMoZ1B4enLn5fh8EE4sd4Dcl5CpyV2cp6Xk0nVrSi4l95WRexGX/Hui5GKTy8g9/3V88h+Jffb1+Idn8cn3Y8k9eBLjt+YS/Lw1zm/NfTOeXCJyLz+pTslNS+6eRGuc4Tqe3JPnMX6vOrkR4psf4vta9SUjxJOnf/qL2OS7BGclM7HJf142n/vTw7jknpBbTMml5FJyKbmUXEouJZeS+1rJre8i2Xs1LvdrIre/j2Rj53zuYkpuInIfb4Xc+u7uwcOHB7u7ew8fvtp9tRtlrL96tbfO8r4GcvC5ww1yvJMTpDsbJyeLUcb+/sbO/sbJebCfSe6X3d3dD68egg4ggeCHhwevQLCX8WH9If6dd8k7SO7jycZJd2dnY2fn48z+4cziCXngxiHe7WwQ18ONmcP9L0vuw/r6+sGr9Q97e8D1cO/gw/ruOnyNZbyiMIYHrt99cvs7YLazf3J4+PFwZufw5GRmAzwWKWPjEChnPm5cFbrTR+v6h4O9vT1Kd8/IQcjb1vd+uRzdnSE3Q9G6v7G4uEj8yOeI3GKUAXIzO/sfv7DPMXIPdw/Wdw8OdtcPpHWCtxtlELkPLGa/BnIf4XaHO90ZJBsfZzb2D/98OPNn5oqHM4cfdxCwX5TcAfMqDA6vomRvHSD3ehl0AqPE3Y/WQ/KqRQwLCFsWu4uUHkbHM/R6uH9FN5fOhKeWlFxKLiWXkkvJpeRScim5u04u/aR6OnLPfx+fJPj9ud/+IT5Jvz/3Zb+Rk4zcy2+BpeSmJnc/ojX57889eP6b+ORpgt+f+218ctn35xROjEm4JHcXis+K7GXzuVj2q40kUXKxSUruS9RyHTmxZ2bGtm16GTknDr9ezeOWyWUiVUVYkTlTvHdu+FW8UrmbkAsarBaxVZE7AVeXh8/l3Oi1xF7L4vlrh+V2yYnNEntVJLnSVLhSbvikXI/KlMk1CsGktVxDTpQDJbotuJRtuzh8sk9uzr3estslp5Rk1q4KuNhlzh3ZRrtoR68V+0a1XEMu69YZLCKH/yDndmpNUSnLjRJOimXiGpFrcsVKpVnglGa5dLHO2yVXtOcYLCKnFIkcfK/EBZVKt46TCouXSuRzmY5cKyPYOh3lylquIVcROZluKDabTQnRWhShQUkpVCg6s6XI0SNyHa6Yo3BuceeigcmtkkOD2xU6UCSYUeBcxQaVmhgwhYtuFEk9chS1QSFXGtf/TE4u05LlDnERyzA3yJEKbrGpUG9QySjNDnPwATmFs+V6q1SqXOwsbpWcW5blJqkKf+PERgY+h/htiOiJQFRujJKriUAbVEql5gUek5Nz4Tw27hT1c+6cXbRrdVQYkcu6BTZizDEX65ETO5lMoX5B+VslVwMTciIWrVzHdpVckMmUe+SK9ShGKqRXn5zrihnlM3yuSTeTsxStQSno2PVipua6jRy1XS2DEaJI7jZXLpVKYoOTmSKlwK3dLXKsfTMSOChNFhClrFLLBa0MkauhO8o0yN3KxVKQQz8HJ5nLZmS3VLmylivJiYwAm8jVC4UCBgmbg0OJNl65OuZ4UQkb5wp4j6kSva8XxqC5TXLMAK5OoQNFoSEUrSsZWMEUtsUzE2EbFxVA0atrSdcQ09aSkpu2lpTcTUS5jNxcLjZJklx8VvzXeHIPHjyPTwZ1JPAJzvfxyTeXkEtC7ufnECm5lFyC5P4mCYmf3F8lIcPkvv313yYh//1tvOQe/8/fJSHPHg+T+6OQgOTjJvdPSVjxx38cJcfHL0mQS8CMlNy0kpKbVlJy00pKblpJyU0rKblpJSU3rYwlRxO9+KpMjFysVown50CGC2n9A5UOhZGsa+VC8aTIqbBCG2Knqr36VToU+PN6XW/FSPFx5NQ3+bxpnV2k6b02zKuqzqsGvcurE1apOQK78syEhMgJBszwvUG9QmhEx2qeN/KCQQZo+Qm9MiqOK68h58PRfTQXtRJSzeQZJ9USVJP3epcLvTZEC1IhVaVEiJq2d46aNgz7VQ3aPClyeQGNzg/UCg2mhRA6ghEKvjOqlhr5oRrpLqgsu2+GwJu94irfd5nx5BCVJs9bppkXNN/STbiaYDloNNVULZ981lQ90zKptG5avqO2LU9FSY23LDMUjLal807bgueaVFzQ1VC3eg6QGDmEjReSAb4heL7VNkJPUNs8bDFCxBVFkykwfSnOyByU0vDfhPl53REAIBSgeNvQ2uQvqq76ptVWLyf3pt2W4M+WIJiO5QiOCcvhbaZKPmdQRTg2DcGhe+BVs6AQyhLYNzyyfVXwQlwm+KpHuARTDUNB1ZMlJ8EMAy2Oisn3LEM1iZlJ5KCRAHIWD8XJnciA0PPyAjmJ54G4qpEBlgbFCTDzW7iQhmLCldGax+UC7sFw4dXwgG+YnGpKFiNHubi30DZN8w1vtCVPe2OaOqAz1+yT8xInh2jlfTAjaPACDxTRxqBF5HQ18jnSl2xmPKGsA919iw8lX/Ng0RvmqCZvaXxEjnziOnLDPqeagB6R83rkHCqDQ7iaYwGuYKJnNJDN+w7aDSPbXSCnq0M+hzBiXXVEjnzO5ElfNbI5JGeh06qmqbDaAQBH7ZHr+xzIXeFzzGVU6rIsXtPRz8FrcRfq53Rea9NoCRR6nrWbiVcNUNAb53WP1y0LY5ee9x0H3aCuOj6KUz8HBfyEo9U029TP5XX0c7r1Buq3Mb7qDGoIA4kc05dstiyLZ2EG3aF1Hr2QRXl5anI+pPiifu5Kn6Nxpj820tBEAw4N6RhbaWSJRh38i2Y3psOGVVZyMB6pWpR3Vrx3UXLk+mYIvDYY8nnChbG1pxqNtP3x0+8P/WxGcDa2Cn1r+XNmTLj6Ck1m8rhJnO7ccKZ+a6svuBgbRvNjztEIcTMzJiTnDHzwklM3kNtbt6psUiaMXTg44zKvkgnJXdEeN14b3uKK//PMGC2SyLOSUbf8Wp+VCMbI26vIsUcN7IFDlAzyLmQMJ8NpL6Gh5fbIjSp39u5ixjlbhmynjP50ZAJyhkcDt4cRwNE8VfU0IXoH6WVg5KEM1TCAEcVR0qOWMQyMZ5TLbiKw4eyWyEHDvhqqBo0cr/eOpxkAZeC04JCWZNyguEaHmkMAtH6uOaHPWZ7XFjzTsEJBCr123mtjnuZZHlvlUYbRVh1khLyJpYZACaY9hunxVuhJhqp7oSXgEJNHJ39r5FTdyIekka8ab7y8D6X4vOWxqShlMC2hto7FloHFt4nigu95vqb5hoU1kW6YWLYZKEULuYnImSHGUlo3+DwWo1ghWJruQBOezX5oEo7FDFqwrfpwQJ4l0MfL09zbMrwQt9DYTfje6uE2yGHirqqkkREaebaMMTVgo+ksrcyRgZUBFvFG3tHRH2u+w8xQ2QMOLC9Mh6z1Dfbcx5uInIBVAntIAnptnpYfluZjUm1Gk2lar1oOVhmWrtKDEMz5dAsqWmbohLTeCFEY1eImWn/1cCvRqll+CJ+H3xM5kx4YtWFGn5zJHlNQBu/Q0xzN0kP4oOU7eYdM92GhyWt5Pc/3Vw/X+pxHjz+w2MMq9E2PHN6pIX9GTqNWCFU4nq6FKG74muDloQqvG/RkwENpAfGNlfWt+Ryt+uBlcJg+OegnOMYwOepQDGShJCWOT3zpCVWbp2VviJsgtAbPRq8l58OTVFPXNSLHXIw3dZ+upid4UYalYykY+tROPprFa5t5ev5gmpTrh4LXxk1GR6WEx1aLVDZ83xIicggjx9ejfo6t//FPowyY6pNBugEzLdMTLN/yCUCb5WJJaw7Prq4gJ4xMSIRoZO59KjKaMZoI9BgFIXqWy49UmTC5YeV6ig+sGM04Z4ajsqcDZ7mqNXTbeGbCaKGRwdQJR0z5SmbCWttqj86mRib0ca0hrlrnfCXkrjEj/aR6WknJTSspuWklJTetpOSmlZTctJKSm1bOk/vCPxoYK/fy9xB/n4RYcZP7339IQobJPXn+q0TkScy/+/rrROT74V/MPUlG7uNvDdNfaabkkiSXrPwqHnLfx7ij6zgBuZKcsLhxkKsHSZuhcJyStMRBjhMTN4OLbQ/ZyzeXjUXuiRmppJJKKqmkkgqTOtv38XphMzKbNl4ctxvpbQrbufLGEwZmytj9IScUsSFB5Gsrjrb7lqUODiVp6urikCJZ0Lx+N+pRgRUil5OkqefoYkeu1+ckciV2D6QZtgc7bdjezxK5jFQiuLLUzHC1Vou2aRd7p85SKo1Lz65MRoJGoa5I7rC60GFgDr0RI9XOsohcq84VW1JmYEpmyIgJTBEbJdrnucAFkoQjpJ0GJ3eAKkvNEnBiDVlikZ3l5FYtmylXWpzdlGhjaDS20kvRfMhBvgwjopslJAFtU45KoUG5p64odZgGMgunVoM24y5AQZcTkcW2Ei5JsivWZEnMMFNyzAgFabaX2g2pggtgnTy2WrFDvl5BacBC0ylco8wVy3ijKF1oUCCqOZuTomhtuUG2EnS5WsC5Da5b5AqK2JKxDuYUm2sUObmBO+VyTc6WEusMA7Kgm6EaO26BqStKRbCou5IotkpkkdvNFNHeWdK6ziK0JOXkQq0kiZWAyzXEpgxTuHKZUqXOyeWeKXXJ5poXdzZn5GouGoT8C43hdkU0IVesETnyJTQcmgSR2iPXLHQqbqnLtehcZg6tXKdLkdbdLu5DHixlmS1jq4uFXNNtNDjmKXCBBqkronZYUCvSNvJcs8Tluhmc7yrkheRcZHC9WQxciVxOkmyXGQHPayJwXLgb10G8dXNZOlscVy1FqwI+c116h0Yi3JHPua1o3KiXgKRPTmxJBZDrzkWXu2Uq5JabdXge6uoUETjZUicJYn1h2sJZel7eV9eWFLkClSsROdoNvCjV4RSRlCRAzuak/t+R4NxaF77oViS7URNRrEym5JRLhxCxGdDoVK9Lc27XznSDHJSAJxclxZZKOcku0NUuJ7E/qSA3OdzflbhSV5FlrhHUK+VMuViv1FjhItBni+Tirjv9oHVTKaKdclJObFaUrlLoRuq2FLklFkgPhZGT7KADpvC8XKlJHgFysmSDXAmEZZGMKItypV5s2q2iAgiulAskF3GfbV382wdELkBUZWSXq9dqmNvUKyU0oRhUlEqBq8sVepZXqcHfsjW2XTq6t4DLytRCAYYeuVLsp0otyAbUZtCNK1QqMW5UfE5c2lM+KIqZIunI1BWluYD+HEOd6QETFTkjlmoVZCm16M9p5NA7F0UFA4hbGxiRCWqyDe2LCpkoKy24rlzLXqNAX4LPCTVXtpXkxoZLRfwCvawr12l0vIGM2a9+crFr3e4Ef+glbhFbk/rJ5WJXuq07YEoq/8/l/wDEt126mp+rFQAAAABJRU5ErkJggg==)

### *Example - XML and JSON Descriptions*

- *XML*
```xml
<id>
A90N17061714391
</id>
<date>
20170617
</date>
<time>
1437
</time>
...
<description>
Broken-down bus on north lane. One lane closed. Expect delays of up to 30 minutes. 
</description>
```
- *JSON*
```json 
{
    id: "A90N17061714391", 
    "date": "20170617", 
    "time": "1437", 
    "road_id": "I95", 
    "place": "Rocky Mount", 
    "direction": "North", 
    "severity": "significant", 
    "description": "Broken-Down bus on north lane. Expect delays of up to 30 minutes."
}
```

### *Example - POST Request and Associated Response*

![Request Example](https://i.sstatic.net/BCfFq.jpg)

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
