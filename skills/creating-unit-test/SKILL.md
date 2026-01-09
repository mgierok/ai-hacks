---
name: creating-unit-test
description: Create or improve unit tests as black-box checks using AAA and FIRST principles, with mocks/stubs for external dependencies. Use when asked to add unit tests, design test cases, or explain unit testing strategies, processes, or best practices.
---

# Creating Unit Tests

## Overview

Use this skill to design and write unit tests that validate individual units in isolation. Focus on observable behavior, keep tests fast, and use mocks or stubs to replace external dependencies.

## Core Rules

- Treat the unit under test as a black box. Analyze only inputs and outputs.
- Follow FIRST: keep tests fast, independent, repeatable, self-validating, and timely.
- Use Arrange-Act-Assert (AAA). Allow exactly one action in Act.
- Verify one behavior per test; write multiple tests to cover distinct behaviors.
- Assert observable behavior, not internal implementation details.
- Avoid real databases, network calls, and filesystem access. Use mocks, stubs, or fakes; keep tests in memory.

## Workflow

1. Analyze the unit, its inputs, and expected outputs. Identify normal, edge, and error cases.
2. Draft test cases for each behavior and boundary condition.
3. Set up the test environment (framework, fixtures, mocks/stubs/fakes).
4. Execute tests, fix failures, and rerun to confirm stability.
5. Review results and keep tests minimal, readable, and maintainable.

## Strategies and Techniques

- Apply mocking to verify interactions and parameters; apply stubbing to supply controlled data.

## References

- Read `references/unit-testing-guide.md` for detailed background, terminology, and extended guidance.
