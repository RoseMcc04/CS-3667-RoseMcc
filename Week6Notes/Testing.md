# Testing

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [What is Software Testing?](#what-is-software-testing)
2. [Software Testing: Important Points](#software-testing-important-points)
3. [Terminology](#terminology)
    1. [Failures](#failures)
    2. [Faults, Defects, and Errors](#faults-defects-and-errors)
4. [Levels of Testing](#levels-of-testing)
5. [Purposes of Testing](#purposes-of-testing)
6. [Why Automate?](#why-automate)
    1. [Why might automation be difficult?](#why-might-automation-be-difficult)
    2. [Automation Challenges](#automation-challenges)
    3. [Standard Automation Testing Steps](#standard-automated-testing-steps)
        1. [Fixture Setup](#fixture-setup)
        2. [Exercise SUT](#exercise-sut)
        3. [Result Verification](#result-verification)
        4. [Fixture Teardown](#fixture-teardown)
7. [Test Cases and Testing Frameworks](#test-cases-and-testing-frameworks)
8. [Keeping Unit Tests Atomic](#keeping-unit-tests-atomic)
9. [Mocks/Test Doubles](#mockstest-doubles)
10. [Unit Testing](#unit-testing)
    1. [White Box vs. Black Box Testing](#white-box-vs-black-box-testing)
    2. [Coming up with Tests](#coming-up-with-tests)
11. [Equivalence Partitioning and Boundary Analysis](#equivalence-partitioning-and-boundary-analysis)
    1. [Equivalence Partitions](#equivalence-partitions)
12. [System and Release Testing](#system-and-release-testing)
13. [Scenario-Based Testing](#scenario-based-testing)
14. [Release Testing](#release-testing)
15. [Code Reviews](#code-reviews)

## What is Software Testing?

- Let's open the SWEBOK *(Software Engineering Body of Knowledge)*
- *"Software testing consists of the dynamic verification that a program provides expected behaviors on a finite set of test cases, suitably selected from the usually infinite execution domain."*

## Software Testing: Important Points

- *"Software testing consists of the **dynamic** verification that a program provides expected behaviors on a finite set of test cases, suitably selected from the usually infinite execution domain."*
    - Dynamic: testing involves running the program, gives *inputs* and some *program state*
    - Inputs: what values do we give to the running part of the system?
    - Program state: what should be true of the world (including the system) when the test is run?
        - *Examples: is a user already logged in? are there items in the shopping cart?*
    - Finite: the number of needed tests could be many more than we can realistically run, or could even be infinite
        - So, we only run a certain number of tests
    - Goal: tests we run use a representative set of values - we want a test to represent many different inputs, since we cannot test them all
    - Selected: since we have only finite time, and can only run a finite number of tests, we need to select which tests to run
        - Different testing methodologies give us different ways of selecting tests
        - How should we select tests?
        - What impact does this have?
    - Expected: we need a way to know if a test is correct, so we have to compare what happens when we run the test against what should happen
        - Is this easy? Hard? What factors influence this? Why may it be hard (you wrote the code, why wouldn't you know what it is supposed to do?)

## Terminology

### Failures

- A failure occurs when the program fails to perform a required function or fails to perform it within specified limits (ISO/IEC/IEEE 24765)
- *Note: see page 139 of the standards doc*

### Faults, Defects, and Errors

- A fault (we often call it a bug) is unearthed when a failure occurs, but can also refef it to an undiscovered problem in the program (ISO/IEC/IEEE 24765, p140)
- *"If a tree falls in the forest..."*
- Put these together: software failures and faults
- Defect: umbrella category for failures and faults
- Error: human action that produces an incorrect result

## Levels of Testing

- Unit testing
    - *"Unit testing verifies the functioning in isolation of software pieces which are separately testable. Depending on the context, these could be the inividual subprograms or a larger component made of tightly related units."*
- Integration testing
    - *"the process of verifying the interaction between software components", generally done at different levels, focused on different subsystems, versus all at once*
- System testing
    - *"concerned with the behavior of a whole system", gives an opportunity to also test non-functional properties (e.g., performance)*

## Purposes of Testing

| Test Type                  | Testing Goals                                                                                  |
|----------------------------|-----------------------------------------------------------------------------------------------|
| Functional testing          | Test the functionality of the overall system. The goals are to find bugs and ensure the system is fit for its intended purpose. |
| User testing                | Ensure the software is useful and usable by end-users. Demonstrate that users understand how to use the features effectively.     |
| Performance and load testing| Test the system's response time, processing speed, and ability to handle expected user loads. Show that the system scales gracefully under load. |
| Security testing            | Ensure the system maintains integrity and protects user information from theft or damage.                                          |

## Why Automate?

- Run more quickly
- Run more often (enabled by the previous point)
- Integrate with standard build process (part of many agile methods)
- Use tests as lightweight specifications of behavior, build programs around tests (TDD)
- Provide almost real-time checks with distributed project teams (continuous integration)
- Ensure changes do not break existing code, old bugs do not reappear

### Why might automation be difficult?

- *Not sure, let's look at the challenges*

### Automation Challenges

- Poor software decomposition
- Difficulty in providing test oracles
- Difficulty in testing systems with complex interactions (how do you test components that rely on many other components?)
- How do you simulate interfacts meant for humans (GUIs in desktop apps, web-based interfaces)
- Any others?

### Standard Automated Testing Steps

- Fixture Setup
- Exercise SUT
- Result Verification
- Fixture Teardown

#### Fixture Setup

- Simple code may just need to be called
- What happens when we have more complicated code with more dependencies?
- A test fixture provides the context needed to execute the code
- *"Everything a system under test (SUT) needs to have in place so that we can exercise the SUT for the purpose of verifying its behavior.", xUnit Test Patterns: Refactoring Test Code*

#### Exercise SUT

- SUT = System Under Test
- This is the part of the system we are actually testing (a specific method, an entire class, a component consisting of multiple classes, or the entire system)
- This part of the system is exercised (i.e., run) by a test case
- The testing framework collects the results of the test

#### Result Verification

- During execution, need to collect information needed to know if SUT works correctly
- Result verification = checking to ensure the result is correct
- Test oracle: determines if test is correct
- As we mentioned above, finding a suitable oracle is not always easy...

#### Fixture Teardown

- After execution and verification, need to clean up, set state back to what it was at the start
- This process is called "fixture teardown"
- What challenges can this bring?

## Test Cases and Testing Frameworks

- Testing Framework: JUnit, PHPUnit, Casperjs, Esprsso, etc. - a framework (tool or set of tools) for automating testing
- Test Case: set of related test methods
- Test Method: a specific test to execute
- Note: this does not seem to be standard, a test case used to be what we now call a test method (smallest unit of testing), this may be inconsistent in what you are reading, so check! (These terms are from JUnit)
- Test Suite: all the test cases we want to run

## Keeping Unit Tests Atomic

- One challenge in setting up fixture: how do we model other components with complex state and behavior?
- Want to be able to test code independently of other classes
- Any ideas?

## Mocks/Test Doubles

- One challenge in setting up fixture: how do we model other components with complex state and behavior?
- Want to be able to test code independently of other classes
- Want repeatable tests
- What if we could create "fake" instances of classes that be

## Unit Testing

### White Box vs. Black Box Testing

- White box testing: testing based on characteristics of the code
- Black box testing: testing based on the specification of the code
- *Note: If you want to measure how much of the code you actually test, you need to use white-box techniques*

### Coming up with Tests

- Start with requirements: should have at least one test per requirement (why?)
- Also look at design, each major design concern should be included
- Use information on code structure (see below) to make sure tests are effective at exercising code
- Keep a checklist of standard errors - learn from prior experience 

## Equivalence Partitioning and Boundary Analysis

- *Do we need to test every possible value?*
- Not usually, this would be prohibitive
- Say we have three possible behaviors, one when the input is < 0, one when the input is 0 <= input <= 100, and one when the input is > 100
- Equivalence partitioning: uses concept of equivalence classes, we can treat values in same class as equivalent, no need to test each
- Boundary analysis: focus specifically on boundary values, what are they for this example?

### Equivalence Partitions

![Equivalence Partition Diagram](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQEYBpB6ESGsCr41h0OXGPmtn_BRSGvZr_mIQ&s)

## System and Release Testing

- System testing involves testing the system as a whole, rather than the inividual system features
- System testing should focus on four things:
    - Testing to discover if there are unexpected and unwanted interactions between the features of a system
    - Testing to discover if the system features work together effectively to support what users really want to do with the system
    - Testing the system to make sure it operates in the expected way in the differentt environments where it will be used
    - Testing the responsiveness, throughput, security, and other quality attributes of the system

## Scenario-Based Testing

- The best way to systematically test a system is to start with a set of scenarios that describe possible uses of the system and then work through these scenarios each time a new version of the system is created
- Using the scenario, you identify a set of end-to-end pathways that users might follow when using the system
- An end-to-end pathway is a sequence of actions from starting to use the system for the task, through to completion of the task 

## Release Testing

- Release testing is a type of system testing where a system that is intended for release to customers is tested
- The fundamental differences between release testing and system testing are:
    - Release testing tests the system in its real operational environment rather in a test environment. Problems commonly arise with real user data, which is sometimes more complex and less reliable than test data
    - The aim of release testing is to decide if the system is good enough to release, not to detect bugs in the system. Therefore, some tests that "fail" may be ignored if these hav minimal consequences for most users
- Preparing a system for release involves packaging that system for development (e.g. in a container if it is a cloud service) and installing software and libraries that are used by your product. You must define configuration parameters such ad the name of a roott directory, the database size limit per user, and so on

## Code Reviews

- Code reviews involve one or more people examining the code to check for errors and anomalies and discussing issues with the developer
- If problems are identified, it is the developer's responsibility to change the code to fix the problems
- Code reviews complimnt testing. They are effective in finding bugs that arise through misunderstandings and bugs that may only arise when unusual sequences of code are executed
- Many software companies insist that all code has to go through a process of code review before it is integrated into the product codebase

![Code Review Diagram](https://www.researchgate.net/publication/328541762/figure/fig1/AS:686040184528896@1540576134082/Overview-of-the-Code-Review-Process.png)
