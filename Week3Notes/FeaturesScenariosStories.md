# Features, Scenarios, and Stories

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [Software Products](#software-products)
2. [Software Features](#software-features)
3. [User Understanding](#user-understanding)
4. [Feature Description Template](#feature-description-template)
5. [Personas](#personas)
    1. [Example](#example)
    2. [Descriptions](#descriptions)
    3. [Aspects of Descriptions](#aspects-of-descriptions)
    4. [Benefits](#benefits)
    5. [Derivation](#derivation)
6. [Scenarios](#scenarios)
    1. [Description Elements](#description-elements)
    2. [Writing Scenarios](#writing-scenarios)
7. [User Involvement](#user-involvement)
8. [User Stories](#user-stories)
    1. [Feature Description Using User Stories](#feature-description-using-user-stories)
    2. [Stories and Scenarios](#stories-and-scenarios)
9. [Feature Identification](#feature-identification)
10. [Feature Design](#feature-design)
    1. [Factors](#factors)
    2. [Trade-Offs](#trade-offs)
    3. [Creep](#creep)
    4. [Derivation](#derivation-1)
    5. [Features from the Product Vision](#features-from-the-product-vision)
    6. [The Feature List](#the-feature-list)
11. [Innovation and Feature Identification](#innovation-and-feature-identification)
12. [Exercises](#exercises)

## Software Products

- Three factors that drive the design of software products
    - Business and consumer needs unmet by current products
    - Dissatisfaction with existing software products
    - Changes in technology that make completely new types of products possible
- In the early stage of product development, you are trying to understand <ins>what product features would be useful to users, </ins>and <ins>what they like and dislike about the products that they use</ins>

## Software Features

- A feature is a fragment of functionality such as a "print" feature, a "change background" feature, a "new document" feature, etc
- You should aim to create a list of features to be included in your product **before** you start to code
- The feature list should be your starting point for product design and development

## User Understanding

- It makes sense in any product development to spend time trying to understand the potential users and customers of your product
- A range of techniques have been developed for understanding the ways that people work and use software
    - *Examples: user interviews, surveys, ethnography, and task analysis*
    - Some of these are expensive and unrealistic for small companies
    - We will talk briefly about some of these
- Informal user analysis and discussions - asking users about their work, the software they use, and its strengths and weaknesses - are inexpensive and very valuable

## Feature Description Template

- **Action**
    - A description of how the input data is processed
    - **Activation**
        - How the feature is activated by the user
    - **Input**
        - The input from the user and other sources
- **Output**
    - The output to the user and the system

## Personas

- You need to have an understanding of your potential users to design features that they are likely to find useful and to design a user interface that is suited to them
- **Personas**
    - "Imagined users" where you create a character portrait of a type of user that might use your product:
        - For instance, if your product is aimed at managing appointments for dentists, you might create a dentist persona, a receptionist persona, and a patient persona
- Personas of different types of user help you imagine what these users may want to do with your software and how it might be used; They help you envisage difficulties that they might have in understanding and using product features 

### Example

- **Jack, a primary school teacher**
    - Jack, age 32, is a primary school (elementary school) teacher in Ullapool, a large coastal village in the Scottish Highlands. He teaches children from ages 9 to 12. He was born in a fishing community north of Ullapool, where his father runs a marine fuels supply business and his mother is a community nurse. He has a degree in English from Glasgow University and retrained as a teacher after several years working as a web content author for a large leisure group.
    - Jack’s experience as a web developer means that he is confident in all aspects of digital technology. He passionately believes that the effective use of digital technologies, blended with face-to-face teaching, can enhance the learning experience for children. He is particularly interested in using the iLearn system for project-based teaching, where students work together across subject areas on a challenging topic.

### Descriptions

- A persona should "paint a picture" of a type of product user; They should be relatively short and easy-to-read
- You should describe their background and why they might want to use your product
- You should also say something about their educational bakground and technical skills
- These help you assess whether or not a software feature is likely to be useful, understandable, and usable by typical product users

### Aspects of Descriptions

| Aspect         | Description                                                                                                                                       |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Personalization | You should give them a name and say something about their personal circumstances. It is sometimes helpful to use an appropriate stock photograph to represent the person in the persona. Some studies suggest that this helps project teams use personas more effectively. |
| Job-related     | If your product is targeted at business, you should say something about their job and (if necessary) what that job involves. For some jobs, such as a teacher where readers are likely to be familiar with the job, this may not be necessary. |
| Education       | You should describe their educational background and their level of technical skills and experience. This is important, especially for interface design. |
| Relevance       | If you can, you should say why they might be interested in using the product and what they might want to do with it. |

### Benefits

- The main benefit of personas is that they help you and other development team members empathize with potential users of the software
- Personas help because they are a tool that allows developers to "step in the user's shoes"
    - Instead of thinking about what you would do in a particular situation, you can imagine how a persona would behave and react
    - Many users of the software you build will not be as technically interested or sophisticate as you, this helps remind you of that!
- Personas can help you check your ideas to make sure that you are not including product featres that are not really needed
- They help you to avoid making unwarranted assumptions, based on your own knowledge, and designing an over-complicated or irrelevant product

### Derivation

- Personas should be uased on an understanding of the potential product users, their jobs, their background, and their aspirations
- You should study and survey potential users to understand what they want and how they might use the product
- From this data, you can then abstract the essential information about the different type of product user and use this as a basis for creating personas
- Personas that are developed on the basis of limited user information are called proto-personas
- **Proto-Persona**
    - created as a collective team exercise using whatever information is available about potential product users; They can bever be as accurate as personas developed from detailed user studies but are better than nothing

## Scenarios

- A scenario is a narrative that describes how a user, or a group of users, might use your system
- There is no need to include everything in a scenario - the scenario is not a system specification
- It is simply a description of a situation where a user is using your product's features to do something they want to do
- Scenario descriptions may vary in length from two to three paragraphs up to a page of text

### Description Elements

- **Scenario Description Elements**
    - Scenario name
    - Overall objective
    - What's involved in reaching the objective
    - Personas of actors involved in the scenarios
    - Problem that cannot be addressed by the existing system
    - Possible ways that the problem could be tackled  

- A brief statement of the overall objective
- References to the personas involved so that you can get information about the capabilities and motivation of the user
- Information about what is involved in doing the activity
- An explanation of problems that cannot be readily addressed using the existing system
- A description of one way that the identified problem might be addressed

### Writing Scenarios

- Scenarios should always be written from the user's perspective and based on identified personas or real users
- Your starting point for scenario writing should be the personas that you have already created; You should normally try to imagine several scenarios from each persona
- Ideally, scenarios should be general and should not include implementation information
    - However, describing an implementation is often the easiest way to explain how a task is done
- It is important to ensure that you have coverage of all of the potential user roles when describing a system

## User Involvement

- It is easy for anyone to read and understand scenarios, so it is possible to get users involved in their development
- The best approach is to develop an imaginary scenario based on our understanding of how the system might be used then ask users to explain what you have got wrong
- They might ask about things they did not understand and suggest how the scenario could be extended and made more realistic
- Author's experience: users are not good at writing their own scenarios

## User Stories

- Scenarios are high-level stories of system use; They should describe a sequence of interactions with the system but should not include details of these interactions
- User stories are finer-grain narratives that set out in a more detailed and structured way <ins>a **single** thing that a user wants from a software system</ins>
    - From Sommerville: *"As an author, I need a way to organize the book that I'm writing into chapters and sections."*
- This story reflects what has become the standard format of a user story:
    - **As a** `role`, I `want | meed` to `do something`
        - *As a teacher, I want to tell all members of my group when new information is available.*
- A variant of this standard format adds a justification for the action:
    - **As a** `role` I `want | need` to `do something` **so that** `reason`
        - *As a teacher, I need to be able to report who is attending a class trip so that the school maintains the required health and safety records.*<br>

- An important part of user stories is in planning
    - Many users of the Scrum method represent the product backlog as a set of user stories
- User stories should focus on a clearly defined system feature or aspect of a feature that can be implemented within a single sprint
- If the story is about a more complex feature that might take several sprints to implement, then it is called an *epic*

### Feature Description Using User Stories

- Stories can be used to describe features in your product that should be implemented
- Each feature can have a set of associated stories that describe how that feature is used

### Stories and Scenarios

- As you can express all of the functionality described in a scenario as user stories, do you really need scenarios?
- Scenarios are more natural and are helpful for the following reasons:
    - Scenarios read more naturally because they describe what a user of a system is actually doing with that system; People often find it easier to relate to this specific information rather than the statement of wants or needs set out in a set of user stories
    - If you are interviewing real users or are checking a scenario with real users, they do not talk in the stylized manner that is used in user stories; People relate better to the more natural narrative in scenarios
    - Scenarios often provide more context - information about what the user is trying to do and their normal ways of working; You can do this in user stories, but it means that they are no longer simple statements about the use of a system feature

## Feature Identification

- Your aim in the initial stage of product design should be to create a list of features that define your product
- A feature is a way of allowing users to access and use your product's functionality so the feature list defines the overall functionality of the system
- Features should be independent, coherent, and relevant:
    - *Independence*
        - Features should not depend on how other system features are implemented and should not be affected by the order of activation of other features
    - *Coherence*
        - Features should be linked to a single item of functionality; They should not do more than one thing and they should never have side effects
    - *Relevance*
        - Features should reflect the way that users normally carry out some task; They should not provide obscure functionality that is hardly ever required

## Feature Design

| **Knowledge Type**     | **Description**                                                                                                            |
|------------------------|----------------------------------------------------------------------------------------------------------------------------|
| **User Knowledge**     | You can use user scenarios and user stories to inform the team of what users want and how they might use the software features. |
| **Product Knowledge**  | You may have experience with existing products or decide to research what these products do as part of your development process. Sometimes your features have to replicate existing features in these products because they provide fundamental functionality that is always required. |
| **Domain Knowledge**   | This is knowledge of the domain or work area (e.g., finance, event booking) that your product aims to support. By understanding the domain, you can think of new innovative ways of helping users do what they want to do. |
| **Technology Knowledge** | New products often emerge to take advantage of technological developments since their competitors were launched. If you understand the latest technology, you can design features to make use of it. |

### Factors

- Automation
- Control
- Familiarity
- Functionality
- Novelty
- Simplicity

### Trade-Offs

- **Simplicity and Functionality**
    - You need to find a balance between providing a simple, easy-to-use system and including enough functionality to attract users with a variety of needs
**Familiarity and Novelty**
    - Users prefer that new software should support the familiar everyday tasks that are part of their work or life; Go encourage them to adopt your system, you need to find a balance between familiar features and new features that convince users that your product can do more than its competitors
- **Automation and Control**
    - Some users like automation, where the software performs automatic processes, but others perfer to have control; You have to think carefully about what can be automated, how it is automated, and how users can configure the automation so that the system can be tailored to their preferences

### Creep

- **Feature Creep**
    - occurs when new features are added in response to user requests without considering whether or not these features are generally useful or whether they can be implemented in some other way
- Too many features make products hard to use and understand
- Three reasons why feature creep occurs:
    - Product managers are reluctant to say "no" when users ask for specific features
    - Developers try to match features in competing products
    - The product includes features to support both inexperienced and experienced users
- There are a few questions we can ask to avoid feature creep:
    - Does this feature really add anything new, or is it simply an alternative way of doing something that is already supported?
    - Is this feature likely to be important to and used by most software users?
    - Does this feature provide generic functionality or is it a very specific feature?
    - Can this feature be implemented by extending an existing feature rather than adding another feature to the system?

### Derivation

- Features can be identified directly from the priduct vision or from scenarios
- You can highlight phrases in narrative description to identify features to be included in the software
    - You should think about the features needed to support user actions, identified by active verbs, such as **use** and **choose**

### Features from the Product Vision

- A feature that allows users to access and use existing web-based resources
- A feature that allows the system to exist in multiple different instantiations
- A feature that allows user configuration of the system to create a specific instantiation

### The Feature List

- The output of the feature identification process should be a list of features that you use for designing and implementing your product
- There is no need to go into a lot of detil about the features at this stage; You add detail when you are implementing the feature
- You can describe features using a standard input-action-output template by using structured narrative descriptions or by a set of user stories

## Innovation and Feature Identification

## Exercises
