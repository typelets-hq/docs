---
title: Take-home assessments overview
description: How take-home coding assessments work in Typelets, including Past assessments and the Candidate Dashboard.
---

A take-home assessment is an interview a candidate completes on their own time,
in their own private workspace, instead of live with an interviewer. You invite
a candidate by email, they solve your problem in a real sandboxed workspace on a
timer, the assessment freezes when they submit, and you review the code, the
session recording, and how they got there.

Where a live [interview](/interviews/overview/) is a shared workspace you drive
together in real time, a take-home is asynchronous: the candidate works alone,
and you review afterward.

## The shape of a take-home

1. **Create the assessment.** Start from a workspace, [apply a
   problem](/interviews/problem-library/) (starter files, prompt, rubric), and
   turn on take-home mode. This workspace is the **source** assessment.
2. **Invite candidates by email.** Each invite is private to one address. See
   [Inviting candidates](/assessments/inviting-candidates/).
3. **The candidate accepts and starts.** Accepting clones the assessment into a
   private workspace only that candidate and your reviewers can see. They click
   Start when ready, and the clock begins. See [The candidate
   experience](/assessments/candidate-experience/).
4. **They work, optionally with an AI assistant.** If you enabled it, the
   candidate has a budget-capped AI assistant in the workspace, and every prompt
   is recorded for you.
5. **The assessment submits.** A timed assessment auto-submits at the deadline; a
   due-date assessment is submitted by the candidate (late submissions are
   flagged). On submit the workspace freezes read-only, then Typelets
   [autogrades](/assessments/grading/) in the background.
6. **You review and edit scores.** Browse the submitted files, replay the
   recording, read the AI transcript, and change any autograded chip you
   disagree with. See [Reviewing
   submissions](/assessments/reviewing-submissions/) and
   [Grading](/assessments/grading/). The source stays under **Assessments**
   until every accepted clone is submitted and graded, then it moves to
   **Past assessments**.

## Source assessment vs candidate clone

The assessment you build and invite from is the **source**. When a candidate
accepts, Typelets makes them a private **clone** of it to work in. Reviewers
never see those clones in the workspace switcher: the source is where you send
invites, watch submission states, and review every candidate's work. Candidates
see only their own clone.

## Finding assessments

The workspace switcher groups take-homes the same way it groups live interviews.

- **Assessments** - source assessments that still have work in flight. A
  candidate has not started, is in progress, or has submitted but not every
  accepted clone is graded yet.
- **Past assessments** - muted, same pattern as **Past interviews**. A source
  moves here once every accepted clone is submitted **and** graded (autograde
  auto-apply or a human score). Opening one shows a **Past assessment** badge
  in the header.

Candidates see their own submitted clone under **Past assessments** as soon as
they submit. That is earlier than the source moves for reviewers. See
[Reviewing submissions](/assessments/reviewing-submissions/) for the reviewer
rule.

## Candidate Dashboard

After sign-in, **Candidate Dashboard** is in the app menu - no reload. Hiring
users use it to see candidates across take-homes. Candidates use it to find
their own assessments. Once a grade is present, the dashboard treats that
submission as scored; it does not stay on Awaiting review or Unscored.
Candidates still never see the numbers. See [The candidate
experience](/assessments/candidate-experience/#candidate-dashboard).

## What candidates can and cannot see

Candidates see the prompt, their own files, and public test cases. They never see
the rubric, hidden test cases (beyond pass/fail), the reference solution, other
candidates, or any scores. See [Sharing & roles](/collaboration/sharing-and-roles/).

Next: [Inviting candidates](/assessments/inviting-candidates/).
