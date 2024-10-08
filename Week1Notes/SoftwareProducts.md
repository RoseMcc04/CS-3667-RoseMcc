# Software Products

## Table of Contents

1. [What is a Software Product?](#what-is-a-software-product)
2. [Software Products](#software-products)
3. [Project-Based Software Engineering](#project-based-software-engineering)
4. [What is a Software Product Line?](#what-is-a-software-product-line)
5. [What is a Platform?](#what-is-a-platform)
6. [How/Where Does Software Execute?](#howwhere-does-software-execute)
7. [Why Look at Product Development?](#why-look-at-product-development)
8. [Developing a Product Vision](#developing-a-product-vision)
9. [Moore's Vision Template](#moores-vision-template)
10. [How is a Product Vision Developed?](#how-is-a-product-vision-developed)
11. [Software Product Management](#software-product-management)
12. [Two Key Product Management Activities](#two-key-product-management-activities)
13. [What is Prototyping?](#what-is-prototyping)
14. [Why Prototype?](#why-prototype)

## What is a Software Product?

- Software products are generic software systems that provide functionality that is useful to a range of customers. 

## Software Products

- Significant differences of scale: large-scale business systems, personal multi-platform products, mobile apps, and games
- Software product engineering methods and techniques have evolved from software engineering techniques that support one-off, custom software systems
- These custom software systems are developed in dedicated software projects - still important for large businesses, government, and public bodies

- Noted Examples:
    - Yelp
    - Google Maps

- Given Examples:
    - Microsoft Excel
    - WhatsApp

## Project-Based Software Engineering

- Starting point (Development): software requirements, created by the client, describing needed functionality 
    - Software Developed internally or by external software company (contractor/consultants) who design and implement a system that delivers functionality to meet the requirements
    - Custom software usually has a long lifetime, must be supported over that lifetime
    - Lifetime could be 10 years or more
    - Many systems (legacy systems) are decades old 
- Starting point (Business): a business opportunity, identified by individuals or a company
    - They develop a software product to take advantage of this opportunity and sell this to customers
    - The company who identified the opportunity design and implement a set of software features that realize the opportunity and that will be useful to customers
    - Who is responsible for deciding on the development timescale, what features to include, and when the product should change?
    - The software development company (not an external client!)
    - Rapid delivery of software products is essential to capture the market for that type of product

## What is a Software Product Line?

- A set of software products that share a common core
    - Each member of the product line includes customer-specific adaptations and additions
    - Software product lines may be used to implement a custom system for a customer with specific needs that cannot be met by a generic product
- An example would be a company providing communication software for different emergency services that use different types of radio/communication equipment
- Another example would be software for smart TVs (due to many different models of said televisions)

## What is a Platform?

- A software (or combined software and hardware) product that includes functionality so that new applications can be built on it. 
- Example: Facebook, where you can create "Facebook apps"
- Self-Example: Github?

## How/Where Does Software Execute?

- Stand-alone: The software executes entirely on the customer's computers
- Hybrid: Part of the software's functionality is implemented on the customer's computer but some features are implemented on the product developer's side
- Software service: All of the product's features are implemented on the developer's servers and the customers accesses these through a browser or mobile app

## Why Look at Product Development?

- Key feature of product development: there is no external customer that generates requirements and pays for the software
- True for other types of software development:
    - Student projects (us) --> students decide on system to build, features to include
    - Research software --> researchers develop software to help them answer questions that are relevant to their research
    - Internal tool development --> software developers may develop tools to support their work - these are basically internal products not intended for customers
    - Open-source systems --> the community decides on features

## Developing a Product Vision

- The starting point for software product development is a "product vision"
- Product visions are simple statements that define the essence of the product to be developed
- The product vision should answer three fundamental questions:
    - What is the product to be developed?
    - Who are the target customers and users?
    - Why should customers buy this product?

## Moore's Vision Template

- FOR (target customer)
- WHO (statement of the need or opportunity)
- The (PRODUCT NAME) is a (product category)
- THAT (key benefit, compelling reason to buy)
- UNLIKE (primary competitive alternative)
- OUR PRODUCT (statement of primary differentiation)

## How is a Product Vision Developed?

| Information Source              | Explanation                                                                                                                                       |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Customer experience             | The software developers may have extensive discussions with prospective customers of the product to understand the problems that they face; constraints, such as interoperability, that limit their flexibility to buy new software; and critical attributes of the software that they need. |
| Prototyping and “playing around” | Developers may have an idea for software but need to develop a better understanding of that idea and what might be involved in developing it into a product. They may develop a prototype system as an experiment and “play around” with ideas and variations using that prototype system as a platform. |
| Domain experience               | The product developers may work in a particular area (say, marketing and sales) and understand the software support that they need. They may be frustrated by the deficiencies in the software they use and see opportunities for an improved system. |
| Product experience              | Users of existing software (such as word processing software) may see simpler and better ways of providing comparable functionality and propose a new system that implements this. New products can take advantage of recent technological developments such as speech interfaces. |

## Software Product Management

- Software product management is a business activity that focuses on the software products developed and sold by the business
- Product managers (PMs) take overall responsibility for the product and are involved in planning, development, and product marketing
- Must balance business needs, technology constraints, and customer experience

## Two Key Product Management Activities

- User story and scenario development
    - User stories and scenarios are used to refine a product vision and identify product features - we will do this in this course for our projects
- Product backlog creation and management
    - The product backlog is a prioritized "to-do" list of what has to be developed - product managers help create and refine this, work with team to prioritize features

## What is Prototyping?

- Product prototypinh is the process of developing an early version of a product to test your ideas and to convince yourself and company funders that your product has real market potential
    - You may be able to write an inspiring product vision, but your potential users can only really relate to your product when they see a working version of your software. They can point out what they like and do not like about it and make suggestions for new features
    - A prototype may be also used to help identify fundamental software components or services and to test technology

## Why Prototype?

- Potential users can only really relate to your product when they see a working version of your software
- Prototypes can help to identify fundamental software components or services
- Prototypes can be used to test technology and check feasibility
- Building a prototype should be the first thing that you do when developing a software product
- Generally plan to throw it away, though