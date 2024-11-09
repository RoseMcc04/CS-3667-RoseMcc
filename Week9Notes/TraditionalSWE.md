# Traditional Software Engineering

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [Class Modeling](#class-modeling)
    1. [Terminology](#terminology)
    2. [Relationships](#relationships)
    3. [Finding Classes](#finding-classes)
2. [Textual Analysis Guidelines](#textual-analysis-guidelines)
3. [CRC Cards](#crc-cards)
    1. [Responsibilities, Collaborations](#responsibilities-collaborations)
    2. [Checking Class Definitions](#checking-class-definitions)
    3. [Example](#example)
4. [UML Class Diagrams](#uml-class-diagrams)
5. [Elements of Class Diagrams](#elements-of-class-diagrams)
    1. [Classes](#classes)
    2. [Attributes and Operations](#attributes-and-operations)
    3. [Relationships](#relationships-1)
    4. [Sample Associations](#sample-associations)
    5. [Multiplicities](#multiplicities)
    6. [Association Classes](#association-classes)
    7. [Sample Aggregations](#sample-aggregations)
    8. [Sample Compositions](#sample-compositions)
6. [Behavioral Diagrams](#behavioral-diagrams)
    1. [Sequence Diagrams](#sequence-diagrams)
        1. [Example](#example-1)
    2. [Communication Diagrams](#communication-diagrams)
        1. [Example](#example-2)
    3. [State Machine Diagrams](#state-machine-diagrams)
        1. [Example](#example-3)

## Class Modeling

### Terminology

- **Class**
    - a template for building objects
        - Concrete classes cans be used to create objects
        - Abstract classes are useful abstractions, but do not 
        directly represent real-world objects
        - *Examples: Person, Student, Instructor*
- **Attribute**
    - a piece of information related to the class (called 
    attributes, fields, or properties in various languages)
- **Operation**
    - actions that perform some sort of functionality (called 
    functions or methods in most languages)

### Relationships

- **Generalization** 
    - also known as inheritance, `is-a` oe `a-kind-of` relationships *(e.g., a Dog is an Animal, a Dog is a kind of Animal)*
- **Aggregation**
    - represents parts of wholes or assemblies, `a-part-of` or `has-parts` *(e.g., an Engine is a part of a Car)*
- **Association**
    - weaker link between two classes, not an aggregation because each part is its own thing *(e.g., a Patient is associated with an Appointment)*
- One rule of thumb: does the item make sense without the item it is associated to?

### Finding Classes

- **Textual analysis**
    - examine use-case diagrams, use-case descriptions, looking for classes, attributes, operations, and relationships
- **Brainstorming**
- **Common object lists**
    - *(lists of objects commonly found in specific domains)*
- **Patterns**

## Textual Analysis Guidelines

- A common or improper noun implies a class of objects 
- A proper noun or direct reference implies an instance of a class 
- A collective noun implies a class of objects made up of groups of instances of another class 
- An adjective implies an attribute of an object 
- A doing verb implies an operation 
- A being verb implies a classification relationship between an object and its class 
- A having verb implies an aggregation or association relationship 
- A transitive verb implies an operation 
- An intransitive verb implies an exception 
- A predicate or descriptive verb phrase implies an operation 
= An adverb implies an attribute of a relationship or operation 

## CRC Cards

- CRC (Class - Responsibility - Collaboration) cards document classes and their relationships 
- Also provide a good way for checking current class definitions, making sure you are not missing anything 

### Responsibilities, Collaborations

- **Knowing responsibilities**
    - what things is the class responsible for knowing?
- **Doing responsibilities**
    - what things is the class responsible for doing? 
- **Collaborations**
    - how do instances of different classes collaborate/interoperate to accomplish some task 

### Checking Class Definitions

- Get team members to pretend they are instances of each card/class, try to solve tasks 
- Ask questions of each team member 
    - *Who or what are you?*
    - *What do you know?*
    - *What can you do?*
- Role-play through each scenario, see where you get stuckL this is something that is not already modeled as part of the class that you may need 

### Example

![CRC Card Diagram](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR15bEQelPXwmvBrDBQ7vLxwxaKvY7hsOCs8w&s)

## UML Class Diagrams

## Elements of Class Diagrams

### Classes

### Attributes and Operations

### Relationships

### Sample Associations

### Multiplicities

### Association Classes

### Sample Aggregations

### Sample Compositions

## Behavioral Diagrams

### Sequence Diagrams

#### Example

### Communication Diagrams

#### Example

### State Machine Diagrams

#### Example
