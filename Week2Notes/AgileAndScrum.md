# Agile Methodologies and Scrum

## Table of Contents

1. [Agile Software Engineering](#agile-software-engineering)
2. [Agile](#agile)
    1. [Agile Software Engineering](#agile-software-engineering)
    2. [Traditional Plan-Driven Development](#traditional-plan-driven-development)
    3. [Origin of Agile Methods](#origin-of-agile-methods)
    4. [The Agile Manifesto (2001)](#the-agile-manifesto-2001)
    5. [Incremental Development](#incremental-development)
        1. [The Big Picture](#the-big-picture)
        2. [Activities](#activities)
    6. [Agile Principles](#agile-principles)
3. [Extreme Programming (XP)](#extreme-programming-xp)
    1. [Extreme Programming Practices](#extreme-programming-practices)
    1. [Widely Adopted XP Practices](#widely-adopted-xp-practices)
4. [Scrum](#scrum)
    1. [Terminology](#terminology)
    2. [Key Roles in Scrum](#key-roles-in-scrum)
    3. [Scrum and Sprints](#scrum-and-sprints)
    4. [Top Five Benefits](#top-five-benefits)
    5. [Key Practices](#key-practices)
5. [Product Backlogs](#product-backlogs)
    1. [Example Items](#example-items)
    2. [Item States](#item-states)
    3. [The Big Picture](#the-big-picture-1)
    4. [The Details](#the-details)
6. [How do we Estimate for Time/Effort?](#how-do-we-estimate-for-timeeffort)
7. [More on Story Points...](#more-on-story-points)
8. [Timeboxed Sprints](#timeboxed-sprints)
    1. [Benefits](#benefits)
9. [Sprints](#sprints)
    1. [Activities](#activities-1)
    2. [Planning](#planning)
    3. [Example Goals](#example-goals)
    4. [Review](#reviews)
10. [More on Scrums](#more-on-scrums)
11. [Important Agile Activities](#important-agile-activities)
    1. [Example: Code Completedness Checklist](#example-code-completedness-checklist)
12. [Teams](#teams)
    1. [Size and Composition](#size-and-composition)
    2. [Coordination](#coordinations)
    3. [External Interactions](#external-interactions)
13. [Project Management](#project-management)
    1. [Responsibilities](#responsibilities)
14. [Meyer](#meyer)
    1. [Singling Out Some Good Practices](#singling-out-some-good-practices)
    2. [Singling Out Some Brilliant Practices](#singling-out-some-brilliant-practices)

## Agile 

- Virtually all software products are now developed using an agile approach

### Agile Software Engineering

- Agile focus: quick delivery of functionality, minimal overhead, reponsiveness to change
- A large number of agile methods have been developed:
    - No best agile method or technique
    - Which to choose? --> Depends on who is using the technique, the development team, and the type of product being developed

### Traditional Plan-Driven Development

- Traditional, plan-driven development evilved to support the engineering of large, long-lifetime systems where teams may be geographically dispersed and work on the software for several years
- Approach based on controlled and rigorous software development processes that include detailed project planning, requirements specification, and analysis and system modelling
- Downside: plan-driven development involves significant overheads and documentation and it does not support the rapid development and delivery of software

### Origin of Agile Methods

- Agile methods were developed in the 1990s to address problems with plan-driven approaches
- Agile methods:
    - Focus on the software rather than its documentation
    - Develop software in a series of increments
    - Aim to reduce process bureaucracy as much as possible
- Common concept: what delivers value to the customer, versus what is "overhead" or "waste" that can be eliminated

### The Agile Manifesto (2001)

- We are uncovering better ways of developing software by doing it and helping others to do it. Through this work, we have come to value: 
    - individuals and interactions over processes and tools
    - working software over comprehensive documentation
    - customer collaboration over contract negotiation
    - responding to change over following a plan
- While there is value on the items on the right, we value the items on the left more 

### Incremental Development

- All agile methods are based around incremental development and delivery
- Product development focuses on the software features, where a feature does something for the software user
- With incremental development, you start by prioritizing the features so that the most important features are implemented first
    - You only define the details of the feature being implemented in an increment
    - That feature is implemented and delivered
- Users or surrogate users can try it out and provide feedback to the development team. You then go on to define and implement the next feature of the system 

#### The Big Picture

- **Product feature list**
  - Choose features to be included in increment
  - Refine feature descriptions
  - Implement and test feature
  - Integrate feature into system
  - Deliver system increment
  - If all features are complete, deliver system release

#### Activities

| **Activity**                         | **Description**                                                                                                               |
|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| Choose features to be included in an Increment | Using the list of features in the planned product, select those features that can be implemented in the next product increment. |
| Refine feature descriptions          | Add detail to the feature descriptions so that the team members have a common understanding of each feature and there is sufficient detail to begin implementation. |
| Implement and test                   | Implement the feature and develop automated tests for that feature that show that its behavior is consistent with its description. |
| Integrate feature and test           | Integrate the developed feature with the existing system and test it to check that it works in conjunction with other features. |
| Deliver system increment             | Deliver the system increment to the customer or product manager for checking and comments. If enough features have been implemented, release a version of the system for customer use. |

### Agile Principles

| **Principle**                       | **Description**                                                                                                                                   |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Involve the customer                | Involve customers closely with the software development team. Their role is to provide and prioritize new system requirements and to evaluate each increment of the system. |
| Embrace change                      | Expect the features of the product and the details of these features to change as the development team and the product manager learn more about the product. Adapt the software to cope with changes as they are made. |
| Develop and deliver incrementally   | Always develop software products in increments. Test and evaluate each increment as it is developed and feed back required changes to the development team. |
| Maintain simplicity                 | Focus on simplicity in both the software being developed and the development process. Wherever possible, do what you can to eliminate complexity from the system. |
| Focus on people, not the development process | Trust the development team and do not expect everyone to always do things in the same way. Team members should be left to develop their own ways of working without being limited by prescriptive software processes. |

## Extreme Programming (XP)

- The most influential work that has changed software development culture was the development of Extreme Programming (XP)
- The name was coined by Kent Beck in 1998 because the approach was developed by pushing recognized good practice, such as iterative development, to "extreme" levels
- Focused on 12 new development techniques that were geared to rapid, incremental software development, change, and delivery

### Extreme Programming Practices

- **Test-first development**
- **Refactoring**
- **Small releases**
- **Simple design**
- **On-site customer**
- **Sustainable pace**
- **Pair programming**
- **Collective ownership**
- **Incremental planning**
- **Continuous integration**

### Widely Adopted XP Practices

| **Practice**                       | **Description**                                                                                                                                                    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Incremental planning/ user stories | There is no “grand plan” for the system. Instead, what needs to be implemented (the requirements) in each increment is established in discussions with a customer representative. The requirements are written as user stories. The stories to be included in a release are determined by the time available and their relative priority. |
| Small releases                     | The minimal useful set of functionality that provides business value is developed first. Releases of the system are frequent and incrementally add functionality to the previous release. |
| Test-driven development            | Instead of writing code and then tests for that code, developers write the tests first. This helps clarify what the code should actually do and that there is always a “tested” version of the code available. An automated unit test framework is used to run the tests after every change. New code should not “break” code that has already been implemented. |
| Continuous integration             | As soon as the work on a task is complete, it is integrated into the whole system and a new version of the system is created. All unit tests from all developers are run automatically and must be successful before the new version of the system is accepted. |
| Refactoring                        | Refactoring means improving the structure, readability, efficiency, and security of a program. All developers are expected to refactor the code as soon as potential code improvements are found. This keeps the code simple and maintainable. |

## Scrum

- Software company managers need information that will help them understand how much it costs to develop a software product, how long it will take, and when the product can be brought to market
- Plan-driven development provides this information through long-term development plans that identify deliverables - items the team will deliver and when these will be delivered
- Plans always change so anything apart from short-term plans are unreliable
- Scrum is an agile method that provides a framework for agile project organization and planning; it does not mandate any specific technical practices

### Terminology

| **Scrum Term**                       | **Explanation**                                                                                                             |
|--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| **Product**                          | The software product that is being developed by the Scrum team.                                                             |
| **Product Owner**                    | A team member who is responsible for identifying product features and attributes. The Product Owner reviews work done and helps to test the product. |
| **Product backlog**                  | A to-do list of items such as bugs, features, and product improvements that the Scrum team has not yet completed.            |
| **Development team**                 | A small self-organizing team of five to eight people who are responsible for developing the product.                         |
| **Sprint**                           | A short period, typically two to four weeks, when a product increment is developed.                                          |
| **Scrum**                            | A daily team meeting where progress is reviewed and work to be done that day is discussed and agreed.                        |
| **ScrumMaster**                      | A team coach who guides the team in the effective use of Scrum.                                                             |
| **Potentially shippable product increment** | The output of a sprint that is of high enough quality to be deployed for customer use.                                       |
| **Velocity**                         | An estimate of how much work a team can do in a single sprint.                                                              |

### Key Roles in Scrum

- **The Product Owner**--> responsible for ensuring that the development team are always focused on the product they are building rather than diverted into technically interesting but less relevant work (often product manager)
- **The ScrumMaster**--> Scrum expert whose job is to guide the team in the effective use of the Scrum method; more if a team manager than a conventional project manager

### Scrum and Sprints

- In Scrum, software is developed in sprints, which are fixed-length periods (2-4 weeks) in which software features are developed and delivered
- During a sprint, the team has daily meetings (Scrums) to review progress and to update the list of work items that are incomplete
- Sprints should produce a "shippable product increment"; This means that the developed software should be complete and ready to deploy

### Top Five Benefits

- **Product**
    - The product is broken down into a set of understandable chunks that stakeholders can relate to
- **Progress**
    - Unstable requirements do not hold up progress
    - Customers see on-time delivery of increments and gain feedback on how the product works
- **People**
    - Team communication is improved because everyone can see everything
    - Trust between customers and developers is established and a positive culture is created

### Key Practices

- **Product backlog**
    - This is a to-do list of items to be implemented that is reviewed and updated before each sprint
- **Timeboxed sprints**
    - Fixed-time (2-4 week) periods in which items from the product backlog are implemented 
- **Self-organizing teams**
    - Self-organizing teams make their own decisions and work by discussing issues and making decisions by concensus

## Product Backlogs

- The product backlog is a list of what needs to be done to complete the development of a product
- The items on this list are called product backlog items (PBIs)
- The product backlog may include a variety of different items such as product features to be implemented, user requests, essential development activities, and desirable engineering improvements
- The product backlog should always be prioritized so that the items that are implemented first are at the top of the list

### Example Items

1. As a student, I have to figure out which person develops which feature of the product. (feature)
2. As a student, I want to make sure that I remember to factor ethical and social implications of my product, along with human factors. (feature)
3. As someone with Autism Spectrum Disorder (ASD), I want to make sure that other autistic children are treated like people. (user request)
4. Establishment criteria for the assessment of open source software that might be used as a basis for parts of this system. (development activity)
5. Refactor user interface code to improve comprehension and performance. (engineering improvement)
6. Implement encryption for all personal user data. (engineering improvement)

### Item States

| **Heading**               | **Description**                                                                                                                                          |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ready for consideration    | These are high-level ideas and feature descriptions that will be considered for inclusion in the product. They are tentative, so may radically change or may not be included in the final product. |
| Ready for refinement       | The team has agreed that this is an important item that should be implemented as part of the current development. There is a reasonably clear definition of what is required. However, work is needed to understand and refine the item. |
| Ready for implementation   | The PBI has enough detail for the team to estimate the effort involved and to implement the item. Dependencies on other items have been identified.                                          |

### The Big Picture

Product Backlog                  |  Process         | Revised 
-----------------------------    | --------------   | --------------------------
PBI 1                            | Refinement       | PBI 1.1
PBI 2                            |                  | PBI 1.2
PBI 3                            | Estimation       | PBI 2E
PBI 4                            |                  | PBI 3E
PBI 5                            | Prioritization   | PBI 4
                                 | Creation         | PBI 5
                                 |                  | PBI 6

### The Details

- **Refinement**
    - Existing PBIs are analyzed and refined to create more detailed PBIs; This may lead to the creation of some new product backlog items
- **Estimation**
    - The team estimates the amount of work required to implement a PBI and add this assessment to each analyzed PBI
- **Creation**
    - New items are added to the backlog; These may be new features suggested by the product manager, required feature changes, engineering improvements, or process activities such as the assessment of development tools that might be used
- **Prioritization**
    - The product backlog items are reordered to take new information and changed circumstances into account

## How do we Estimate for Time/Effort?

- **Effort required**
    - This may be expressed in person-hours or person-days, the number of hours or days it would take one person to implement that PBI; This is not the same as calendar time; Several people working can reduce calendar time
- **Story points**
    - Story points are an arbitrary estimate of the effort involved in implementing a PBI, taking into account the size of the task, its complexity, the technology that may be required, and the "unknown" characteristics of the work

## More on Story Points...

- They were derived originally by comparing user stories, but they can be used for estimating any kind of PBI
- Story points are estimated relatively; The team agrees on the story points for a baseline task and other tasks are estimated by comparisin with this

## Timeboxed Sprints

- Products are developed in a series of sprints, each of which delivers an increment of the product or supporting software
- Sprints are short duration activities (1-4 weeks) and take place between a defined start and end date; Sprints are timeboxed, which means that development stops at the end of a sprint whether or not the work has been completed
- During a sprint, the team works on the items from the backlog

### Benefits 

- **Demonstrable Progress** --> 
    - There is a tangible output (usually a software demonstrator) that can be delivered at the end of every sprint
- **Problem Discovery** -->
    - If errors and omissions are discovered, the rework required is limited to the duration of a sprint
- **Work Planning** --> 
    - The team develops an understanding of how much work they can do in a fixed time period

## Sprints

### Activities

### Planning

### Example Goals

### Reviews

## More on Scrums

## Important Agile Activities

### Example: Code Completedness Checklist

## Teams

### Size and Composition

### Coordinations

### External Interactions

## Project Management

### Responsibilities

## Meyer

### Singling Out Some Good Practices

### Singling Out Some Brilliant Practices