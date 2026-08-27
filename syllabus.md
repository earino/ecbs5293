---
title: Syllabus
layout: default
nav_order: 2
---

# DS1 — Computing for Analytical Work

**Program:** MSBA
**Academic year:** 2026–2027
**Credits:** 1.0
**Format:** 3 teaching sessions × 200 minutes + a separate closed-book final exam (~1 week after Session 3, 60–75 min)
**Instructor:** Eduardo Ariño de la Rubia · [RubiaE@ceu.edu](mailto:RubiaE@ceu.edu)
**Office hours:** by appointment

---

## What this course is for

You will spend the next year writing code, training models, and analyzing data — and then keep doing those things for the rest of your career. Most of the problems that block you in that work will not be statistics or modeling. They will be computing problems: missing files, the wrong Python, notebooks that won't restart cleanly, errors you don't know how to read.

This course is one credit of practical instruction in the layer *beneath* your other courses. It is not a Python course. It is a course on the operating system, the filesystem, the processes, the shell, the environments, and the version-control system your code actually runs on top of. Your other courses ask what you should compute; this one asks where the file actually is, which process is running, in which environment, with which dependencies — and how to recognize, quickly, when something has silently gone wrong.

The skills apply to anything you will ever run — Python, R, SQL, or a tool that does not yet exist. They are the substrate of every analytical job you will hold afterward, not just the MSBA. The labs use Python because Intro to Programming does. The diagnostic moves are identical for R, SQL, or a shell script — and one lab uses no Python libraries at all, on purpose.

---

## What you will be able to do

These are behaviors, not topics. By the end of DS1, you should be able to do each of the following without guessing — and the assessments check that you can:

1. **Work in a terminal.** Navigate the filesystem, inspect files without opening them in Excel or a text editor, run scripts and project commands, and read command output as a primary source of information — confidently enough that the terminal is your default workspace, not a last resort.

2. **Orient yourself in a new project.** Given an unfamiliar project on your laptop, locate the files, identify the working directory, name which Python is active, and identify which environment that Python belongs to — *before* you change anything.

3. **Read a traceback as evidence.** Given a Python error, name the error type, identify the failing line, distinguish symptom from cause, and name the next thing to inspect.

4. **Use `uv` to manage Python projects.** Install a project from its `pyproject.toml`, add a dependency, run notebooks inside the project's environment, and recognize when a "package not installed" symptom is actually a "wrong environment" problem.

5. **Use Git as a safety net.** Recognize a repository, see what has changed, take a meaningful checkpoint, read your own history, and recover from a broken working tree without re-cloning.

6. **Inspect data before trusting it.** After loading any dataset, verify its shape, types, columns, and missingness as a reflex — not after a model gives a weird answer.

7. **Use AI assistants without outsourcing your thinking.** Write debugging prompts that contain evidence, evaluate AI suggestions against the actual system, and explain in your own words what fixed the problem.

8. **Articulate a diagnosis.** In 60–90 seconds, without notes, explain what the symptom was, what the cause was, what you changed, and how you verified the fix.

---

## Format

Each 200-minute session is structured as:

```
Block 1:  45 min lecture · 5 min stretch · 45 min lab
          10 min break
Block 2:  45 min lecture · 5 min stretch · 45 min lab
```

The labs are not optional or supplemental — they are where the learning happens. Each lab gives you an intentionally broken project to diagnose, repair, verify, and explain.

---

## Workload

20–25 hours outside class across the term, on top of 10 hours in class. This is a 1-credit course but a practically intense one.

Per-homework time expectation: HW1 ≈ 5–6 hours · HW2 ≈ 6–7 hours · HW3 ≈ 7–8 hours.

---

## Prerequisites

Basic familiarity with Python, or concurrent enrollment in Intro to Programming. No prior command-line, Git, or software engineering experience is assumed. Bring a laptop to every session.

---

## Technical setup

You will need:

- Python 3.10 or later
- Git 2.23 or later
- `uv` (the program-standard Python package and environment manager)
- VS Code or JupyterLab
- A GitHub account
- Terminal access — macOS Terminal, Linux terminal, or **Git Bash on Windows** (not PowerShell, cmd, or Anaconda Prompt — lecture commands assume a Unix-style shell)
- **Windows only:** never type bare `python` in Git Bash — it hangs with no error. Use `python --version`, `python -c "..."`, `python script.py`, or `uv run python`. And if `sys.executable` points into `WindowsApps`, that is the Microsoft Store stub, not a real Python; the setup instructions explain how to disable it.

Detailed installation instructions are on Moodle.

### Pre-course setup checklist — due before Session 1

Run these in your terminal and submit a screenshot to the Moodle "Setup verification" slot before Session 1:

```bash
python --version
python -c "import sys; print(sys.executable)"
git --version
uv --version
git config --global core.autocrlf
```

Then clone the `ds1-setup-check` starter repo (link on Moodle) and, from inside it, run:

```bash
uv sync
uv run python -c "import pandas; print(pandas.__version__)"
```

If anything fails, the setup instructions cover remediation. There is a scheduled "uv install troubleshooting" office-hours slot the week before Session 1 if you need a human.

### Notebook launch standard

Course notebooks must be launched from the project folder with `uv run jupyter lab`. Opening a notebook from a globally installed Jupyter, Anaconda Navigator, or VS Code with a non-project kernel selected will silently use a different Python environment than `uv` is managing — and recreate the exact mismatch this course is teaching you to diagnose.

---

## AI policy

You may use AI assistants (ChatGPT, Claude, Copilot, etc.) to:

