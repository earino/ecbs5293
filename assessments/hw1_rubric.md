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
**Format:** `hw1-submission.zip` (made with `git archive` from your commits) and the video, both uploaded to Moodle
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

**What we're looking for:** the fix works from a fresh unzip following your own run instructions.

### 2. Verification (20 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 20 | Evidence the fix worked — the generated output file, the command and its output, a fresh run — not just an assertion. |
| **Satisfactory** | 13 | Some evidence, but it does not fully prove the fix (e.g. output from a run in a different directory). |
| **Needs Improvement** | 5 | "It works now" with nothing to back it up. |

**What we're looking for:** something a skeptical reader could check.

### 3. Diagnosis note (20 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 20 | All five parts for every failure: symptom, actual cause, the raw evidence you ran (cwd, `ls`, the traceback lines), what you changed, how you verified. The cause is a cause, not a restatement of the change. |
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

Also required for any points: 60–90 seconds, your voice, starts by naming the homework and the repo. Production quality is not graded; going over length is not penalised on Homework 1.

*Approved alternative formats* (see the syllabus's accessibility section — arrange in advance): a written walkthrough with annotated screenshots, or an audio-only recording, is scored on the same four elements at the same values. The "your voice" requirement applies to the standard video route only, never to an arranged accommodation.

**What we're looking for:** that you can articulate your own work. Excellent / Satisfactory / Needs Improvement here map to 13–15 / 8–12 / 0–7.

### 5. Clean submission and Git hygiene (10 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 10 | Run instructions correct; `GIT_LOG.txt` shows at least one commit with a message that says what it fixed; no junk in the archive; `COMMANDS.md` is the commands that worked. |
| **Satisfactory** | 6 | Minor clutter, a commit message like "fix", or an instruction that is slightly off. |
| **Needs Improvement** | 2 | Junk or secrets in the archive, no commit history, or instructions that do not work. |

**What we're looking for:** a README a classmate could follow, and a log that shows you checkpointed.

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
- Late: −10% per calendar day, up to three days (syllabus, *Policies*).
