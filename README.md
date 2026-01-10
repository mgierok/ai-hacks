# ai-hacks
A set of helpers, tools and rules for AI Coding Agents

## Skill sources
- `generate-image` — ported from https://github.com/buildatscale-tv/claude-code-plugins (skill name `generate`).
- `frontend-design` — sourced from https://github.com/anthropics/skills.

## System requirements
To run every command and script referenced in this repo, install the tools below:
- `git` — version control CLI used by commit and workflow prompts.
- `python3` (>=3.10) — runs the image generation script.
- `uv` — Python package/runner used to execute the image script with dependencies.
- `curl` — CLI HTTP client used for simple requests in rules.
- `rg` (ripgrep) — fast text search; preferred over grep.
- `fd` — fast file finder; preferred over find.
- `jq` — JSON processor for inspection and transformations.
- Core Unix tools (`rm`, `cat`) — basic file operations used in instructions (usually preinstalled).

## Python dependencies (for image generation)
Required only if you use the image generation script:
- `google-genai` — Google Gemini API client used to call the image model.
- `pillow` — image library used to load and save images.

## Environment variables
For the image generation workflow:
- `GEMINI_API_KEY` — API key for Google Gemini.
