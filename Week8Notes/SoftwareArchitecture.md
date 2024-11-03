# Software Architecture

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [Software Architecture Definition](#software-architecture-definition)
    1. [The IEEE Definition of Software Architecture](#the-ieee-definition-of-software-architecture)
    2. [What does the architecture include?](#what-does-the-architecture-include)
2. [What is a service?](#what-is-a-service)
3. [What is a component?](#what-is-a-component)
4. [What is a module?](#what-is-a-module)
5. [Why is architecture important?](#why-is-architecture-important)
6. [Issues that Influence Architectural Decisions](#issues-that-influence-architectural-decisions)
7. [Non-Functional System Quality Attributes](#non-functional-system-quality-attributes)
    1. [Other Issues](#other-issues)
8. [Architectural Design Guidelines](#architectural-design-guidelines)
9. [Component Organization](#component-organization)
    1. [Architectural Model of a Document Retrieval System](#architectural-model-of-a-document-retrieval-system)
10. [Design Guidelines and Layered Architectures](#design-guidelines-and-layered-architectures)
11. [Cross Cutting Concerns](#cross-cutting-concerns)
12. [Distribution Architecture](#distribution-architecture)
13. [Client-Server Architecture](#client-server-architecture)
    1. [Client-Server Communication](#client-server-communication)
14. [Service-Oriented Architecture](#service-oriented-architecture)
15. [Zooming Out: Architectural Styles](#zooming-out-architectural-styles)
    1. [Examples of Architectural Styles](#examples-of-architectural-styles)
16. [Technology Choices](#technology-choices)
17. [Database Options](#database-options)
18. [Delivery Platform](#delivery-platform)
19. [Server](#server)
20. [Open Source](#open-source)
21. [Development Tools](#development-tools)

## Software Architecture Definition

### The IEEE Definition of Software Architecture

- **Software Architecture**
    - Architecture is the fundamental organization of a software system embodied in its components, their relationships to each other and to the environment, and the principles guiding its design and evolution. 

### What does the architecture include?

- Overall organization (*what are the moving parts of your system?*)
- Decomposition into <ins>components</ins> (*how is your system broken into pieces?*)
- Server organization (*how is your system distributed across different machines?*)
- Technologies that you use to build the software (*what is your technology stack?*)

## What is a service?

- A *service* is a "coherent unit of functionality"
- This means it includes related pieces of functionality that naturally go together
- Note: we can view this at different levels of granularity:
    - Our program may use a smaller service to handle sending emails
    - The mailer service may be made up of multiple services to create, edit, send, and receive messages

## What is a component?

- A *component* implements a coherent set of functionality or features
- Components could be small (a single class) or large (an entire program)
- Components present a related collection of more focused *services*
- Architecture focuses on component *interfaces*, leaves *implementation* to a later stage of the development process

## What is a module?

- A *module* is a named collection of components
- The components in a module are generally related, meaning they provide a coherent collection of related *services*

## Why is architecture important?

- The architecture of a system has fundamentals influence (often the main influence!) on the non-functional system properties
- Architectural design involves understanding the issues that affect the architecture of your product and creating an architectural description that shows the critical components and their relationships
- Minimizing complexity should be an important goal for architectural designers! (Complex == harder to change, harder to understand, more likely to have bugs)

## Issues that Influence Architectural Decisions

- Nonfunctional product characteristics
- Product lifetime
- Software use
- Number of users
- Software compatability

## Non-Functional System Quality Attributes

| Attribute      | Key Issue                                                                 |
|----------------|---------------------------------------------------------------------------|
| Responsiveness  | Does the system return results to users in a reasonable time?            |
| Reliability     | Do the system features behave as expected by both developers and users?   |
| Availability    | Can the system deliver its services when requested by users?              |
| Security        | Does the system protect itself and users’ data from unauthorized attacks and intrusions? |
| Usability       | Can system users access the features that they need and use them quickly and without errors? |
| Maintainability | Can the system be readily updated and new features added without undue costs? |
| Resilience      | Can the system continue to deliver user services in the event of partial failure or external attack? |

### Other Issues

- Product lifetime: long-lived products will have multiple revisions, how well does the architecture accommodate this requirement?
- Software reuse: reuse of existing software helps us deliver more quickly, but also constrains our choices
- Number of users: what is the impact of having a large number of users, or a number that varies significantly?

## Architectural Design Guidelines

- **Implement Once**
    - Avoid duplicating functionality at different places in your 
    architecture 
- **Separation of Concerns**
    - Organize your architecture into components that focus on a single 
    concern 
- **Stable Interfaces**
    - Design component interfaces that are coherent and change slowly 

## Component Organization

- Abstraction in software design means that you focus on the essential 
elements of a software or software component without concern for its 
details
- At the architectural level, your concern should be on large-scale 
architectural components 
- Decomposition involves analyzing these large-scale components and 
representing them as a set of finer-grain components 
- *Layered* models are often used to illustrate hwo a system is composed 
of components 

### Architectural Model of a Document Retrieval System

![Document Retrieval System Model](https://media.springernature.com/lw685/springer-static/image/chp%3A10.1007%2F978-981-33-4866-0_63/MediaObjects/498359_1_En_63_Fig1_HTML.png)

## Design Guidelines and Layered Architectures

- Each layer is an area of concern and its considered separately from other layers
    - The top layer is concerned with user interaction, the next layer down with user interface management, the thid layer with information retrieval and so on
- Within each layer, the components are independent and do not overlap in functionality
    - The lower layers include components that provide general functionality so there is no need to replicate this in the components in a higher level
- The architectural model is a high-level model that does not include implementation information
    - Ideally, components at level X should only interdace with the APIs of the components in level X-1; That is, interactions should be between layers and not across layers
- Why may this be challenging in practice?

## Cross-Cutting Concerns

- Cross-cutting concerns are concerns that are systemic - they affect the whole system
- In a layered architecture, cross-cutting concerns affect all layers in the system as well as the way in which people use the system
- Cross-cutting concerns are completely different from the functional concerns represented by layers in a software architecture
- Every layer has to take them into account and there are inevitably interactions between the layers because of these concerns
- The existance of cross-cutting concerns is the reason why modifying a system after it has been designed to improve its security is often more difficult <br>

![Cross Cutting Concerns Diagram](https://miro.medium.com/v2/resize:fit:568/0*7oVHDbVUsuXW4d5K.png)

## Distribution Architecture

- The distribution architecture of a software system defines the servers in the system and the allocation of components to these servers
- Client-server architectures are a type of distribution architecture that is suited to applications where clients access a shared database and perform business logic applications on that data
- In this architecture, the user interface is implemented on the user's own computer or mobile device
    - Functionality is distributed between the client and one or more server computers

## Client-Server Architecture

![Client-Server Architecture Model](https://media.geeksforgeeks.org/wp-content/uploads/20240419170238/Client-Server-Model.webp)

### Client-Server Communication

- Client-server communication normally uses HTTP protocal
    - Client uses a HTTP *verb* (e.g., GET, POST) along with a resource identifier (URL, technically a URI) that should be acted upon, additional info is in URI or separate, e.g., a POST form
- HTTP is a text-only protocol so structured data has to be represented as text
    - XML is a markup language with tags used to identify each data item (XML == "eXtensible Markup Language")
    - JSON is a similar representation based on the representation of objects in the JavaScript language (JSON == "JavaScript Object Notation")

## Service-Oriented Architecture

- Services in a service-oriented architecture are stateless components, which means that they can be replicated and can migrate from one computer to another
- Many servers may be involved in providing services
- A service-oriented architecture is usually easier to scale as demand increases and is resilient to failure <br>

![Service-Oriented Architecture Diagram](https://umairsaeed.com/img/Paper-2023-Architecture-04-SOA-01w.png)

## Zooming Out: Architectural Styles

- Introduced by Garlan and Shaw, 1994
- Useful terminology
    - Components: encountered this term above
    - Connectors: interactions between components
    - Constraints: limitations on how components and connectors can be combined
- Paper view architectures as graphs (components == nodes, connectors == edges)

### Examples of Architectural Styles

- Pipes and filters
- Data abstraction and object-oriented organization
- Event-based, implicit invocation
- Layered
- Repository
- Also: client-server, state transition
- Some newer: service-oriented

## Technology Choices

| Technology          | Design Decision                                                                                     |
|---------------------|-----------------------------------------------------------------------------------------------------|
| Database            | Should you use a relational SQL database or an unstructured NoSQL database?                        |
| Platform            | Should you deliver your product on a mobile app and/or a web platform?                            |
| Server              | Should you use dedicated in-house servers or design your system to run on a public cloud? If a public cloud, should you use Amazon, Google, Microsoft, or some other option? |
| Open Source         | Are there suitable open-source components that you could incorporate into your products?           |
| Development Tools   | Do your development tools embed architectural assumptions about the software being developed that limit your architectural choices? |

## Database Options

- There are two kinds of databases that are now commonly used:
    - Relational databases, where the data is organized into structured tables
    - NoSQL databases, in which the data has a more flexible, user-defined organization
- Relational databases, such as MySQL, are particularly suitable for situations where you need transaction management and the data structures are predictable and fairly simple
- NoSQL databases, such as MongoDB, are more flexible and potentially more efficient than relational databases for data analysis
    - NoSQL databases allow data to be organized hierarchically rather than as flat tables and this allows for more efficient concurrent processing of "big data"
- Many other varietires of NoSQL databases, e.g., tuple stores, graph databases

## Delivery Platform

- Delivery can be web-based or a mobile product or both
- Mobile Issues:
    - **Intermittent Connectivity**
        - You must be able to provide a limited service without network connectivity
    - **Processor Power**
        - Mobile devices have less powerful processors, so you need to minimize computationally intensive platforms
    - **Power Management**
        - Mobile battery life is limited so you should try to minimize the power used by your application
    - **On-Screen Keyboard**
        - On-screen keyboards are slow and error-prone; You should minimize input using the screen keyboard to reduce user frustration
- To deal with these differences, you usually need separate browser-based and mobile versions of your product's front-end
    - You may need a completely different decomposition architecture in these different versions to ensure that performance and other characteristics are maintained

## Server

- A key decision: design your system to run on customer services or to run on the cloud?
- For consumer products that are not simply mobile apps, the author thinks it almost always makes sense to develop for the cloud
- For business products, it is a more difficult decision
    - Some businesses are concerned about cloud security and prefer to run their systems on in-hours servers; They may have a predictable pattern of system usage so there is less need to design your system to cope with large changes in demand
- An important choice you have to make if you are running your software on the cloud is which cloud provider to use

## Open Source

- Open source software is software that is available freely, which you can change and modify as you wish
    - The advantage is that you can reuse rather than implement new software, which reduces development costs and time to market
    - The disadvantages of using open-sourced software is that you are constrained by that software and have no control over its evolution
- The decision on the use of open-source software also depends on the availability, maturity, and continuing support of open source components
- Open source license issues may impose constraints on how you use the software
- Your choice of open source software should depend on the type of product that you are developing, your target market, and the expertise of your development team

## Development Tools

- Development technologies, such as a mobile development toolkit or a web application framework, influence the architecture of your software
    - These technologies have built-in assumptions about system architectures and you have to conform to these assumptions to use the development system
- The development technology that you use may also have an indirect influence on the system architecture
    - Developers usually favor architectural choices that use familiar technologies that they understand; For instance, if your team has a lot of experience with relational databases, they may argue for this instead of a NoSQL database
