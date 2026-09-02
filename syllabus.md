---
title: Syllabus
layout: default
nav_order: 2
---

# DS1 — Computing for Analytical Work

**Program:** MSBA
**Academic year:** 2026–2027
**Credits:** 1.0
**Format:** 3 teaching sessions × 200 minutes + a separate closed-book final exam (~1 week after Session 3, 70 min)
**Instructor:** Eduardo Ariño de la Rubia · [RubiaE@ceu.edu](mailto:RubiaE@ceu.edu)
**Office hours:** by appointment

---

## What this course is for

You will spend the next year writing code, training models, and analyzing data — and then keep doing those things for the rest of your career. Most of the problems that block you in that work will not be statistics or modeling. They will be computing problems: missing files, the wrong Python, notebooks that won't restart cleanly, errors you don't know how to read.

This course is one credit of practical instruction in the layer *beneath* your other courses. It is not a Python course. It is a course on the operating system, the filesystem, the processes, the shell, the environments, and the version-control system your code actually runs on top of. Your other courses ask what you should compute; this one asks where the file actually is, which process is running, in which environment, with which dependencies — and how to recognize, quickly, when something has silently gone wrong.

The skills apply to anything you will ever run — Python, R, SQL, or a tool that does not yet exist. They are the substrate of every analytical job you will hold afterward, not just the MSBA. The labs use Python because Intro to Programming does. The diagnostic moves are identical for R, SQL, or a shell script — and one lab uses no Python libraries at all, on purpose.

One more thing, from a student who took this program last year: this year is the cheapest time you will ever have to try the *other* tool — the script instead of the notebook, the unfamiliar library, the second way of doing it. Treat your first encounter with any tool as a starting point, not a default to defend. Wherever you work next will have its own toolkit anyway; the flexibility is the skill.

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

Sessions 2 and 3 open with a 10-minute closed-book knowledge check; on those days Block 1's lecture is **35 minutes**, so the session still totals 200.

The labs are not optional or supplemental — they are where the learning happens. Each lab gives you an intentionally broken project to diagnose, repair, verify, and explain.

---

## Workload

About **25 hours outside class** across the term, on top of 10 hours in class. This is a 1-credit course but a practically intense one. Where those hours go: the three homeworks (≈18–21 hours: HW1 5–6 · HW2 6–7 · HW3 7–8), pre-course setup (≈1 hour), and reviewing your notes against the self-check keys before each knowledge check and the exam (3–4 hours).

---

## Prerequisites

Basic familiarity with Python, or concurrent enrollment in Intro to Programming. No prior command-line, Git, or software engineering experience is assumed. Bring a laptop to every session.

---

## Technical setup

The **program prep session** (before the semester) installs the MSBA-standard stack: Python 3.13, `uv`, VS Code, Git, and a GitHub account. This course uses exactly that stack — nothing extra. If you missed the prep session, the *Pre-course setup* page covers the same installs. You will need:

- Python 3.13 — the program standard; every course repo pins it, and `uv sync` fetches it automatically
- Git 2.23 or later — the version-control tool; this course uses it as a save-points-and-what-changed system
- `uv` — the tool that gets each project the right Python and the right packages, so "it works on my machine" means it works on yours
- VS Code — the program's editor (JupyterLab is installed per project as an alternative)
- Terminal access — macOS/Linux Terminal, or **Git Bash on Windows**: a terminal that speaks the same commands as macOS/Linux, so the whole class uses one command language. (PowerShell, cmd, and Anaconda Prompt speak different ones — that is why they are excluded.)

- **Windows only:** never type bare `python` in Git Bash — it hangs with no error. Use `python --version`, `python -c "..."`, `python script.py`, or `uv run python`. And if `sys.executable` points into `WindowsApps`, that is the Microsoft Store stub, not a real Python; the setup instructions explain how to disable it.

New to these words? The **Glossary** page on the course site defines every one of them in a sentence.

Detailed installation instructions are on Moodle.

### Pre-course setup checklist — due before Session 1

If you did the program prep session, you have everything — just run the check. Otherwise install Git and `uv` per the **Pre-course setup** page first (Python 3.13 arrives by itself via `uv sync`):

