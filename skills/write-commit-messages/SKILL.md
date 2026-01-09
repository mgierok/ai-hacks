---
name: write-commit-messages
description: Create commit messages that follow the Conventional Commits v1.0.0 specification. Use whenever asked to provide a commit message or to write, standardize, or suggest git commit messages with structured type/scope/breaking-change markers or conventional footers. Use also when the user asks to commit changes but does not provide a commit message.
---

# Write Commit Messages

## Overview

Use this skill to craft commit messages that conform to the Conventional Commits v1.0.0 specification.

## Workflow

1. If the user asks to commit without a message, infer intent from the diff or ask a brief clarifying question.
2. Identify the intent of the change and choose a type.
3. Decide whether a scope is useful; use a short, specific scope if so.
4. Determine if the change is breaking; add `!` and a `BREAKING CHANGE:` footer if it is.
5. Write a concise description in the imperative mood with no trailing period.
6. Add an optional body for rationale or behavior details.
7. Add optional footers for breaking changes or issue references.

## Specification Details

- Header format: `type(scope)!: description`
- Type: use a common type; follow user or repo conventions if provided.
- Scope: optional; keep short and specific; prefer lower-case if unsure.
- Breaking change: add `!` before the colon and include `BREAKING CHANGE: <summary>` in the footer.
- Body: optional; explain rationale or behavior changes.
- Footers: optional; use `BREAKING CHANGE:` and other tokens like `Refs:` or `Closes:` when requested.

## Common Types

- feat: add a new feature
- fix: fix a bug
- docs: documentation only changes
- style: formatting only; no code change
- refactor: code change that neither fixes a bug nor adds a feature
- perf: performance improvement
- test: add or update tests
- build: changes affecting build system or external dependencies
- ci: CI configuration changes
- chore: other changes that do not modify src or test files

## Output Rules

- Return only the commit message(s), each in a code block.
- If required details are missing, ask a short clarifying question.
- If the diff is provided, infer type and scope from files and changes.

## Examples

```text
feat(parser): add support for quoted tokens
```

```text
fix(api)!: reject unknown fields in request payloads

BREAKING CHANGE: clients must remove unknown fields before sending requests
```

```text
docs(readme): add local setup and troubleshooting steps
```
