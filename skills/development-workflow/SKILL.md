---
name: development-workflow
description: Enforce a strict, approval-gated development workflow for tasks; use only when the user explicitly invokes this skill or when the prompt starts with "TASK:". Includes analysis confirmation, detailed plan approval, branch creation, TDD-first implementation with lint/format/tests and per-step commits, app run + healthcheck with user confirmation, then merge with merge commit and cleanup.
---

# Development Workflow

## Initialization phase

- Wait for user approval before editing files.
- Record the current branch name with `git branch --show-current`; treat it as the merge target.
- Ask as many questions as needed to clarify the task and scope.
- Analyze the task and provide an expanded interpretation; wait for user confirmation.

## Plan (implementation only)

- Produce a detailed, multi-step implementation plan.
- Keep each step the smallest practical change with a single responsibility.
- Include only implementation work in the plan: tests, code changes, linting, and formatting.
- Do not include preparations, app running, or finalization in the plan.
- Wait for plan approval before proceeding.

## Preparations

- Do not include these tasks in the plan; run them only after the plan is approved.
- Create and checkout a new git branch with a short, meaningful name; avoid `/` in the branch name.

## Execute each plan step (repeat for every step)

- Prefer TDD when possible; create or update the relevant unit test before implementation.
- If any uncertainties arise or a decision is needed, please ask.
- Make the minimal required code change that keeps the software working.
- Run the code linter and code formatter for affected files.
- Run the full test suite; fix failures and re-run until all tests pass.
- Create a commit for the changes in this step before moving to the next step; if no message is provided, propose one and wait for confirmation.

## Running the app

- Do not include these tasks in the plan; run them only after all plan steps are completed and committed.
- Show how to run application and how to do health-check if available
- Wait for user confirmation before proceeding to finalization.

## Finalization

- Do not include these tasks in the plan; run them only after the user confirms the app run.
- Merge the task branch back into the original branch with a merge commit (no fast-forward).
- Proposed commit message should reflects chages made in a commit
- Push changes and delete the task branch.
