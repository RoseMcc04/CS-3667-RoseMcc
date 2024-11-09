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

- A `common or improper noun` implies a class of objects 
- A `proper noun` or `direct reference` implies an instance of a class 
- A `collective noun` implies a class of objects made up of groups of instances of another class 
- An `adjective` implies an attribute of an object 
- A `doing verb` implies an operation 
- A `being verb` implies a classification relationship between an object and its class 
- A `having verb` implies an aggregation or association relationship 
- A `transitive` verb implies an operation 
- An `intransitive` verb implies an exception 
- A `predicate` or `descriptive verb phrase` implies an operation 
- An `adverb` implies an attribute of a relationship or operation 

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

![UML Class Diagram](https://agiledata.org/wp-content/uploads/2023/04/oo1013ONF.gif)

## Elements of Class Diagrams

### Classes

- Represent the classes in the system: domain classes at this point, more detailed classes once we are in design 
- Include attributes and operations, but not those that are part of all classes 
- *Note: we can leave information out and these are still valid!* <br>

![Class Example](https://cdn-proxy.slickplan.com/wp-content/uploads/2023/10/5_uml.png)
<br>

### Attributes and Operations

- Properties (either stored or derived), or actions/functions that can be performed
- **An attribute:**
    - Represents properties that describe the state of an object 
    - Can be derived from other attributes, shown by placing a slash before the attribute's name <br>
![Attribute Example](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/04-class-attributes-with-different-visibility.png)
<br>
- **An operation:**
    - Represents the actions or functions that a class can perform
    - Can be classified as a constructor, query, or update operation 
    - Includes parentheses that may contain parameters or information needed to perform the operation <br>

![Operation Example](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/03-class-notation-with-examples.png)
<br>

### Relationships

- **An association:**
    - Represents a relationship between multiple classes or a class and itself
    - Is labeled using a verb phrase or a role name, whichever better represents the relationship 
    - Can exist between one or most classes 
    - Contains multiplicity symbols, which represent the minimum and maximum times a class instance can be associated with the related class instance
- **A generalization:**
    - Represents `a-kind-of` relationship between multiple classes 
- **An aggregation:**
    - Represents a logical `a-part-of` relationship between multiple classes or a class and itself 
    - Is a special form of an association 
- **A composition:**
    - Represents a physical `a-part-of` relationship between multiple classes or a class and itself 
    - Is a special form of an association <br>
![UML Relationships Diagram](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/07-relationships-between-classes.png)
<br>

### Sample Associations

![Sample Association](https://i.sstatic.net/Idffa.png)

### Multiplicities

![Multiplicity Diagram](https://slideplayer.com/slide/13005053/79/images/33/Multiplicity+PowerPoint+Presentation+for+Dennis,+Wixom,+&+Roth+Systems+Analysis+and+Design,+3rd+Edition..jpg)

### Association Classes

- Allow information about an association to be stored 
- Very common, actually quite rare to have a true many to many relationship without such a class 
- *Example: each student, in each course, will have a grade, Grade class provides a place for this* <br>
![Association Classes Example](https://www.researchgate.net/publication/243692015/figure/fig3/AS:667660601815045@1536194100533/An-example-of-the-association-notation-in-UML-class-diagrams.png)
<br>

### Sample Aggregations

- Logical relationship 
- Classes are logically linked to one another 
- Instances of these classes make sense on their own (I can take a wheel off a car, a desk out of an office), can be linked to multiple classes <br>
![Sample Aggregation Example](https://www.cplusoop.com/uml/module4/images/m4l8-01.gif)
<br>

### Sample Compositions

- Physical relationship 
- Classes are physically part of one another 
- Instances do not make sense on their own, or cannot be easily be removed from a single related instance 
- "Ownership" <br>
![Sample Composition Example](https://i.sstatic.net/n60US.png)
<br>

## Behavioral Diagrams

- Sequence diagrams 
- Communication diagrams 
- State machine diagrams 
- CRUDE matrices 

### Sequence Diagrams

- Used to illustrate how actors and objects communicate in specific user-case scenarios
- Considered an "interaction" diagram - focused specifically on interactions 
- Requirements: we keep this high-level, can also used in design with objects representing lower-level entities *(e.g., specfic database classes)* 

#### Example

![Sequence Diagram Example](https://i.sstatic.net/RTchP.png)

### Communication Diagrams

- Another "interaction" diagram - showing how different parts of the system interact 
- Higher-level than sequence diagrams, shows possible interactions between actors and objects, does not limit these to specific scenarios 
- Good at showing dependencies between objects, how objects exchange messages (method calls) 

#### Example

![Communication Diagram Example](https://webusupload.apowersoft.info/gitmind/wp-content/uploads/2021/07/web-store-communication-diagram.jpg)

### State Machine Diagrams

- Used to model the state of a system/object that maintains state through various operations that can change this state 
- These are often objects that represent real-world systems, such as hardware systems or real-life processes 
- States represent the different states (values of attributes, potentials for behavior) that the object can be in 
- Transitions allow for movement between states 
- Events trigger transitions 

#### Example

![State Machine Diagram Example](https://agilemodeling.com/wp-content/uploads/2023/04/stateMachineSeminarComplete.jpg)
