# Reliable Programming

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [Introducing Design Patterns](#introducing-design-patterns)
    1. [What is a design pattern?](#what-is-a-design-pattern)
    2. [What makes up a design pattern?](#what-makes-up-a-design-pattern)
    3. [A sample pattern: Observer](#a-sample-pattern-observer)
2. [Categories of Patterns](#categories-of-patterns)
    1. [The Factory Pattern](#the-factory-pattern)
        1. [Where should you use a factory?](#where-should-you-use-a-factory)
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
        2. [Origin 2: Opdyke and Johnson](#origin-2-opdyke-and-johnson)
        3. [Restructure: Some Points](#restructure-some-points)
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

### The Factory Pattern

#### Where should you use a factory?

### The Singleton Pattern

#### Why the singleton pattern?

### The State Pattern

### The Composite Pattern

### The Interpreter Pattern

### The Visitor Pattern

#### Interpreter vs. Visitor Patterns

## When should you use design patterns?

## Refactoring

### What is refactoring?

### What is not refactoring?

### Origins of Refactoring

#### Origin 1: Griswold and Notkin

#### Origin 2: Opdyke and Johnson

#### Restructure: Some Points

### Differences in Approaches

### The Two Challenges

#### Dealing with Challenge 1: Code Smells

##### Examples of Code Smells

##### How do we detect code smells?

#### Dealing with Challenge 2: Program Analysis

## The Importance of Testing