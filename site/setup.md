---
title: Pre-course setup
layout: default
nav_order: 4
---

# Pre-course setup — due before Session 1

Session 1 cannot be tech support. Complete this before the first class and submit the output to the Moodle "Setup verification" slot.

## What you need

- Python 3.10 or later
- Git 2.23 or later
- `uv` — the program-standard Python package and environment manager
- VS Code or JupyterLab
- A GitHub account
- Terminal access — macOS Terminal, Linux terminal, or **Git Bash on Windows** (not PowerShell, cmd, or Anaconda Prompt — lecture commands assume a Unix-style shell)

**Windows only:** never type bare `python` in Git Bash — it hangs with no error. Use `python --version`, `python -c "..."`, `python script.py`, or `uv run python`. If `sys.executable` points into `WindowsApps`, that is the Microsoft Store stub, not a real Python: disable it under *Settings → Apps → Advanced app settings → App execution aliases* and re-check. Before cloning any course repo, run `git config --global core.autocrlf input`.

## The check

Run these in your terminal and submit a screenshot or pasted block:

```bash
python --version
python -c "import sys; print(sys.executable)"
git --version
uv --version
git config --global core.autocrlf
```

Then clone the `ds1-setup-check` starter repo (link on Moodle) and, from inside it:

```bash
uv sync
uv run python -c "import pandas; print(pandas.__version__)"
```

Expected: Python ≥ 3.10; a real file path from `sys.executable`; Git ≥ 2.23; a `uv` version; on Windows, `input` from the autocrlf line; and a pandas version number at the end. That last line proves the whole chain works — `uv` installs packages, the project environment exists, and `uv run` finds the right interpreter.

If anything fails, the setup instructions on Moodle cover remediation, and there is a scheduled "uv install troubleshooting" office-hours slot the week before Session 1.

## Notebook launch standard

Course notebooks must be launched from the project folder with `uv run jupyter lab`. Opening a notebook from a globally installed Jupyter, Anaconda Navigator, or VS Code with a non-project kernel selected will silently use a different Python environment than `uv` is managing — and recreate the exact mismatch this course teaches you to diagnose.
