---
title: Pre-course setup
layout: default
nav_order: 4
---

# Pre-course setup — due before Session 1

The **program prep session** installs the MSBA-standard stack — Python 3.13, `uv`, VS Code, Git, and a GitHub account — for every course, this one included. If you attended it, skip to **§2 Run the check** (everyone runs the check). §1 is the same installs, for anyone who missed the session or is on a fresh machine.

Session 1 cannot be tech support. Submit the check's output to the Moodle "Setup verification" slot before the first class. If anything fails, come to the "uv install troubleshooting" office-hours slot in the week before Session 1 — with the output.

## 1. Install the tools (skip if you did the prep session)

### Git (2.23 or later)

- **macOS:** open Terminal, type `git --version`. If it offers to install the command-line tools, accept. Or `brew install git`.
- **Windows:** install [Git for Windows](https://git-scm.com/download/win). Accept the defaults. This installs **Git Bash**, which you will use for *everything* in this course — not PowerShell, not cmd, not Anaconda Prompt. Then, in Git Bash: `git config --global core.autocrlf input`
- **Linux:** `sudo apt install git` (or your distribution's equivalent).

### uv (the program-standard Python manager)

- **macOS / Linux:** in Terminal: `curl -LsSf https://astral.sh/uv/install.sh | sh` — then close and reopen the terminal.
- **Windows:** in Git Bash the same `curl` line works. If it does not, open PowerShell **once** for `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`, then go back to Git Bash. Close and reopen Git Bash.

Check: `uv --version`.

### Python (3.13 — the program standard)

You do not need to install Python separately: every course repo pins **3.13** in its `.python-version`, and `uv sync` downloads it automatically the first time. If you want it on hand anyway: `uv python install 3.13`.

**Windows:** if `python -c "import sys; print(sys.executable)"` prints a path containing `WindowsApps`, that is the Microsoft Store *stub*, not Python. Disable it under *Settings → Apps → Advanced app settings → App execution aliases* (turn off both `python` entries), then re-check.

### VS Code (the program-standard editor)

Install [VS Code](https://code.visualstudio.com/) and, inside it, the **Python** and **Jupyter** extensions (Microsoft).

**Windows — set the integrated terminal to Git Bash** (VS Code's default is PowerShell, which this course does not support): open the Command Palette (`Ctrl+Shift+P`) → *Terminal: Select Default Profile* → **Git Bash**. Every terminal you open inside VS Code is then the same shell the course teaches.

Notebooks: always open the **project folder** (*File → Open Folder…*), and pick the kernel from the project's **`.venv/`** in the kernel picker — details in the syllabus under *Notebook standard*. JupyterLab is installed per project by the course repos as an alternative (`uv run jupyter lab`); you do not need to install anything notebook-related globally. Do **not** install Anaconda for this course; if you already have it, that is fine — just never select an Anaconda kernel for course notebooks.

### GitHub account

**Not required.** Starter repos are public; you clone them, you never push. All submissions go through Moodle.

## 2. Run the check

In your terminal (macOS Terminal / Git Bash):

```bash
git clone https://github.com/earino/ecbs5293-setup-check.git
cd ecbs5293-setup-check
uv sync
uv run python check.py
```

It prints a short report ending in **`ALL CHECKS PASSED`** or **`FIX THESE FIRST`** with one line per problem. Fix, re-run, then copy the whole output (or a screenshot) into the Moodle slot.

What it proves: `uv sync` installed this project's packages into an environment of its own; `uv run` found that environment's Python; that Python can import pandas. That is the whole chain the course relies on. Session 2 explains each step — for now, type it exactly.

## 3. Rules that save you an hour

- **Windows: never type bare `python` in Git Bash.** It hangs with no error. Always `python --version`, `python -c "..."`, `python script.py`, or `uv run python …`.
- **Notebooks run on the project's own kernel.** In VS Code: open the folder, pick the `.venv/` interpreter in the kernel picker, and verify with `import sys; sys.executable`. A global Python, Anaconda, or another project's kernel silently uses a different Python than the one `uv` manages — and recreates exactly the problem this course teaches you to diagnose.
- **Every course repo is run from its own folder** (the one containing `pyproject.toml`). The READMEs say so; the labs are built around it.

## 4. If it still does not work

Submit the failing output anyway — that is useful — and book the office-hours slot. The most common fixes are: reopening the terminal after installing `uv`; the Store stub on Windows; a corporate proxy blocking the installer (use a personal network once); and an old Anaconda install shadowing `python` on PATH.