```bash
git clone https://github.com/earino/ecbs5293-setup-check.git
cd ecbs5293-setup-check
uv sync
uv run python check.py
```

It ends in `ALL CHECKS PASSED` or `FIX THESE FIRST` with one line per problem. Submit the whole output to the Moodle "Setup verification" slot. If anything fails, the setup page covers remediation, and there is a scheduled "uv install troubleshooting" office-hours slot the week before Session 1.

### Notebook standard (VS Code)

The program's standard editor is **VS Code**, and that is how you open course notebooks:

1. Open the **project folder** in VS Code (*File → Open Folder…*), not the lone `.ipynb`.
2. Run `uv sync` once in the terminal.
3. Open the notebook and, in the **kernel picker** (top right), select the interpreter inside the project's **`.venv/`**. VS Code usually suggests it first once the folder is open.
4. Verify — this is the course habit, not paranoia: run `import sys; sys.executable` in a cell. The path must point inside this project's `.venv/`.

Selecting a global Python, an Anaconda environment, or another project's kernel silently runs your code with a different Python than `uv` is managing — the exact mismatch this course teaches you to diagnose. The kernel picker is where that mismatch lives; step 4 is how you catch it.

`uv run jupyter lab` from the project folder remains a supported alternative (browser JupyterLab, kernel pre-pointed at the project). On Windows, set VS Code's default terminal to **Git Bash** (see the setup page).

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
| Homework 1 — Files, paths, terminal, and run instructions | 10% |
| Homework 2 — Python execution, environments, notebooks, and Git checkpoints | 15% |
| Homework 3 — Debugging, data files, recovery, and final diagnosis note | 15% |
| Knowledge checks (start of Sessions 2 and 3, closed-book) | 10% |
| Final exam (closed-book, in-person, ~1 week after Session 3) | 50% |

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

**Labs carry no points.** A lab is *complete* when it is checked off — in lab, at office hours, or asynchronously — and we track completion, because the labs are where the homework skills are built. But only the components in the grade table above produce your numeric grade; an incomplete lab costs you preparation, not points.

### Knowledge checks

At the start of Sessions 2 and 3, you'll take a 10-minute closed-book check: three short questions on the previous session's material and homework. These are diagnostic, not tricky. If you did the prior work, they are quick.

Before each check, use the **self-check key** for the homework it covers: it is posted on Moodle the **Sunday before the check** (once the late window closes on Saturday night), listing every failure the homework contained and what a correct diagnosis of each names. Comparing your own notes against it on Sunday is the intended preparation.

### Final exam

Closed-book, individual, in-person, 70 minutes. Held in a separate session approximately one week after Session 3; exact date set by the program calendar.

Two parts: **18 multiple-choice questions** (4 points each — every question is a scenario: a traceback, a folder tree, a `git status`, a `head` of a file — and asks for the likely cause or the right next step), and **two written diagnosis notes** (14 points each): one data failure, one environment failure, each with its evidence supplied; you write the five-part note exactly as you did in every lab and homework, graded with the same anchor rubric.

The exam tests the same skills as the homeworks on new scenarios — paths, environments, tracebacks, Git status and recovery, data-file problems, responsible AI use. It does not re-test the specific contents of your homework solutions. No penalty for guessing on the multiple choice.

**Homework 3 is due 48 hours before the exam.** Do not expect *graded* feedback on HW3 before the exam — the 48 hours is for *you* to consolidate, not for the graders. What you will get: as with HW1 and HW2, a **self-check key** — posted the moment HW3 closes (it has no late window), listing every failure and what a correct diagnosis of each names. The best exam preparation is rereading your three diagnosis notes and your reflection against all three keys.

---

## Schedule

### Session 1 — Where am I?

**Monday 14 September 2026**

Files, folders, paths, working directories. The terminal as a way to inspect reality. Your first Git habits (`git status`, `git diff`). You will use `uv run` to launch everything from day one; Session 2 explains what it does.

Lab themes: *The missing file that is not missing* · *Run the project without clicking around*

Homework 1 assigned at the end of the session. **Due Friday 18 September, 23:59** on Moodle (Moodle is authoritative); late window closes Saturday 23:59; self-check key posts Sunday 20 September.

### Session 2 — What is running?

**Monday 21 September 2026**