- Explain error messages and terminal output
- Suggest diagnostic steps and possible causes
- Explain Python, Git, or environment concepts you don't yet understand
- Help you improve a debugging prompt, a diagnosis note, or your documentation

You may not use AI to:

- Submit code or explanations you cannot defend in person
- Run commands you cannot explain
- Generate diagnosis notes or videos that describe work you did not do

**Two labs open with no-AI time.** The environments lab (Session 2) and the tracebacks lab (Session 3) each begin with 15 minutes where chat windows are closed — terminal, filesystem, and the error itself only. After that, normal AI policy resumes. The point is for you to feel what it is like to be alone with a broken project before the closed-book exam asks you to be. It is not a trap; it is practice.

You remain fully responsible for every command you run, every file you modify, and every line of code or text you submit. The assessment design assumes you used AI; it checks whether you understood the result.

---

## Assessment

| Component | Weight |
|---|---:|
| Homework 1 — Files, paths, terminal, and run instructions | 20% |
| Homework 2 — Python execution, environments, notebooks, and Git checkpoints | 25% |
| Homework 3 — Debugging, data files, recovery, and final diagnosis note | 25% |
| Knowledge checks (start of Sessions 2 and 3, closed-book) | 10% |
| Final exam (closed-book, in-person, ~1 week after Session 3) | 20% |

### How homework is graded

Each homework is the repair of a broken repository. Submissions are graded on:

- **The fix** — does the project run?
- **Verification** — can you show it works?
- **Written diagnosis note** — can you explain *symptom, cause, change, verification* in writing?
- **Video walkthrough** — 60–90 seconds (up to 2 minutes for HW3) of you narrating your screen, explaining the same four elements out loud. Face not required.
- **Git hygiene** — clean submission, no committed junk
- **AI use note** — short description of how AI was used, if at all

The diagnosis note and the video walkthrough together count for more than the fix itself. **A working submission you cannot explain will lose meaningful credit. A partial fix with a clear, honest diagnosis can still do well.**

### In-lab oral checkoff

When you finish a lab, signal a TA or the instructor. They will spend 60–90 seconds at your desk and ask you to explain your fix in your own words, without notes.

**The checkoff is not a test of public speaking.** It exists to confirm that you understand what you changed and why. If speaking aloud under time pressure is a barrier for you, see *Accessibility* below.

If you don't reach checkoff during the 45-minute lab, you can complete it during office hours or by submitting a short asynchronous video. The lab is credited either way.

### Knowledge checks

At the start of Sessions 2 and 3, you'll take a 10-minute closed-book check: three short questions on the previous session's material and homework. These are diagnostic, not tricky. If you did the prior work, they are quick.

### Final exam

Closed-book, individual, in-person. Held in a separate session approximately one week after Session 3; exact date set by the program calendar.

The exam tests the same skills as the homeworks on new scenarios — paths, environments, tracebacks, Git status interpretation, data-file problems, responsible AI use. It does not re-test the specific contents of your homework solutions.

**Homework 3 is due 48 hours before the exam.** Do not expect graded feedback on HW3 before the exam — the 48 hours is for *you* to consolidate, not for the graders. The best exam preparation is rereading your own three diagnosis notes and your end-of-course reflection.

---

## Schedule

### Session 1 — Where am I?

Files, folders, paths, working directories. The terminal as a way to inspect reality. Your first Git habits (`git status`, `git diff`). You will use `uv run` to launch everything from day one; Session 2 explains what it does.

Lab themes: *The missing file that is not missing* · *Run the project without clicking around*

Homework 1 assigned at the end of the session.

### Session 2 — What is running?

Python interpreters, packages, environments managed by `uv`, notebooks vs. scripts, kernel state and the restart-kernel-and-run-all test, meaningful Git checkpoints (`add`, `commit`, `.gitignore`).

Lab themes: *It imports on my machine, but not here* · *The notebook lies*

Knowledge check at the start. Homework 2 assigned at the end.

### Session 3 — What broke?

Reading tracebacks systematically. The two-anchor method (last line = error type; line above = failing line). Common beginner errors. Inspecting CSV files. The four-line dataframe sanity check (`df.shape`, `df.dtypes`, `df.head()`, `df.isna().sum()`). Final Git checkpoint before submission.

Lab themes: *The traceback is the map* · *The data is the bug*

Knowledge check at the start. Homework 3 assigned at the end. The final exam follows in a separate session ~1 week later (see *Assessment*).

---

## Submitting your work

- **Homework repos:** clone from GitHub Classroom, work in your private fork, push when done.
- **Homework videos:** upload to Moodle as MP4 (under 50 MB). Not to GitHub.
- **Setup checklist:** Moodle, before Session 1.

Submissions must run as instructed, contain no hard-coded local paths, and contain no committed secrets or generated junk. You must be able to explain everything you submit.

---

## Academic integrity and accessibility

CEU academic integrity and accessibility policies apply. Contact me and the relevant university office early if you need accommodations.

**For the oral checkoff and homework videos.** If speaking aloud is a barrier — speech anxiety, language processing, a registered accommodation — the checkoff can be completed in writing at the TA's desk, via a short audio recording, or by submitting a written walkthrough with annotated screenshots. The four required content elements (symptom, cause, change, verification) stay the same; only the mode of delivery is flexible. Talk to me early so we can arrange it.

---

## Contact

**Eduardo Ariño de la Rubia**
Department of Economics and Business, Central European University
[RubiaE@ceu.edu](mailto:RubiaE@ceu.edu)
Office hours by appointment.
