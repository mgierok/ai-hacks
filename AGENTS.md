# Global Rules

## Local rules

- use `python3` instead of `python`
- use `curl` instead of python script to perform simple http requests
- use `apply_patch` to perform text manipulations (add/remove/edit)
- use `rm` to remove files
- use `cat /dev/null > filename` to erase a file

## Optimized Queries and Tools

This section defines standard, fast, and repeatable practices for searching, listing files, and processing data in this `workdir`. It serves as a single source of truth for agents (human and automated) to ensure work is fast, predictable, and .gitignore-aware.

Golden rule: always prefer fast tools (rg, fd, jq) and avoid slow, legacy alternatives.

### Never Use (Slow)

- `grep` or `grep -r` → use **`rg`**
- `find` → use **`rg --files`** or **`fd`** (respects `.gitignore`)
- `ls -R` → use **`rg --files`**
- `cat file | grep pattern` → use **`rg "pattern" file`**

### Always Use (Fast)

#### Content Search

- `rg "search_term"` — search in all files
- `rg -i "case_insensitive"` — case-insensitive search
- `rg "pattern" -t py` — only Python files
- `rg "pattern" -g "*.md"` — only Markdown files
- `rg -l "pattern"` — filenames with matches
- `rg -c "pattern"` — count matches per file
- `rg -n "pattern"` — show line numbers
- `rg -A 3 -B 3 "error"` — context lines (before/after)
- `rg "(TODO|FIXME|HACK)"` — multiple patterns (regex)

#### File Listing

- `rg --files` — list all files (respects `.gitignore`)
- `rg --files | rg "pattern"` — find files by name
- `rg --files -t md` — only Markdown files

#### Fast File Finding

- `fd -e js` — all `.js` files
- `fd -x command {}` — execute command per file
- `fd -e md -x ls -la {}` — example with `ls`

#### JSON Processing

- `jq . data.json` — pretty-print JSON
- `jq -r .name file.json` — extract field
- `jq '.id = 0' x.json` — modify field

### Search Strategy (Best Practices)

1. **Start broad, then narrow** `rg "partial" | rg "specific"`
2. **Filter by type early** `rg -t python3 "def function_name"`
3. **Batch patterns** `rg "(pattern1|pattern2|pattern3)"`
4. **Limit scope** `rg "pattern" src/`
