---
title: Grading
description: Take-homes autograde on submit. Reviewers can edit the scores.
---

On submit (and when a timed assessment hits its deadline), Typelets **autogrades**
the clone: it runs the problem's tests if they exist, writes scores against the
rubric, and emails reviewers. You can still edit every chip and note. The hire
decision is yours.

Live [interviews](/interviews/scoring/) are different: those scores are entered
by the interviewer. This page is take-homes only.

## Autograde on submit

When the candidate submits, the clone **freezes read-only** immediately. Autograde
runs in the background - the submit request does not wait on tests or the model.

1. If the problem has **test cases**, they run unattended in the sandbox.
   Results are stored on the clone for reviewers (candidates never see them).
2. Typelets then runs the same **Draft with AI** pass you can trigger by hand:
   submitted files, the rubric and criteria, optional test summary, and (when
   the assistant was enabled) the [AI transcript](/assessments/reviewing-submissions/#reading-the-ai-transcript).
3. That draft is **auto-applied** onto the clone. There is no confirm step. The
   Scoring tab shows filled 1-5 chips, notes, and an **Autograded** line:
   `20/22 passed`, `n/a` (no tests on the problem), or `tests failed to run`.
4. Reviewers get the existing **submitted** email once the grade lands (or after
   a short cap if the model fails). The subject includes the weighted percent
   when a score is present, for example `(78%)`. The body has that percent,
   optional test counts, overall notes, and per-criterion notes. In-app
   notifications show the percent only.

A **timed** assessment that auto-submits at the deadline follows the same hook.

Empty tests are not a blocker: Typelets still AI-grades from files, transcript,
and rubric. If the model cannot grade (no API key, upstream error), the
submission stays frozen and reviewers are still notified - they score by hand.

Autograde on submit uses **fill-empty** merge: it writes scores and notes only
where none exist yet. If a reviewer already scored that clone, submit autograde
does not overwrite them.

## Scoring against the rubric

A problem defines named **criteria** (for example "Correctness", "Design",
"Communication"). In the scoring panel you score each criterion 1-5 with optional
per-criterion notes, plus an overall notes field. Scores are saved on the
candidate's clone and visible only to reviewer-side roles.

A workspace is scorable once it has a prompt and either a rubric or at least one
criterion.

## Draft with AI (regrade)

**Draft with AI** is the same model pass autograde uses, run by you from the
Scoring tab. Use it when you want a second look after autograde, or when
autograde could not run.

For the selected candidate it reads the submitted files, the rubric and
criteria, and (when the assistant was enabled) the candidate's AI transcript,
then proposes a score and a note for every criterion plus an overall summary.

Apply behaves differently from submit autograde:

- **Reviewer Apply overwrites** the chips and notes you just previewed, including
  scores autograde already filled. That is what makes a regrade stick.
- **Submit autograde** stays fill-empty so a background grade cannot clobber a
  human score.

You can still edit any chip after Apply. Saved scores are yours.

## How AI usage affects the score

The grader reads the candidate's AI transcript **before** it weighs the rest of
the rubric, not as an afterthought:

- **Meaningful direction** - decomposing the problem, asking targeted questions,
  reviewing and verifying generated code, iterating - is normal modern practice
  and is never a penalty.
- **Wholesale delegation** - pasting the problem and asking Claude Code to
  complete the assessment (including auto mode), then submitting the output -
  means the submitted code demonstrates the assistant's ability, not the
  candidate's. The draft lowers the scores on the criteria that delegated work
  dominates and says so in the notes.

This keeps the score about the candidate's own demonstrated contribution, which
is the point of letting them use AI in the first place.

## Who can see scores

- **owner / admin / interviewer** on the source assessment can view and edit
  scores on each clone.
- **Candidates never see the rubric or scores**, including after autograde.
  Once a grade is present, the [Candidate
  Dashboard](/assessments/candidate-experience/#candidate-dashboard) treats the
  submission as scored without showing the numbers. It does not stay on
  Awaiting review or Unscored.

## Driving scoring programmatically

Through the [MCP server](/automation/mcp/), `score_against_rubric` returns a
recording timeline together with the rubric and criteria, so an AI assistant can
help a reviewer reason about a **live interview**. That tool provides input; it
does not write `interviewScores`.

Take-home autograde is a product path, not an MCP write.
