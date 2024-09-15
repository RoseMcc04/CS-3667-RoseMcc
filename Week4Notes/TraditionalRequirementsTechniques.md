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

- Common technique, especially when users are outside the organization or are geographically dispersed
- Can either be electronic or paper-based
- Select participants
    - Generally a subset of possible participants
    - Sampling techniques used to select people
    - Need to plan for lower participation: paper questionnaires often returned by only 30-50%, web-based 5-30%
- Design the questionnaire
    - Focus on closed-ended questions with little room for ambiguity
    - Opinion questions can ask for level of agreement
    - Factual questions look for specific information
    - Test drive first! Helps remove ambiguity
- Administer the questionnaire
    - Key challenge: getting people to return it
    - Explaining how it will be used, setting a fixed return date, offering to supply a summary of the results, and giving away free stuff all help
    - Inside the org, can also track who has, or has not, completed it
- Follow-up
    - Summarize results shortly after questionnaires returned
    - Helps requirements to proceed quickly, allows results to be provided to interested respondents

### Good Questionnaire Design

- Begin with nonthreatening and interesting questions
- Group items into logically coherent sections
- Do not put important items at the very end of the questionnaire
- Do not crowd a page with too many items
- Avoid abbreviations
- Avoid biased or suggestive items or terms
- Number questions to avoid confusion
- Pretest the questionnaire to identify confusing questions
- Provide anonymity to respondants

## Document Analysis

- Review existing documentation for the system, including reports and the user interface
- Note: *this is only the formal system, there may be an informal system as well*
    - Users may include ad-hoc information in specific "unused" field or on other reports since there is no way to actually give this information directly
    - Some parts of the system may never be used, so it may be good to get rid of them
- Formal is system as it is intended to be used, informal is how it is actually used, these may differ!

## Observation/Ethnography

- Actually watch how people do their work
- Essentially, you are acting like an anthropologist
- Works to check validity of gathered information, gather new information when people do not volunteer it (e.g., people may forget some steps that they do automatically)
- **Keys**
    - Keep a low profile
    - Do not interrupt people while they work
    - Do not influence how people do their work

### Challenges

- People may work differently when they know they are being watched
- Hard to identify new features, you are just getting more details on an existing process
- Studies existing practices, may not be ideal or may be based on historical reasons that no longer hold

## Selecting Appropriate Techniques

- Often, will use multiple techniques, not just one
- Pick different technqiues based on...
    - Type of information
    - Depth of information
    - Breadth of information
    - Integration of information
    - User involvement
    - Cost

## Requirements Analysis Strategies

- Problem analysis
- Root cause analysis
- Duration analysis
- Activity-based costing
- Informal benchmarking
- Outcome analysis
- Technology analysis
- Activity elimination

## Elicitation vs. Analysis

- Requirements *elicitation* focuses on requirements discovery by asking current or potential users of the system
- Requirements *analysis* uses this information as a starting point to develop further details about the requirements
- Analysis may lead to more questions, leading to elicitation, and back to analysis - this operates iteratively

## Requirements Challenges

- We may not have the correct set of users
- The requirements specification may be inadequate (especially with more lightweight techniques)
- Requirements may be ambiguous, interpreted by different stakeholders in different ways
- Some requirements are unknowable at the beginning of a project
- Verifying and validating requirements can be challenging
- Analysis can help us identify these problems

## Analysis Strategies

### #1: Problem Analysis

- Asks users and managers about problems with the current system, possible solutions in the to-be system
- What is a possible limitation of this for finding requirements?
    - This tends to focus only on incremental changes
    - Can improve performance and usability, not likely to truly increase the value or capabilities of the system

### #2: Root Cause Analysis

- Try to identify the root cause of a problem, making sure we do not skip too quickly to a solution
- Works by identifying problems, looking for root causes for each

### #3: Duration Analysis

- Determine the total time it takes to perform a set of business processes for a typical input
- Time each individual step in the processes
- What would it mean if there is a large variance between the total time and the sum of the individual step times?
    - The process may be broken at time point - e.g., something sits in a queue waiting for several weeks

### #4: Activity-Based Costing

- Similar to duration analysis, but with costs and not times
- Look for most costly parts of processes, focuses attention on them
- Remember indirect costs (e.g., rent, electricity)

### #5: Informal Benchmarking

- Analyze other businesses, to see how they do the same or similar processes
- May actually informally visit your competitors to see how they do business (e.g., if you sell computers, you may visit the Apple store to see how they do customer service)

### #6: Outcome Analysis

- Analyze outcomes of business processes from the customer's perspective
- Note: this may not be obvious - what do customers want out of the process, versus what do we typically think this process does?
- Example: *if a customer has a car accident and we are an insurance company, what outcome does the customer want?*

### #7: Technology Analysis

- Develop a list of important and/or interesting technologies
- Brainstorm ways that these technologies could be used to support/enhance the business
- This does not mean they will all be adopted!
- What is a potential problem here?
    - We do not want to use a technology for technology's sake, there needs to be a real business driver

### #8: Activity Elimination

- Look at each activity in the business process
    - How could it be eliminated?
    - How could the company operate without it?
    - What would be likely to happen?
- This can result in some odd results that do not make sense, since we have to do this with each activity

## Requirements Modeling

- For high-level requirements, we will use domain models
    - Also referred to as logical models
    - Focus on what the requirements are, not on how they will be implemented
- These include use case diagrams and activity diagrams, can also just be box and arrow diagrams

## Use Case Diagrams

<figure>
    <img src="https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/what-is-a-use-case-diagram-in-UML/UML_use_case_example-800x707.PNG" alt="Basic Use Case Diagram" width="300">
    <figcaption>Lucidchart Use Case Tutorial Diagram</figcaption>
</figure>

### Elements of Use Case Diagrams

## Identifying Major Use Cases

## Activity Diagrams

### Elements of Activity Diagrams

## Business Process Modeling Best Practices

## Guidelines for Creating Activity Diagrams