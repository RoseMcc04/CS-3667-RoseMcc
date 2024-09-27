# Reliable Programming

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [Introducing Design Patterns](#introducing-design-patterns)
    1. [What is a design pattern?](#what-is-a-design-pattern)
    2. [What makes up a design pattern?](#what-makes-up-a-design-pattern)
    3. [A sample pattern: Observer](#a-sample-pattern-observer)
2. [Categories of Patterns](#categories-of-patterns)
    1. [The Factory Pattern](#the-factory-pattern)
        1. [Where should you use a factory?](#when-should-you-use-a-factory)
    2. [The Singleton Pattern](#the-singleton-pattern)
        1. [Why the singleton pattern?](#why-the-singleton-pattern)
    3. [The State Pattern](#the-state-pattern)
    4. [The Composite Pattern](#the-composite-pattern)
    5. [The Interpreter Pattern](#the-interpreter-pattern)
    6. [The Visitor Pattern](#the-visitor-pattern)
        1. [Interpreter vs. Visitor Patterns](#interpreter-vs-visitor-patterns)
3. [When should you use design patterns?](#when-should-you-use-design-patterns)
4. [Refactoring](#refactoring)
    1. [What is refactoring?](#what-is-refactoring)
    2. [What is not refactoring?](#what-is-not-refactoring)
    3. [Origins of Refactoring](#origins-of-refactoring)
        1. [Origin 1: Griswold and Notkin](#origin-1-griswold-and-notkin)
        2. [Restructure: Some Points](#restructure-some-points)
        3. [Origin 2: Opdyke and Johnson](#origin-2-opdyke-and-johnson)
        4. [Origin 2: Some Points](#origin-2-some-points)
    4. [Differences in Approaches](#differences-in-approaches)
    5. [The Two Challenges](#the-two-challenges)
        1. [Dealing with Challenge 1: Code Smells](#dealing-with-challenge-1-code-smells)
            1. [Examples of Code Smells](#examples-of-code-smells)
            2. [How do we detect code smells?](#how-do-we-detect-code-smells)
        2. [Dealing with Challenge 2: Program Analysis](#dealing-with-challenge-2-program-analysis)
5. [The Importance of Testing](#the-importance-of-testing)

## Introducing Design Patterns

*"Each pattern describes a problem which occurs over and over again in our environment, and then describes the core of the solution to that problem, in such a way that you can use this solution a million times over, without ever doing it in the same way twice."* - Christopher Alexander, *A Pattern Language*

### What is a design pattern?

- **Design Pattern**
    - a way of reusing abstract knowledge about a problem and its solution
- **Pattern**
    - a description of the problem and the essence of its solution
- It should be sufficiently abstract to be reused in different settings!
- Note: *patterns generally make heavy use of OO features like inheritance and polymorphism, so most work on patterns has been in the OO context (not C, Lisp, etc.)*

### What makes up a design pattern?

- **Pattern name**
    - used to discuss the pattern
- A description of the **problem**
- A description of the **solution** to the problem, described in terms of design elements, relationships between these elements, responsibilities, and collaborations, but not in terms of *concrete* solutions (this should be reusable!)
- The **consequences** (good and bad) of using the pattern

### A sample pattern: Observer

- **Name:** Observer
- **Problem Description:** Multiple displays of the same state are needed
- **Solution Description:** A subject contains state and allows observers to register their interest in state changes. Changes to the state result in an update message to each registered observer. The observers all implement a standard interface. 
- **Consequences:** Low coupling, but performance could suffer because the subject does not know details of the observer.

![Observer Pattern](https://sourcemaking.com/files/v2/content/patterns/Observer.png)

## Categories of Patterns

- **Creational Patterns**
    - Patterns that deal with how objects are created

![Creational Pattern Example](https://sourcemaking.com/files/v2/content/patterns/Abstract_Factory_example1.png)

- **Structural Patterns**
    - Patterns that deal with relationships between entities

![Structural Pattern Example](https://sourcemaking.com/files/v2/content/patterns/Decorator-preview-2x.png)

- **Behavioral Patterns**
    - Patterns that exemplify common communication patterns between objects

![Behavioral Pattern Example](https://sourcemaking.com/files/v2/content/patterns/Interpreter_example1.png)

### The Factory Pattern

- This is a *creational pattern*
- A **factory method** creates an object

![Factory Method Image](https://sourcemaking.com/files/v2/content/patterns/Factory_Method.png)

- A **factory class** provides a number of factory methods
- Related concept: *an **abstract factory** creates families of related objects, with different instances for different families*

![Abstract Factory Class Image](https://sourcemaking.com/files/v2/content/patterns/Abstract_Factory.png)

#### When should you use a factory?

- If you want to abstract from the specific implementation
- If you have related families of types and want to ensure they are consistently related
- Related concept: **builder**

![Builder Image](https://sourcemaking.com/files/v2/content/patterns/Builder_example1.png)

- Related concept: **prototype**
    - Note: *actually used in some languages in place of classes (e.g., JavaScript)*

![Prototype Image](https://sourcemaking.com/files/v2/content/patterns/Prototype_example1.png)

### The Singleton Pattern

- This is a *creational pattern*
- **Challenge**
    - we want to ensure we only have one instance of a given class available and make it easily available

![Singleton Example Pic](https://sourcemaking.com/files/v2/content/patterns/Singleton_example1.png)

- **Solution**
    - use a factory method (note: these are static, why?) to create the object and make the constructor private
- This may create the obejct in advance, or it may do so lazily, waiting until it is forst needed

#### Why the singleton pattern?

- Lower memory usage
- Ability to choose appropriate class to instantiate at runtime
- Ability to properly set up this class (since we do not just use the constructor)
- Can make the instance globally available

### The State Pattern

- This is a *behavioral pattern*
- **Challenge**
    - use different representations at different times for the same data type
- **Solution**
    - separate the *context*, representing the data type from the *state type*, representing the internal state (e.g., a List type, with state for an empty list, a single value, or an arbitrary numbero of values)

![State Pattern Image](https://sourcemaking.com/files/v2/content/patterns/State_example1.png)

### The Composite Pattern

- This is a *structural pattern*
- Used for tree-like structures, hierarchies with internal and leaf nodes: file systems (directories, files), GUIs, programming languages (expressions with sub-expressions, literals), etc.
- Abstract base class defines expected behavior, internal nodes handle children, internal nodes and leaf nodes both implement behavior

![Composite Pattern Image](https://sourcemaking.com/files/v2/content/patterns/Composite_example1.png)

### The Interpreter Pattern

- This is a **behavioral pattern**
- Use when you can model your problem as a language (or something with similar structure) that you can "run"
- Works with the composite pattern, problem generally is hierarchically structured, solving it involves recursing over this structure

![Interpreter Pattern Image](https://sourcemaking.com/files/v2/content/patterns/Interpreter1.png)

### The Visitor Pattern

- This is a *behavioral pattern*
- Similar to interpreter in concept, but we separate our the traversal logic (included in the composite classes) from the specific operation we are performing (defined inside the Visitor class)
- Composites *accept* a Visitor, handle their own structure; Visitors use values to perform some sort of computation
- Different Visitors are used for different operations, versus defining different interpret methods for this using the interpreter pattern

![Visitor Pattern Image](https://sourcemaking.com/files/v2/content/patterns/Visitor_example1.png)

#### Interpreter vs. Visitor Patterns

- Visitor is more confusing, interpreter is conceptually easier to understand (and thus probably easier to maintain)
- Interpreter is easier when you are adding new language constructors (just add new interpret methods!), harder when adding new operations (need to touch every class)

## When should you use design patterns?

- Do not over-engineer: use them when they are helpful
    - They can improve performance or flexibility
    - They often increase complexity at the same time
- Use them during design as discussion points
    - Patterns provide a vocabulary for design
    - Recognized patterns can make code easier to understand
- Hint: *learn them so you recognize them when you see them, can use them for your own designs - read sites like [Sourcemaking](https://sourcemaking.com/) and look at books on this topic!*

## Refactoring

### What is refactoring?

- *"Code refactoring is the process of restructuring existing computer code ... changing the factoring ... without changing its external behavior."* - [Refactoring Wikipedia](https://en.wikipedia.org/wiki/Code_refactoring)

### What is not refactoring?

- Adding new functionality to a program
- Fixing bugs
- Is changing a program to use safer libraries refactoring? Why or why not?

### Origins of Refactoring

- Unclear where the term first came from
- Also unclear when it first started - to some extent, people have been refactoring for as long as they have been programming
- Two research pairs focused on this and made it promiment:
    - Griswold and Notkin (University of Washington)
    - Opdyke and Johnson (University of Illinois at Urbana-Champaign)

#### Origin 1: Griswold and Notkin

- Motivating problem: how do we modify deployed applications?
    - Initial solution allowed functionality to be added to extend the app
    - Results in a different architecture than what would have been created if extensions known in advance (why?)
- Question: can a program be restructured in a way that changes the design but does not change the behavior?
- Result was the Restructure tool for refactoring scheme

#### Restructure: Some Points

- Restructure worked over Program Dependence Graphs (PDGs), which encode control and data flow dependencies
    - Control flow: loops, conditionals, etc.
    - Data flow: how data flows through program statements, which data reaches what places
- Guarded transformations: must meet preconditions first
- Refactoring as graph transformation

#### Origin 2: Opdyke and Johnson

- Motivating problem: how do we evolve real software?
- Opdyke wanted a "macro" focus, but Johnson had a "micro" focus
- This resulted in evolution (macro) through a sequence of small (micro) changes
- One big question: how do we reuse abstractions that are tangled with specifics of the application domain?
- Approach: mine actual changes from existing software

#### Origin 2: Some Points

- Decided to focus on C++, not Smalltalk (why?)
- Came iip with a collection of transformations, some bigger and some very focused
- Investigated safe application: refactoring should not change meaning of code (deciding which to apply still being investigated)
- Approach based on code equivalence, cannot change meaning - not decidable in general, but often is in real systems
- Equivalence based on invariants of transformation

### Differences in Approaches

- Griswold: focused on the semantics, what it means for a refactoring to be meaning-preserving
- Opdyke: focused more on OO aspects and real-world systems, e.g., pushing methods up and down the inheritance hierarchy
- Many other tools and systems for this now, with support for lots of languages and some fairly involved refactoring scripts

### The Two Challenges

- What two challenges do you see with actually doing refactoring?
    - Challenge 1: How do we know where to refactor (and can we automate this)?
    - Challenge 2: How do we know a refactoring is safe (and can we automate this)?

#### Dealing with Challenge 1: Code Smells

- A funny phrase for structures or patterns in the code that "suggest...the possibility of refactoring"
- Note: *these are not bugs!*
- They are structural problems in the code that could make it harder to ensure quality and evolve the system over time

##### Examples of Code Smells

- Duplicated code
- Longer methods
- Larger classes
- Divergent changes
- Shotgun surgery
- Feature envy

##### How do we detect code smells?

- Manually: this is a matter of gaining experience
- Automatically: many tools now attempt to do this, but this is not an easy problem (why?)

#### Dealing with Challenge 2: Program Analysis

- Program analysis lets us encode rules about when a refactoring is safe (preconditions, invariants) and check these on the code
- Not easy! And some languages are harder than others

## The Importance of Testing

- We need a way to ensure our changes do not break anything ... and we will be making lots of changes!
- Automated testing gives us confidence that we are not breaking anything when we change the code!
