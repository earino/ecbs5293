---
title: "Homework 2 Rubric"
subtitle: "Python execution, environments, notebooks, and Git checkpoints"
author: "ECBS5293 — Computing for Analytical Work"
titlepage: false
toc: false
geometry: margin=1in
---

# Homework 2 — Rubric

**ECBS5293 — Computing for Analytical Work**

**Deliverable:** Homework 2 — Python execution, environments, notebooks, and Git checkpoints
**Format:** `hw2-submission.zip` (made with `git archive` from your commits) and the video, both uploaded to Moodle
**Total points:** 100

## Overview

You receive a repo that fails for two kinds of reason: the environment or package setup is wrong, and the notebook only works when cells are run in a particular order. You repair the setup instructions, make the notebook run cleanly after *Restart Kernel and Run All*, leave meaningful Git checkpoints — and practise recovering from a broken working tree with Git.

## How scoring works

Every criterion is scored at **exactly one of its three anchor values** — no in-between points. The video is scored per element.

## Rubric

### 1. Correct fix (30 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 30 | From a fresh unzip: `uv sync` builds the environment, the script runs, the notebook runs top to bottom after Restart-and-Run-All, and `pyproject.toml` declares what the code needs. |
| **Satisfactory** | 20 | One entry point fully works and the other still fails on a fresh unzip (for example the script runs and the notebook still fails a clean run); or both run but a dependency is undeclared, so it works only because of the student's own environment. |
| **Needs Improvement** | 8 | Neither entry point works from a fresh unzip, or the environment does not build. |

**What we're looking for:** the mismatch between "installed" and "importable" is resolved in the project, not on your laptop.

### 2. Verification (20 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 20 | Restart-and-Run-All shown succeeding on a kernel whose `sys.executable` is inside the project's `.venv/`, **and** the reconciliation stated: the script's per-product table and the notebook's per-product revenue agree to the cent, and the selected products are exactly those above the README's threshold. |
| **Satisfactory** | 13 | The clean run shown, but the reconciliation is missing or the kernel is not verified; or the reconciliation stated without the clean run. |
| **Needs Improvement** | 5 | Neither, or evidence from a stale kernel. |

**What we're looking for:** Restart-and-Run-All is the execution test; the reconciliation is the value test. A notebook with every value ×100 passes the first and fails the second. Agreement between the two implementations shows they agree, not that the shared formula is right; a note that claims more than that is claiming more than it checked.

### 3. Diagnosis note (20 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 20 | Every failure diagnosed with all five parts and its own evidence, in whatever organisation makes the causes clearest. The environment note names the case its evidence supports — a dependency not declared in the project, a kernel that is not the project's, or a package present locally but not declared — and cites the `sys.executable` paths and the declaration that told it. |
| **Satisfactory** | 13 | Correct but thin, or one failure diagnosed and the other only fixed, or a cause asserted that the cited evidence does not support. |
| **Needs Improvement** | 5 | Cause and change conflated; evidence missing. |

**What we're looking for:** each cause named from evidence the student actually has. Matching interpreter paths plus an undeclared package is a complete, correct environment diagnosis.

### 4. Video walkthrough (15 points)

Scored per element: **full**, **half** (vague or wrong), or **0** (absent).

| Element | Full | Half | What earns full |
|---|---|---|---|
| Symptom | 3 | 1 | Names both failures as you saw them |
| Cause | 5 | 2 | Why the environment was wrong *and* why the notebook lied — not just what you changed |
| Change | 3 | 1 | What you changed, for each |
| Verification | 4 | 2 | Restart-and-Run-All shown succeeding on a fresh kernel, and the reconciliation stated |

Your voice is required: a silent recording scores 0 on all four elements — the point is you explaining. Open by naming the homework and the repo; a missed name is a clean-submission matter (criterion 5), not a video one. 60–90 seconds. Excellent / Satisfactory / Needs Improvement map to 13–15 / 8–12 / 0–7.

*Approved alternative formats* (see the syllabus's accessibility section — arrange in advance): a written walkthrough with annotated screenshots, or an audio-only recording, is scored on the same four elements at the same values. The "your voice" requirement applies to the standard video route only, never to an arranged accommodation.

### 5. Clean submission, Git checkpoints, and recovery (10 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 10 | `GIT_LOG.txt` shows at least two meaningful commits with messages that say what they fixed; the **recovery exercise** is documented (`RECOVERY.md`: what you broke, the exact `git` commands that brought the file back, and how you confirmed it); nothing junk in the archive. |
| **Satisfactory** | 6 | Commits exist but messages are "fix"/"update", the recovery exercise is thin, or the video does not open by naming the homework and repo. |
| **Needs Improvement** | 2 | No checkpoints, no recovery exercise, or environment files in the archive. |

**What we're looking for:** a `git log` that tells the story, and proof you can get a file back without re-downloading the project.

### 6. AI use disclosure (5 points)

| Level | Points | Criteria |
|---|---|---|
| **Excellent** | 5 | Specific: what you asked, what it got right or wrong, how you verified. Or an honest "did not use AI." |
| **Satisfactory** | 3 | Present but generic. |
| **Needs Improvement** | 1 | Missing, or contradicted by the submission. |

**What we're looking for:** whether you verified the assistant against the active interpreter.

## General Notes

- The diagnosis note and the video together (35 points) outweigh the fix (30). A working repo you cannot explain will lose meaningful credit; a partial fix with a clear, honest diagnosis can still do well.
- AI tools are allowed. You must be able to explain everything you submit, in your own words, without notes.
- "It works in my terminal" is not verification. The kernel is what runs the notebook.
- `git status` reporting a clean tree is the completeness check after a commit. An empty `git diff` alone is not: it does not see staged work or new files.
- Late: accepted up to one day late at −10%; nothing after Saturday 23:59 (syllabus, *Policies*).
