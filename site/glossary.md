---
title: Glossary
layout: default
nav_order: 5
---
<!-- Owned by the TA team — expand freely (plain sentences, no jargon defining jargon).
     course check validates only the frontmatter. Keep entries alphabetical. -->

# Glossary

Every term the syllabus and setup pages use, one plain sentence each. If a word on this site confuses you and is not here, tell a TA — that is a bug in this page, not in you.

**Clone** — making your own local copy of a repository from GitHub (`git clone <url>`); after that, everything you do happens in your copy.

**Command line** — typing instructions to the computer as text, one line at a time, instead of clicking.

**Dataframe** — a table of data (rows and columns) held in Python by the `pandas` package, like a spreadsheet your code can inspect and transform.

**Commit** — a saved snapshot of your project at one moment, with a short note; Git keeps all of them so you can look back or go back.

**Environment** — one project's private set of Python + packages, kept in its `.venv/` folder so projects can't interfere with each other.

**Git** — the tool that tracks what changed in your project and lets you save and restore snapshots (commits).

**Git Bash** — a terminal for Windows that understands the same commands as the macOS/Linux terminal, so the whole class speaks one command language.

**Interpreter** — the actual Python program (one file on your disk) that reads your code and runs it; your machine may have several, which is why "which Python?" matters.

**JupyterLab** — a notebook editor that runs in your browser; this course uses VS Code for notebooks instead, but `uv run jupyter lab` opens this one if you prefer it.

**Kernel** — the live Python process that runs your notebook's cells and remembers your variables between runs.

**Lock file** (`uv.lock`) — the exact list of every package version a project uses, so `uv sync` builds the identical environment on any machine.

**Notebook** (`.ipynb` file) — a document that mixes runnable code cells with their outputs and text; convenient for exploration, and the reason "run order" and "kernel state" matter.

**Package** — code someone else wrote (like `pandas`) that gets installed into an environment so your code can `import` it.

**Python** — the programming language this program is taught in — and also shorthand for the interpreter that runs it, which is why "which Python?" is a real question.

**Path** — the address of a file in the folder tree, written like `data/raw/sales.csv`; relative paths start from the working directory.

**Prompt** — the line the terminal prints when it is waiting for you to type a command.

**Repository (repo)** — a project folder that Git is tracking; cloning a repo copies it, history included, to your machine.

**Shell** — the program inside the terminal window that reads your commands and runs them (bash or zsh here).

**Terminal** — the window you type commands into; not a different computer, just a precise way to talk to yours.

**Traceback** — Python's error report: the chain of calls that led to a failure, with the error type on the last line.

**`uv`** — the tool that gets each project the right Python and the right packages; `uv sync` sets a project up, `uv run` runs things inside its environment.

**`.venv/`** — the folder inside a project where its environment lives (its own interpreter and packages); `uv sync` creates it, you never edit it, and deleting it is safe because `uv sync` rebuilds it.

**VS Code** — the program's standard code editor; you open the whole project folder in it, and it runs your notebooks (after you pick the `.venv` kernel) and gives you a terminal in the right place.

**Working directory (cwd)** — the folder a program is "standing in"; every relative path is resolved from there. First thing to check when a file can't be found.
