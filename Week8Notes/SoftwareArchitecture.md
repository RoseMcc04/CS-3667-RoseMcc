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

![Document Retrieval System Model](https://ai2-s2-public.s3.amazonaws.com/figures/2017-08-08/33252ce2ac645d06da936295686c45e6a1e4432b/3-Figure2-1.png)

## Design Guidelines and Layered Architectures

## Cross-Cutting Concerns

## Distribution Architecture

## Client-Server Architecture

### Client-Server Communication

## Service-Oriented Architecture

## Zooming Out: Architectural Styles

### Examples of Architectural Styles

## Technology Choices

## Database Options

## Delivery Platform

## Server

## Open Source

## Development Tools
