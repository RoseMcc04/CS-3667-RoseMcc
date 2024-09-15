# Traditional Requirements Techniques

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [The World and the Machine](#the-world-and-the-machine)
2. [System Environments](#system-environments)
3. [Functional Requirements](#functional-requirements)
4. [Non-Functional Requirements](#non-functional-requirements)
    1. [Metrics](#metrics)
5. [Traceability](#traceability)
6. [Requirements Elicitation](#requirements-elicitation)
    1. [Techniques](#techniques)
    2. [Challenges](#challenges)
7. [Interviews](#interviews)
    1. [Select Interviewees](#select-interviewees)
    2. [Design Interview Questions](#design-interview-questions)
    3. [Prepare for the Interview](#prepare-for-the-interview)
    4. [Conduct the Interview](#conduct-the-interview)
    5. [Post-Interview Followup](#post-interview-follow-up)
    6. [Interviewing Challenges](#interviewing-challenges)
8. [Questionnaires](#questionnaires)
    1. [Good Questionnaire Design](#good-questionnaire-design)
9. [Document Analysis](#document-analysis)
10. [Observation/Ethnography](#observationethnography)
    1. [Challenges](#challenges-1)
11. [Selecting Appropriate Techniques](#selecting-appropriate-techniques)
12. [Requirements Analysis Strategies](#requirements-analysis-strategies)
13. [Elicitation vs. Analysis](#elicitation-vs-analysis)
14. [Requirements Challenges](#requirements-challenges)
15. [Analysis Strategies](#analysis-strategies)
    1. [#1: Problem Analysis](#1-problem-analysis)
    2. [#2: Root Cause Analysis](#2-root-cause-analysis)
    3. [#3: Duration Analysis](#3-duration-analysis)
    4. [#4: Activity-Based Costing](#4-activity-based-costing)
    5. [#5: Informal Benchmarking](#5-informal-benchmarking)
    6. [#6: Outcome Analysis](#6-outcome-analysis)
    7. [#7: Technology Analysis](#7-technology-analysis)
    8. [#8: Activity Elimination](#8-activity-elimination)
16. [Requirements Modeling](#requirements-modeling)
17. [Use Case Diagrams](#use-case-diagrams)
    1. [Elements of Use Case Diagrams](#elements-of-use-case-diagrams)
18. [Identifying Major Use Cases](#identifying-major-use-cases)
19. [Activity Diagrams](#activity-diagrams)
    1. [Elements of Activity Diagrams](#elements-of-activity-diagrams)
20. [Business Process Modeling Best Practices](#business-process-modeling-best-practices)
21. [Guidelines for Creating Activity Diagrams](#guidelines-for-creating-activity-diagrams)

## The World and the Machine

- Problems we are trying to solve are generally rooted in the physical world
- Our goal, in general, is to build some machine that will help to solve this problem
- The world and the machine share some phenomena, while others are just in the world or just in the machine
- **Examples**
    - eCommerce Systems
        - Delivery of products happen in the real world
        - Creation of payment records in the database happens in the machine
        - Payment notifications sent to sellers are a shared phenomenon: they are created by the machine, but can be monitored in the world
    - Computerized Speed Monitoring
        - Actual movement of a vehicle takes place in the real world, speed is a real-world phenomenon
        - Monitoring of speed is a shared phenomenon: speed sensors operate in the world, readings are visible to the machine
        - Machine can compute adjustments to speed, braking, etc. internally
        - Machine can transmit braking signals through shared phenomenon, brakes operate in the real world

## System Environments

- *System-as-is*
    - the system that currently exists, which may or may not be computerized
- *System-to-be*
    - the system that will exist once the machine has been built
- *Software-to-be*
    - the software that is part of this system
- *Environment*
    - the surrounding world, which is also part of the system

## Functional Requirements

- Requirements that deal with the functionality of the system
- *"A functional requirement relates directly to a process a system has to perform or information it needs to contain."* - Dennis et al
- Focused on the specific tasks that the users are trying to accomplish (e.g., rent a video, check out a book from a library system, book a flight)
- Can be higher-level or very detailed
- User stories are *one way* of capturing these

## Non-Functional Requirements

- Requirements that deal with properties or constraints of the system
- *"Nonfunctional requirements refer to behavioral properties that the system must have, such as performance and usability."* - Dennis et al
- Often focus on either the system being developed or the process used to develop the system
- May cut across or induce multiple functional requirements
- Will see these as non-functional attributes later

### Metrics

- Should use metrics for non-functional requirements where possible
- **Examples**
    - transactions/second (speed), size in MB (size), time to find specific features on a page (ease of use), mean time to failure (reliability), availability (reliability), time to restart after failure (robustness), number of target systems for executable (portability)
- This is useful, even in an *agile* context

## Traceability

- **Traceability**
    - means we can link together different software engineering artifacts, to see which influence which
- Worls in the forward direction (e.g., from requirements to design, from design artifacts to code) and in the backwards direction (e.g., from code to the related requirement)
- For us: iseful to link tests to user stories

## Requirements Elicitation

- To start, we need to figure out what requirements are
- Often called requirements eliciation or requirements discovery
- Requirements Analysis then takes these requirements and fleshes them out
= This often involves two systems, mentioned before: the as-is (current) and to-be (new) systems
- Technical staff need to work with the project stakeholders to actually find out what the requirements are for the to-be system

### Techniques

- Interviews
- Questionnaires
- Observation
- Joint Application Development (JAD) sessions
- Document analysis <br><br>  

- This is also about building support for the system
- What does it say to someone if they are included in this process?

### Challenges

- Stakeholders may not know what they really want
- Stakeholders may express requirements in theor own terms
- Different stakeholders may have conflicting requirements
- Organizational and political factors (factors outside the project) may influence the requirements
- Requirements change during analysis, we may learn of new stakeholders, and the busines itself may change

## Interviews

- Generally one on one, but may be done as a group
- Basic steps:
    - Select interviewees
    - Design interview questions
    - Prepare for the interview
    - Conduct the interview
    - Post-interview follow-up

### Select Interviewees

- Set up an interview schedule with attendees, purpose of each interview, times
- Project sponsor, key users, team helps select people to interview
- Should include both managers and lower-level worekrs
- Note: this is an iterative process; You will find you should interview new people as you progress and get more information about the system

### Design Interview Questions

- **Closed-Ended Questions**
    - questions that require a specific answer, used when specific, precise information is needed
- **Open-Ended Questions**
    - questions that leave room for elaboration, used to gather richer information, give the interviewee more control over what is said
- **Probing Questions**
    - follow-up, clarification questions, give the interviewee room to elaborate, shows the person being interviewed that you are listening
- Do not ask questions with readily available answers!
- Process tends to begin with unstructured interviews, more open-ended questions
- Later, more structures interviews, more closed-ended questions, more well-structured question sets
- **Top-Down Interview**
    - start with broad questions, zoom in on specifics (this is the typical style)
- **Bottom-Up Interview**
    - start with specific questions, zoom out (not typical, but may be used to fill in gaps of knowledge)

### Prepare for the Interview

- Prepare for an interview in the same way you would prepare for a presentation
    - Have a plan, including a list of questions in an appropriate order, and think about possible answers and follow-ups
    - Identify transitions between topics
    - Confine the interview to areas the interviewee should know about
- Do not wing it! Prepare in advance, versus just asking general, open-ended questions
- Prepare the interviewee, send info in advance

### Conduct the Interview

- Describe the purpose of the interview
- Write down everything! Feel free to ask the interviewee to pause
- Before recording, check corporate policies and make sure the interviewee is comfortable (can be stressful to be recorded)
- Feel free to ask questions, identify and follow up on jargon
- Separate facts from opinions
- Give interviewee time to ask questions
- End with a summary of how information will be used, next steps

### Post-Interview Follow-Up

- Create a report of the interview
- Send this to interviewee, ask for feedback on any needed clarification or updates
- How soon after the interview should you write up the notes? 
    - Usually should be within 48 hours; more likely to forget information after this period

### Interviewing Challenges

- Interviewees may used specialized language that you do not know or (potentially worse) think means something it does not
- Interviewees may not mention important parts of requirements if they think those are unimportant or if they do not think of them (may be hard to articulate, may be something they do without even thinking about it)

## Questionnaires

### Good Questionnaire Design

## Document Analysis

## Observation/Ethnography

### Challenges

## Selecting Appropriate Techniques

## Requirements Analysis Strategies

## Elicitation vs. Analysis

## Requirements Challenges

## Analysis Strategies

### #1: Problem Analysis

### #2: Root Cause Analysis

### #3: Duration Analysis

### #4: Activity-Based Costing

### #5: Informal Benchmarking

### #6: Outcome Analysis

### #7: Technology Analysis

### #8: Activity Elimination

## Requirements Modeling

## Use Case Diagrams

### Elements of Use Case Diagrams

## Identifying Major Use Cases

## Activity Diagrams

### Elements of Activity Diagrams

## Business Process Modeling Best Practices

## Guidelines for Creating Activity Diagrams