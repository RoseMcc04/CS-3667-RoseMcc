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
8. [Test Cases and Testing Frameworks](#test-cases-and-testing-frameworks)
9. [Keeping Unit Tests Atomic](#keeping-unit-tests-atomic)
10. [Mocks/Test Doubles](#mockstest-doubles)
11. [Unit Testing](#unit-testing)
    1. [White Box vs. Black Box Testing](#white-box-vs-black-box-testing)
    2. [Coming up with Tests](#coming-up-with-tests)
12. [Equivalence Partitioning and Boundary Analysis](#equivalence-partitioning-and-boundary-analysis)
    1. [Equivalence Partitions](#equivalence-partitions)
13. [System and Release Testing](#system-and-release-testing)
14. [Scenario-Based Testing](#scenario-based-testing)
15. [Release Testing](#release-testing)
16. [Code Reviews](#code-reviews)

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

### Why might automation be difficult?

### Automation Challenges

### Standard Automated Testing Steps

#### Fixture Setup

#### Exercise SUT

#### Result Verification

#### Fixture Teardown

## Test Cases and Testing Frameworks

## Keeping Unit Tests Atomic

## Mocks/Test Doubles

## Unit Testing

### White Box vs. Black Box Testing

### Coming up with Tests

## Equivalence Partitioning and Boundary Analysis

### Equivalence Partitions

## System and Release Testing

## Scenario-Based Testing

## Release Testing

## Code Reviews
