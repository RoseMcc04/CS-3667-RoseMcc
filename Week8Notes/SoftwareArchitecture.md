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
- Software compatability: Do we need to interoperate with other existing systems?

## Architectural Design Guidelines

- **Implement Once**
    - Avoid duplicating functionality at different places in your architecture
- **Separation of Concerns**
    - Organize your architecture into components that focus on a single concern
- **Stable Interfaces**
    - Design component interfaces that are coherent and that change slowly

## Component Organization

- Abstraction in software design means that you focus on the essential 
elements of a software or software component without concern for its 
details
- At the architectural level, your concern should be on large-scale 
architectural components
- Decomposition involves analyzing these large-scale components and 
representing them as a set of finer-grain components 
- *Layered* models are often used to illustrate how a system is composed 
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
