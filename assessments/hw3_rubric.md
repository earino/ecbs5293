---
title: "Homework 3 Rubric"
subtitle: "Debugging, data files, recovery, and final diagnosis note"
author: "ECBS5293 — Computing for Analytical Work"
titlepage: false
toc: false
geometry: margin=1in
---

# Homework 3 — Rubric

**ECBS5293 — Computing for Analytical Work**

**Deliverable:** Homework 3 — Debugging, data files, recovery, and final diagnosis note
**Format:** `hw3-submission.zip` (made with `git archive` from your commits; includes `REFLECTION.md`) and the video, both uploaded to Moodle. **Due 48 hours before the final exam; this deadline is firm.**
**Total points:** 100

## Overview

You receive a repo with several realistic failures. Some are code errors; some are problems in the input data files. You repair the project, verify the output, explain each failure, and — because this is the last deliverable — write a short reflection looking back across all three homeworks. Do not expect graded feedback before the exam; a self-check key is posted on Moodle when submissions close.

## How scoring works

Every criterion is scored at **exactly one of its three anchor values** — no in-between points. The video is scored per element.

## Rubric

### 1. Correct fix (25 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 25 | Every failure fixed; the pipeline runs end to end from a fresh unzip and produces the verified output; data problems fixed with loading options, not by editing the data. |
| **Satisfactory** | 16 | Most failures fixed; one remains, or one was fixed by hand-editing the data. |
| **Needs Improvement** | 6 | The pipeline does not run, or fixes mask the problems rather than resolve them. |

**What we're looking for:** fixes that would survive the next data file.

### 2. Verification (15 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 15 | Row counts, column names, dtypes, and missing counts checked after each load (the four-line check, left in the code); the output file exists and is what the task asked for. |
| **Satisfactory** | 10 | Some of those checks. |
| **Needs Improvement** | 4 | "It ran" with no data validation. |

**What we're looking for:** the four-line sanity check, applied.

### 3. Diagnosis notes (15 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 15 | One note per failure, each with all five parts, each labelled **code** or **data** with the evidence that decided it. |
| **Satisfactory** | 10 | Notes present but a label is wrong or evidence is thin. |
| **Needs Improvement** | 4 | Failures lumped together, or causes guessed. |

**What we're looking for:** you can tell a wrong column name from a wrong delimiter, and you can say how you knew.

### 4. Video walkthrough (15 points)

Scored per element: **full**, **half** (vague or wrong), or **0** (absent). Up to 2 minutes for this homework.

| Element | Full | Half | What earns full |
|---|---|---|---|
| Symptom | 3 | 1 | Shows the pipeline running end to end and names what used to fail |
| Cause | 5 | 2 | Explains the failures, distinguishing data problems from code problems |
| Change | 3 | 1 | What you changed — loading options vs. code — and why that split |
| Verification | 4 | 2 | Shows the checks that prove the data loaded correctly |

Also required for any points: your voice, starts by naming the homework and the repo. Excellent / Satisfactory / Needs Improvement map to 13–15 / 8–12 / 0–7.

*Approved alternative formats* (see the syllabus's accessibility section — arrange in advance): a written walkthrough with annotated screenshots, or an audio-only recording, is scored on the same four elements at the same values. The "your voice" requirement applies to the standard video route only, never to an arranged accommodation.

### 5. End-of-course reflection (15 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 15 | All four specifics present: a quoted sentence from a prior diagnosis note; a step in the loop you admit to skipping and what it cost; the failure class you were slowest at and a concrete plan; one thing you stopped and one thing you started doing with AI. |
| **Satisfactory** | 10 | Three of the four specifics; the rest is general. |
| **Needs Improvement** | 4 | Generalities, or a reflection that could have been written without re-reading your own work. |

**What we're looking for:** honesty and specificity. 200 concrete words beat 300 padded ones; ~300 is a ceiling.

### 6. Clean submission and Git hygiene (10 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 10 | `GIT_LOG.txt` shows a sequence of meaningful commits ending in a clean final state; nothing junk in the archive; run instructions correct. |
| **Satisfactory** | 6 | Minor clutter or a stale instruction, or commit messages that say nothing. |
| **Needs Improvement** | 2 | No history, junk in the archive, or instructions that do not work. |

**What we're looking for:** before archiving, you knew exactly what changed.

### 7. AI use disclosure (5 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 5 | Specific: what you asked, what it got right or wrong, how you verified. Or an honest "did not use AI." |
| **Satisfactory** | 3 | Present but generic. |
| **Needs Improvement** | 1 | Missing, or contradicted by the submission. |

**What we're looking for:** the same honesty the reflection asks for.

## General Notes

- Diagnosis notes, video, and reflection together (45 points) outweigh the fix (25). This is deliberate: the course grades the diagnosis, not the tinkering.
- AI tools are allowed. You must be able to explain everything you submit, in your own words, without notes.
- Fix data-loading problems with loading options (delimiter, header, dtype, encoding, dates), not by editing the data file.
- Re-read your own three diagnosis notes before writing the reflection — that re-reading is the point, and the best exam preparation you have.
- The deadline is firm: the self-check key is posted when submissions close.
