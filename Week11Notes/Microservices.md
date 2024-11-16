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
3. [Microservices Architecture](#microservices-architecture)
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

## Software Services

- **Software Service**
    - a software component that can be accessed from remote computers over the internet; *Given an input*, a service produces a corresponding outpit, *without side effects*
- *Given an input*: service accessed through defined interface, implementation details hidden (abstraction!)
- *Without side effects*: services <ins>do not</ins> maintain internal state, state stored outside the service 

### Modern Web Services

- After various experiments in the 1990s with service-oriented computing, the idea of "big" Web Services emerged in the early 2000s
- Based on XML-based protocols and standards, e.g., SOAP for service interaction ![SOAP Interaction](https://www.w3.org/TR/soap/), WSDL for interface description ![WSDL Interface Description](https://www.w3.org/TR/wsdl/)
- Heavy-weight, very general protocols - most services do not need anything this complex (but many nice tools work with these, so do not disregard them completely!)
- Modern service-oriented systems tend towards lighter-weight solution, we will focus on those

## Microservices

### *Example - System Authentification Features*

### *Example - Authentification Microservices*

### Characteristics of Microservices

### Microservice Communication

### Cohesion and Coupling

### Single Responsibility Principle

## Microservices Architecture

### Benefits of Microservices Architecture

### *Example - Photo-Printing System for Mobile Devices*

### Key Design Questions

## Decomposition Guidelines

## Service Communications

### Synchronous and Asynchronous Microservice Interaction

### Direct and Indirect Service Communication

## Microservice Data Design

### Service Coordination: Orchestration and Choreography

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

### Automating Deployment: High-Level

