Goal: Execute commit.

Workflow:

1. Run `git status -sb` and summarize the working tree.
2. If there is nothing to commit, say so and stop.
3. If there are changes and only if nothing is staged: run `git add .`.
4. Generate commit message.
5. After explicit confirmation, run `git commit -m "<message>"`.

Rules:

- Never commit without explicit user confirmation.
- Do not modify files.
