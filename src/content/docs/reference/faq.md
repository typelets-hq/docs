---
title: FAQ
description: Common questions about Typelets workspaces, hosting, interviews, and limits.
---

## Do I need to install anything?

No. Typelets runs entirely in the browser - editing, the terminal, running code,
and video. Any modern desktop browser works; phones get a read-only
[spectator view](/collaboration/mobile/).

## Is my data saved if the container stops?

Your **workspace files** are durable - they are stored independently of any
running sandbox and rebuilt into it on the next start. Anything written **only
inside the running sandbox** at runtime (a local database file, scratch state)
is **not** durable across a restart. Use an external store for data that must
survive. See [Core concepts](/start/concepts/).

## Does the preview container really stay up?

With [persistent preview](/hosting/persistent-preview/) on, yes - it opts out of
idle eviction and stays warm while the workspace exists. Without it, a sandbox
is idle-evicted after about 15 minutes.

## Can I run a database next to my app?

SQLite or an in-process store works out of the box. A separate database server
process can run, but its data lives in the sandbox and does not persist across a
restart. For durable data, connect to an external database.

## Are interviews recorded with video?

No. [Recordings](/interviews/recording/) capture the code timeline and Run
invocations, not video. The [video call](/collaboration/video/) is live only.

## Does Typelets auto-score candidates?

**Live interviews:** no. The interviewer [scores](/interviews/scoring/) against
the rubric. MCP can help them reason about a score; it does not write one.

**Take-home assessments:** yes. On submit - and when a timed assessment hits its
deadline - Typelets [autogrades](/assessments/grading/) the clone (tests when
present, then Draft with AI auto-applied onto the scorecard) and emails
reviewers the weighted percent, optional test counts, and notes. Reviewers can
edit every chip afterward. Candidates never see the rubric or the numbers.

## What can a candidate see?

The prompt, their own files, and public test cases. Never the rubric, hidden
test expected-output, the reference solution, or scores. When a live interview
ends, the candidate loses access. Take-home candidates find their work on the
[Candidate Dashboard](/assessments/candidate-experience/#candidate-dashboard)
in the app menu; after autograde that item is treated as scored, still without
numbers. See [Sharing & roles](/collaboration/sharing-and-roles/).

## Where do finished take-homes go?

In the workspace switcher, under **Past assessments** (muted, same pattern as
**Past interviews**). For reviewers, the **source** moves there once every
accepted clone is submitted **and** graded - submit alone is not enough.
Candidates see their own clone under Past assessments as soon as they submit.
See [Reviewing
submissions](/assessments/reviewing-submissions/#where-the-source-lives).

## Is hosting available everywhere?

Preview/hosting runs on the hosted platform. The self-hosted local Docker
backend does not serve previews.

## How do I automate Typelets?

Create a [personal access token](/automation/tokens/) and use the
[REST API](/automation/api/) or the [MCP server](/automation/mcp/).

## What languages can I run?

Node, TypeScript, Python, Ruby, Java, Go, and C/C++ are installed. The Run button
handles single-file entrypoints; multi-file projects run from the terminal. See
[Languages & runtimes](/running-code/languages/).
