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

![Document Retrieval System Model](data:image/png;base64,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)

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
