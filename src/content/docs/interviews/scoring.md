---
title: Scoring
description: Score a live interview against a structured rubric. Take-homes autograde separately.
---

Typelets lets you score a candidate against the problem's rubric criteria,
rather than relying on a single gut-feel verdict.

Live interviews and take-homes share the same rubric shape (named criteria, 1-5
chips, notes). They do **not** share the same write path.

## Live interviews

A problem defines named **criteria** (for example "Correctness",
"Communication", "Code quality"). After the interview, the interviewer scores
each criterion on a **1-5 scale** with optional notes, plus an overall notes
field. Scores are saved on the workspace and visible only to interviewer-side
roles.

For a live interview, scoring is **entered by a human** - the score is the
interviewer's judgment. Nothing auto-applies chips when you end the session.

## Take-home assessments

Take-homes **autograde on submit** (and when a timed assessment hits its
deadline). The clone is locked, tests run when present, Draft with AI is
auto-applied onto the scorecard, and reviewers are emailed the weighted percent
and notes. Reviewers can still edit. See [Grading](/assessments/grading/).

## Who can score and see scores

- **owner / admin / interviewer** can enter and view scores.
- **candidates and viewers never see the rubric or scores** - those fields are
  stripped before the data reaches them.

A workspace is scorable once it has a prompt and either a rubric or at least one
criterion (i.e. a problem has been applied).

## LLM-assisted scoring input

Through the [MCP server](/automation/mcp/), `score_against_rubric` returns the
recording timeline together with the rubric and criteria, so an AI assistant can
help an interviewer reason about a **live interview** score. It provides
**input** - it does not write the score.

That is separate from take-home autograde, which does write scores on the clone.
See [Grading](/assessments/grading/).

## ATS export

Some deployments can sync the resulting scorecard to an applicant tracking
system. This is an optional, deployment-gated integration; if it is not enabled
in your deployment, the ATS controls are not present.