Python interpreters, packages, environments managed by `uv`, notebooks vs. scripts, kernel state and the restart-kernel-and-run-all test, meaningful Git checkpoints (`add`, `commit`, `.gitignore`).

Lab themes: *It imports on my machine, but not here* · *The notebook lies*

Knowledge check at the start. Homework 2 assigned at the end. **Due Friday 25 September, 23:59** on Moodle; late window closes Saturday 23:59; self-check key posts Sunday 27 September.

### Session 3 — What broke?

**Monday 28 September 2026**

Reading tracebacks systematically. The two-anchor method (last line = error type; line above = failing line). Common beginner errors. Inspecting CSV files. The four-line dataframe sanity check (`df.shape`, `df.dtypes`, `df.head()`, `df.isna().sum()`). Final Git checkpoint before submission.

Lab themes: *The traceback is the map* · *The data is the bug*

Knowledge check at the start. Homework 3 assigned at the end. The final exam follows in a separate session ~1 week later (see *Assessment*).

---

## Submitting your work

Everything is submitted through **Moodle**. Nothing is graded from GitHub.

- **Labs:** clone the public starter repo (link on the session page and on Moodle) and work in that folder. Labs are credited by the in-lab checkoff; nothing to upload unless you finish asynchronously (then: the diagnosis note + a short video, on Moodle).
- **Homework:** clone the starter, work, and **commit** your work. Then, from the project folder, produce the submission archive with Git itself — it contains exactly what you committed, and nothing you ignored:

  ```bash
  git log --oneline > GIT_LOG.txt
  git add GIT_LOG.txt && git commit -m "Add git log for submission"
  git archive --format=zip -o hw1-submission.zip HEAD
  ```

  Upload the zip **and** your video (MP4, under 50 MB) to the homework's Moodle slot. Homework 3's reflection lives in the zip as `REFLECTION.md`.
- **Setup checklist:** the check's output, on Moodle, before Session 1.

Submissions must run as instructed from a fresh unzip, contain no hard-coded local paths, and contain no secrets or generated junk. If `git archive` produced it, the last rule takes care of itself. You must be able to explain everything you submit.

---

## Policies

- **Late homework:** Homework 1 and 2 are due **Friday 23:59** and accepted up to **one day late** at −10% (nothing after Saturday 23:59). The window is short on purpose: the self-check key posts on **Sunday**, so you have a full day with it before Monday's knowledge check. Homework 3's deadline (48 hours before the exam) is firm — no late window — because its key is posted immediately.
- **Extensions:** ask *before* the deadline, by email, with a reason. Documented illness or emergencies are always accommodated; "I ran out of time" is what the late policy is for.
- **Missed knowledge check:** each is 5%. A documented absence moves that 5% to the final exam; an undocumented absence scores 0. There are no make-up checks — they are ten minutes long and test the previous session.
- **Missed lab checkoff:** complete it in office hours that week or asynchronously (diagnosis note + short video on Moodle). Labs are credited, not scored.
- **Regrading:** within 7 days of a grade being released, in writing, stating which rubric criterion you believe was misapplied and why. The whole submission is re-read; the grade can go up or down.
- **Grade conversion:** CEU letter scale — A 94+ · A- 88–93 · B+ 80–87 · B 71–79 · B- 63–70 · C+ 58–62 (minimum pass) · F 57 and below.

## Academic integrity and accessibility

CEU academic integrity and accessibility policies apply. Contact me and the relevant university office early if you need accommodations.

**For the oral checkoff and homework videos.** If speaking aloud is a barrier — speech anxiety, language processing, a registered accommodation — the checkoff can be completed in writing at the TA's desk, via a short audio recording, or by submitting a written walkthrough with annotated screenshots. The four required content elements (symptom, cause, change, verification) stay the same; only the mode of delivery is flexible. Talk to me early so we can arrange it.

**For the knowledge checks and the final exam.** The printed papers are produced from plain-text sources; an accessible-format copy (screen-reader-friendly text or DOCX, large print, or extra time per your CEU accommodation letter) is available on request — ask at least a week before the date.

---

## Contact

**Eduardo Ariño de la Rubia**
Department of Economics and Business, Central European University
[RubiaE@ceu.edu](mailto:RubiaE@ceu.edu)
Office hours by appointment.
