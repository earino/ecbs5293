---
title: Syllabus
layout: default
nav_order: 2
---

# DS1 — Computing for Analytical Work

**Program:** MSBA · **Credits:** 1.0 · **Academic year:** 2026–2027
**Format:** 3 teaching sessions × 200 minutes + a closed-book final exam in a separate session
**Instructor:** Eduardo Ariño de la Rubia · [RubiaE@ceu.edu](mailto:RubiaE@ceu.edu) · office hours by appointment

---

## What this course is for

You will spend the next year writing code, training models, and analyzing data. Most of the problems that block you in that work will not be statistics or modeling — they will be computing problems: missing files, the wrong Python, notebooks that won't restart cleanly, errors you don't know how to read.

This course is one credit of practical instruction in the layer *beneath* your other courses. It is not a Python course. It is a course on the filesystem, the shell, the environments, and the version-control system your code actually runs on top of — and the habit of diagnosing, quickly, what actually went wrong. The skills apply to anything you will ever run: Python, R, SQL, or a tool that does not yet exist.

---

## What you will be able to do

1. **Work in a terminal** — navigate, inspect, and run things confidently enough that it is a default workspace, not a last resort.
2. **Orient yourself in a new project** — locate the files, the working directory, the active Python, and its environment before changing anything.
3. **Read a traceback as evidence** — error type, failing line, symptom vs. cause, next thing to inspect.
4. **Use `uv` to manage Python projects** — install, add dependencies, run notebooks in the right environment.
5. **Use Git as a safety net** — see what changed, checkpoint meaningfully, recover without re-cloning.
6. **Inspect data before trusting it** — shape, types, columns, missingness, as a reflex.
7. **Use AI assistants without outsourcing your thinking** — prompt with evidence, verify against the actual system.
8. **Articulate a diagnosis** — symptom, cause, change, verification, in your own words, without notes.

---

## Format and workload

Each session runs two blocks of lecture plus hands-on lab, with a break between. Sessions 2 and 3 open with a 10-minute closed-book knowledge check. The labs are where the learning happens: each gives you an intentionally broken project to diagnose, repair, verify, and explain. Expect about 25 hours of work outside class, most of it on the three homeworks.

---

## Prerequisites and setup

Basic familiarity with Python, or concurrent enrollment in Intro to Programming. No prior command-line or Git experience is assumed. Bring a laptop to every session.

The course uses the MSBA-standard stack from the program prep session — Python 3.13, `uv`, Git, VS Code, and a GitHub account (Windows users work in Git Bash) — nothing extra. **Before Session 1**, run the pre-course setup check (link on Moodle and the course site) and submit its output to the Moodle "Setup verification" slot. The *Pre-course setup* page covers installation and fixes; the *Glossary* page defines every term used here.

---

## AI policy

You may use AI assistants to explain errors, suggest diagnostic steps, teach you concepts, and improve your writing. You may not use AI to submit code or explanations you cannot defend in person, run commands you cannot explain, or describe work you did not do. Two labs open with 15 minutes of no-AI time — practice for the closed-book exam, announced in session.

You remain fully responsible for everything you run, change, and submit. The assessment design assumes you used AI; it checks whether you understood the result.

---

## Assessment

| Component | Weight |
|---|---:|
| Homework 1 — Files, paths, terminal, and run instructions | 10% |
| Homework 2 — Python execution, environments, notebooks, and Git checkpoints | 15% |
| Homework 3 — Debugging, data files, recovery, and final diagnosis note | 15% |
| Knowledge checks (start of Sessions 2 and 3, closed-book) | 10% |
| Final exam (closed-book, in-person, ~1 week after Session 3) | 50% |

**Homework** is the repair of a broken repository, graded against a rubric published with each assignment. Every submission includes a written diagnosis note — symptom, cause, evidence, change, verification — and a short video walkthrough in your own voice. The explanation carries more weight than the fix: a working repo you cannot explain loses meaningful credit; a partial fix with an honest diagnosis can still do well. A self-check key for each homework is posted on Moodle after its late window closes.

**Labs carry no points.** A lab is complete when you explain your fix to a TA in a short oral checkoff (in lab, at office hours, or asynchronously). Labs cost you preparation if skipped, not points.

**Knowledge checks** are 10-minute closed-book checks on the previous session's material. Each is 5%.

**The final exam** is closed-book, individual, in-person, about 70 minutes, in a separate session roughly one week after Session 3 (exact date set by the program calendar). It tests the same skills as the homeworks on new scenarios; format details are announced on Moodle before the exam. Homework 3 is due 48 hours before it.

---

## Schedule

| Session | Date | Arc | Homework |
|---|---|---|---|
| 1 — Where am I? | Mon 14 Sep 2026 | Files, paths, the terminal, first Git habits | HW1 due **Fri 18 Sep, 23:59** |
| 2 — What is running? | Mon 21 Sep 2026 | Interpreters, environments, notebooks, Git checkpoints | HW2 due **Fri 25 Sep, 23:59** |
| 3 — What broke? | Mon 28 Sep 2026 | Tracebacks, data files, recovery | HW3 due 48h before the exam |

All deadlines are on Moodle, which is authoritative.

---

## Submitting your work

Everything is submitted through **Moodle**; nothing is graded from GitHub. You clone each lab and homework from a public starter repository and work locally; each homework README gives the exact submission commands (a Git-produced zip plus your video). Submissions must run as instructed from a fresh unzip and contain nothing you cannot explain.

---

## Policies

- **Late homework:** HW1 and HW2 are accepted up to one day late at −10% (nothing after Saturday 23:59, so the self-check key can post before Monday's knowledge check). HW3's deadline is firm — its key posts immediately.
- **Extensions:** ask before the deadline, by email, with a reason. Documented illness or emergencies are always accommodated.
- **Missed knowledge check:** a documented absence moves that 5% to the final exam; an undocumented absence scores 0. No make-up checks.
- **Missed lab checkoff:** complete it in office hours that week or asynchronously.
- **Regrading:** within 7 days, in writing, naming the rubric criterion you believe was misapplied. The whole submission is re-read; the grade can move either way.
- **Grade conversion:** CEU letter scale — A 94+ · A- 88–93 · B+ 80–87 · B 71–79 · B- 63–70 · C+ 58–62 (minimum pass) · F below.

---

## Academic integrity and accessibility

CEU academic integrity and accessibility policies apply; contact me and the relevant university office early if you need accommodations. If speaking aloud is a barrier, the oral checkoff and homework videos can be completed in writing or by audio with the same content requirements — arrange it with me in advance. Accessible-format exam papers are available on request per your CEU accommodation letter; ask at least a week ahead.
