---
title: "Homework 1 Rubric"
subtitle: "Files, paths, terminal, and run instructions"
author: "ECBS5293 — Computing for Analytical Work"
titlepage: false
toc: false
geometry: margin=1in
---

# Homework 1 — Rubric

**ECBS5293 — Computing for Analytical Work**

**Deliverable:** Homework 1 — Files, paths, terminal, and run instructions
**Format:** `hw1-submission.zip` (made with `uv run python make_submission.py` from the project folder) and the video, both uploaded to Moodle
**Total points:** 100

## Overview

You receive a repo that fails because files are misplaced, paths are wrong, or commands are being run from the wrong location. You get it to run, and you document how. This rubric grades the *diagnosis* at least as much as the fix: a working repo you cannot explain loses more credit than a partial fix with a clear, honest diagnosis.

## How scoring works

Every criterion is scored at **exactly one of its three anchor values** — there are no in-between points. The video is scored per element. Two graders reading this rubric should reach the same number.

## Rubric

### 1. Correct fix (30 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 30 | The notebook and the script both run from the documented location, from a fresh unzip, and produce the expected output. Paths are correct and not hard-coded to your machine. |
| **Satisfactory** | 20 | It runs, but with a workaround (an absolute path, a manual `cd` not in the instructions) or one loose end. |
| **Needs Improvement** | 8 | It does not run as instructed, or only runs with changes not reflected in the submission. |

**What we're looking for:** the fix works from a fresh unzip following your own run instructions. For the notebook, either the project-root anchor or a stated kernel folder in the README counts as "documented location".

### 2. Verification (20 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 20 | Evidence the fix worked — the generated output file, the command and its output, a fresh run — not just an assertion; the sanity checks the README asks for (data rows in, rows loaded, products out); and the **reconciliation**: total revenue computed from the input agrees to the cent with the total of the report's `revenue` column, both numbers stated. |
| **Satisfactory** | 13 | Some evidence, but it does not fully prove the fix (e.g. output from a run in a different directory), or the reconciliation is missing while the sanity checks are there. |
| **Needs Improvement** | 5 | "It works now" with nothing to back it up. |

**What we're looking for:** something a skeptical reader could check — including that the report came from the supplied data, not just that a file appeared. Counts alone cannot show that: a report with every value wrong still has four products. The two totals show that the aggregate revenue matches; they do not establish every product value, and a note that claims more than that is claiming more than it checked.

### 3. Diagnosis note (20 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 20 | All five parts for every failure: symptom, actual cause, the raw evidence you ran (`pwd` or `os.getcwd()`, `ls`, the traceback lines), what you changed, how you verified. The cause is a cause, not a restatement of the change. Any organisation is fine — one note per failure, or fewer notes — as long as every cause and its evidence is there. |
| **Satisfactory** | 13 | Four of five parts, or the cause is vague ("the path was wrong"). |
| **Needs Improvement** | 5 | Missing parts, or evidence you did not actually collect. |

**What we're looking for:** "the notebook's working directory was `notebooks/`, so `data/raw/sales.csv` resolved to `notebooks/data/raw/sales.csv`" — not "I fixed the path."

### 4. Video walkthrough (15 points)

Scored per element. Each element is **full**, **half** (mentioned but vague or wrong), or **0** (absent).

| Element | Full | Half | What earns full |
|---|---|---|---|
| Symptom | 3 | 1 | Names what failed, as the error or behaviour you saw |
| Cause | 5 | 2 | Says why the system did that — not "I changed line 5" but why line 5 was wrong |
| Change | 3 | 1 | Says what you changed, specifically |
| Verification | 4 | 2 | Shows or says how you know it works now |

Cover **every failure you fixed**: the elements are scored across all of them, and a failure the video skips caps Cause and Change at half. Your voice is required: a silent recording scores 0 on all four elements — the point is you explaining. Open by naming the homework and the repo; a missed name is a clean-submission matter (criterion 5), not a video one. 60–90 seconds; production quality is not graded, and going over length is not penalised on Homework 1.

*Approved alternative formats* (see the syllabus's accessibility section — arrange in advance): a written walkthrough with annotated screenshots, or an audio-only recording, is scored on the same four elements at the same values. The "your voice" requirement applies to the standard video route only, never to an arranged accommodation.

**What we're looking for:** that you can articulate your own work. Excellent / Satisfactory / Needs Improvement here map to 13–15 / 8–12 / 0–7.

### 5. Clean submission (10 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 10 | Run instructions correct and minimal — the commands that worked, in order, from the project folder; the archive holds the project files and nothing else (no `.venv/`, no `output/`, no checkpoints); the video opens by naming the homework and the repo. |
| **Satisfactory** | 6 | Minor clutter, an instruction that is slightly off, or the video does not open by naming the homework and repo. |
| **Needs Improvement** | 2 | Junk or secrets in the archive, or instructions that do not work. |

**What we're looking for:** a README a classmate could follow, and an archive with nothing in it you cannot explain.

### 6. AI use disclosure (5 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 5 | A short, specific note: what you asked, what it got right or wrong, how you verified it. Or an honest "did not use AI." |
| **Satisfactory** | 3 | Present but generic. |
| **Needs Improvement** | 1 | Missing, or contradicted by the submission. |

**What we're looking for:** honesty and specificity, not a confession.

## General Notes

- The diagnosis note and the video together (35 points) outweigh the fix (30). A working repo you cannot explain will lose meaningful credit; a partial fix with a clear, honest diagnosis can still do well.
- AI tools are allowed. You must be able to explain everything you submit, in your own words, without notes.
- Do not hard-code paths to your own machine. The fix must work for the grader from a fresh unzip.
- Late: accepted up to one day late at −10%; nothing after Saturday 23:59 (syllabus, *Policies*).
