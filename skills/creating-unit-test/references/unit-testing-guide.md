# Unit Testing: Detailed Guide

## Overview

Unit testing validates individual components in isolation. It sits at the base of the testing pyramid and is the fastest, least expensive form of testing.

## What is Unit Testing?

Unit testing is a software testing method in which individual components or modules of an application are tested in isolation to verify their correctness. The main purpose is to ensure each unit works correctly for different input conditions and to catch bugs early.

## Why Perform Unit Testing?

- Ensure individual pieces of code work as intended.
- Catch bugs early before they grow into bigger issues.
- Simplify fixing problems during development.
- Improve reliability from the start of the project.
- Reduce defects in later testing stages.

## What are Unit Tests?

A unit test is a test case that validates the behavior of a given unit (function, method, class) by providing input values and verifying the output.

Typical structure: Arrange-Act-Assert (AAA).

- Arrange: Set up test environment and inputs.
- Act: Call the unit under test.
- Assert: Compare actual and expected outcomes.

## Prerequisites for Unit Testing

- Clear requirements for each unit's behavior.
- Modular code organized into small, testable units.
- A suitable testing framework (e.g., JUnit, pytest, NUnit, TestNG).
- Mocking tools for external dependencies.
- Automation setup to run tests consistently.

## Unit Testing Strategies

1. Test-Driven Development (TDD): Write tests before implementation to drive design.
2. Behavior-Driven Development (BDD): Focus on behavior in natural language specs.
3. Mocking and Stubbing: Replace external dependencies to isolate the unit.

## Unit Testing Process

1. Analyze the code and identify what to test.
2. Write test cases, including edge and error cases.
3. Set up the test environment (framework, mocks/stubs).
4. Execute the tests and debug failures.
5. Run tests again to ensure stability after changes.
6. Review results and iterate.

## Application Unit Testing

Apply unit testing principles to components within a larger application. Early validation helps avoid costly defects later and is commonly automated in CI pipelines.

## Unit Testing Techniques

1. Structural Testing (White Box): Verify internal structure and flow.
2. Functional Testing (Black Box): Validate features based on inputs and outputs.
3. Error-Based Testing: Focus on common error patterns (e.g., mutation testing, fault seeding).

## Mocking and Stubbing

Mocking and stubbing isolate a unit by replacing dependencies with controlled versions.

- Mocking: Simulate a dependency and verify interactions (calls, parameters).
- Stubbing: Provide fixed responses to dependency calls.

Use mocking to confirm interactions and stubbing to supply controlled inputs.

## Best Practices

- Write tests during development, not after.
- Avoid logic in tests; keep them simple and focused.
- Ensure tests are independent with their own setup/teardown.

## Unit Test Principles

- Fast: tests must execute quickly (milliseconds).
- Independent: tests must not depend on each other or on execution order.
- Repeatable: tests must be deterministic and produce the same result every time, in any environment.
- Self-validating: tests must clearly report pass/fail without manual log inspection.
- Timely: tests must be written together with the code change, not postponed.
