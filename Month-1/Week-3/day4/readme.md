# Filter Content — Command-Line Text Filtering Cheat Sheet

**Author:** Arjuman Sofi
**Date:** September 16, 2025

---

## Purpose

A concise, one-file README that summarizes how to read files from the command line and filter/process their contents using common Unix tools. This is a learning-focused cheat sheet — short, practical examples and a recommended pipeline for extracting, transforming, and viewing text data.

---

## Key Concepts

* **Pagers:** `more`, `less` — view large files interactively, one screen at a time. `less` offers richer navigation and search features.
* **Head / Tail:** peek at the beginning or end of files (`head`, `tail`, `tail -f` for live logs).
* **Pipes (`|`):** chain tools so output of one becomes input to the next — the foundation of powerful text-processing workflows.
* **Filter & Transform Tools:** `sort`, `grep`, `cut`, `tr`, `column`, `awk`, `sed`, `wc` — combine these for searching, extracting, formatting, substituting, and counting.

---

## Quick Command Cheats

```bash
# View with a pager
cat /etc/passwd | more
less /etc/passwd

# Head / tail
head /etc/passwd
tail /etc/passwd

# Sort lines
cat /etc/passwd | sort

# Search (include / exclude)
cat /etc/passwd | grep "/bin/bash"
cat /etc/passwd | grep -v "false\|nologin"

# Extract first field (delimiter = ':')
cat /etc/passwd | cut -d":" -f1

# Replace characters (':' -> ' ')
cat /etc/passwd | tr ":" " "

# Neat columns
cat /etc/passwd | tr ":" " " | column -t

# First and last column using awk
cat /etc/passwd | tr ":" " " | awk '{print $1, $NF}'

# Substitute text using sed (global)
... | sed 's/bin/HTB/g'

# Count lines
... | wc -l
```

---

## Example Workflow (explainable pipeline)

1. Start: `cat /etc/passwd` — read the file.
2. Exclude disabled shells: `| grep -v "false\|nologin"`.
3. Replace `:` with spaces: `| tr ":" " "`.
4. Print username + shell: `| awk '{print $1, $NF}'`.
5. Show as table: `| column -t`.

This sequence extracts active users and displays their login shell in a clean table.

---

## Notes & Tips

* Prefer `less` when you need to search or scroll back and forth.
* Use `grep -v` to remove matches.
* `awk` is very powerful for field-aware extraction; `$1` is the first field, `$NF` is the last.
* `sed` is ideal for substitutions and lightweight stream edits.
* Combine simple tools; small building blocks lead to powerful pipelines.

---

## Short Practice Tasks

* List usernames with `/bin/bash`:  `cat /etc/passwd | grep "/bin/bash" | cut -d":" -f1`
* Show username and shell in columns:  `cat /etc/passwd | tr ":" " " | awk '{print $1, $NF}' | column -t`
* Count active users:  `cat /etc/passwd | grep -v "nologin" | wc -l`

---


