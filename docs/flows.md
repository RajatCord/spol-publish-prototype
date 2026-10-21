---
title: "SPOL Publish · flows"
source: https://rajatcord.github.io/spol-publish-prototype/docs/flows.html
format: markdown export of the HTML document; tables are pipe tables; the HTML remains the reference rendering
---

Publish · every flow · 21 Oct 2026

# Publish flows

Every path through the polished Publish workflow, screen by screen, as built in the prototype. Select a screen to open it full size. The interactive version is the canvas; this page is the map.

## The shape

A landing page, then four steps: **Standards & content** → **Readiness check** → **Cover & signers** → **Preview & publish**. Content problems leave the workflow through **Send back**; formatting is fixed in Preview with **Auto-format**; AI is opt-in, costed and always a suggestion. A draft can be published at any time; a final needs every selected standard approved and three confirmations.

Flow 1 · the main path

## Publish an internal draft

Alex Carter, Accreditation Coordinator, publishes Draft 4 of the Compliance Certification.

**1**Landing

![Publish landing with Source, Cycle, Report template and Start, above a table of publications](shots/L0.png)

Choose source, cycle and template. Start is inactive until a template is chosen and says so. Or continue a draft from the table.

→

**2**Step 1

![Standards and content](shots/S1.png)

Tick standards by section; search and filter; set what prints with each standard and the response type.

→

**3**Step 2

![Readiness check dashboard](shots/S2.png)

Readiness score 64 (rules, free): internal draft ready, final not yet. Findings by standard. Nothing blocks a draft.

→

**4**Step 3

![Cover and signers](shots/S3.png)

Institution from the profile, preparer and signers by role, submit date, logo and cover letter; live cover preview.

→

**5**Step 4

![Preview and publish](shots/S4.png)

Read the document; confirmations unlock after all 16 sections are viewed; choose PDF, Word, HTML package or Website; internal draft or final; file name.

**1b**Order sections

![Order sections dialog](shots/S4o.png)

"Order sections" in the toolbar lists the sixteen sections in print order. Cover and Contents stay first, Documents and Links stay last; the arrows move a standard, "moved" marks what changed, Reset returns to the template. Applying reorders the thumbnails and navigation, rebuilds contents and page numbers, and clears the confirmations.

→

**6**Published

![Draft published](shots/S4b.png)

Draft 4 published: download, copy link, share; what's next; recorded in the audit trail.

Flow 2 · a branch from Step 2

## Send a standard back

A standard is not good enough. It goes back to the person who holds it, with the findings as a comment, through the approval chain. Nothing is fixed inside Publish.

**1**Step 2

![Readiness check listing every standard with Review and Send back; the AI panel can be hidden](shots/S2.png)

4.2 Assessment of Outcomes has four findings: missing evidence, an oversized image, a heading level. Click Send back.

→

**1a**Review

![Review panel for 3.1 Governing Board](shots/S2f.png)

Review opens any standard, approved or not: the response as it will print with the findings and open comments marked in the text, the evidence and the comment thread. Select any passage to pin a comment to it (blue letter marks); add one overall comment for the standard; they stay together under "Your review". Then either post them to the thread (the standard stays Approved) or send them back together.

→

**1b**Bundled

![Send back dialog for 3.1 with the compiled review comments](shots/S2g.png)

Send back with 3 comments compiles the overall comment, each lettered comment with its quote and paragraph, and the readiness findings into one editable comment; for an approved standard "Leave out of this draft" is off by default, so the current text still prints while the writer answers.

→

**2**Dialog

![Send back dialog](shots/S2b.png)

Choose the writer, the reader who holds it or the editor; one line says what each does to the review. The comment is prefilled with the findings. Optionally leave 4.2 out of this draft until it returns.

**3b**Send all back

![Send all standards with findings back](shots/S2i.png)

"Send all back…" beside the standards list opens one dialog: every standard with findings, who holds it, what its comment will contain (rule findings and, when AI readiness is unlocked, the open AI recommendations with their suggested fixes), whether it keeps printing or is left out, and an optional line added to every comment.

**3c**After send all

![Readiness after sending nine standards back](shots/S2j.png)

Nine rows carry "Sent back", the AI findings on them are marked sent, the unapproved ones are left out of the draft, and the run is marked out of date. Recorded in the audit trail.

→

**3**After

![Readiness check after sending 4.2 back](shots/S2c.png)

"4.2 sent back to Tracy Hall" is confirmed; the row reads Sent back; the audit trail has the entry. The coordinator carries on to Step 3.

Where it rejoins:

the writer fixes 4.2 in All Accreditation, the chain re-approves it, and the next readiness run clears the finding. Meanwhile a draft can still be published without 4.2.

Flow 3 · optional, AI

## Unlock AI readiness

The rules score is free. The AI score is shown blurred with an unlock card that explains what it adds and what it costs. Unlocking is per report and per run.

**1**Locked

![AI readiness locked behind an unlock card](shots/S2.png)

"See it the way a reviewer will": argument strength, evidence sufficiency, consistency, clarity. 29 credits for 12 standards. Suggestions only.

→

**2**Unlocked, in detail

![AI readiness unlocked with score 58, one finding opened in detail](shots/S2d.png)

AI score 58, five bars, and concrete findings. Open one: where it is, the passage the AI saw, why a reviewer would care, a suggested fix, a confidence level.

→

**3a**Accept

![Send back dialog](shots/S2b.png)

**Accept and send back:** the finding goes to the person who holds the standard as a comment, exactly like a rule finding.

or

**3b**Ignore

![AI findings: one sent back, one closed as ignored](shots/S2e.png)

**Ignore:** give a reason (not an issue, already covered, fix later, accepted risk); the finding is marked Closed and can be reopened. Both decisions are recorded; the panel counts open, sent back and closed.

Flow 4 · optional, AI, in Step 4

## Auto-format the whole document

Formatting is the publisher's job. One AI pass fixes tables, images, heading levels, spacing, citation style and the contents, and never changes wording.

**1**Step 4

![Preview with the Auto-format with AI button](shots/S4.png)

The document toolbar carries "Auto-format with AI" in the AI colour. Readiness also points here for formatting findings.

→

**2**Ask

![Auto-format confirmation dialog](shots/S4a.png)

What it fixes, what it never touches, what happens afterwards, and the cost (4 credits). Auto-format document or Cancel. While it runs, a progress modal shows pages laid out and what has been decided per kind; Cancel applies nothing and charges nothing.

→

**3**After

![After Auto-format: banner, change list, marked pages](shots/S4c.png)

184 pages formatted, 23 changes listed with Undo per change or for everything; changed pages carry a margin bar; confirmations are cleared and readiness is out of date, so the publisher rereads.

→

**3a**Before / after

![What Auto-format changed, before and after](shots/S4d.png)

"See before and after" opens every change with the fragment before and after, the page edge marked where content was cut off, who decided it (rules or AI, with the alternative), and Undo this change / Apply again; the count of changes kept updates and Undo never refunds.

Flow 5 · reading

## Read the document in full

Confirming means reading. Reading mode gives the pages the whole screen.

**1**Step 4

![Preview with the maximize button](shots/S4.png)

Click the maximize button in the document toolbar.

→

**2**Reading mode

![Reading mode: pages full width with a slim bar](shots/S4r.png)

No rail, header, thumbnails or side column. A slim bar: exit, page, zoom, sections viewed, next unviewed, comments. Viewed sections count towards the confirmations.

→

**3**Back

![Back to Preview and publish](shots/S4.png)

Exit returns to Step 4 with the viewed count carried over; once 16 of 16, the three confirmations unlock.

Flow 6 · coming back

## Resume a draft

Drafts are saved at every step; the landing table says where each one is.

**1**Landing

![Landing table with Where it is column](shots/L0.png)

"Compliance Certification · Draft 4 · Step 2 · Readiness check". Click the title.

→

**2**The step

![Readiness check reopened](shots/S2.png)

Opens at the step reached, with everything saved. Completed steps in the stepper are links back.

→

**3**Save and exit

![Back on the landing page](shots/L0.png)

Any step's footer has Save and exit; the table updates its "Where it is" and "Last edited".

Flow 7 · first time

## First publication in a cycle

**1**Empty landing

![Landing with no publications yet](shots/L0e.png)

A designed empty state says what to do: choose a source, a cycle and a template above, then start.

→

**2**Step 1

![Standards and content](shots/S1.png)

Start opens Step 1 with the three choices already applied; the rest is Flow 1.

Flow 8 · the final

## Publish a final for submission

Same four steps, with the bar raised. Not yet reachable in the sample data on purpose: three standards are not approved.

**1**Step 2

![Readiness with Final: not yet](shots/S2.png)

The dashboard says "Final: not yet" and lists what is missing: 3.3 written, 4.2 and 6.2 approved, comments resolved.

→

**2**Step 4

![Version choice: Internal draft or Final for submission](shots/S4.png)

"Final for submission" is selectable only when every selected standard is approved; otherwise its reason is shown. The cover carries the signatures; no watermark.

→

**3**Published

![Published state with What's next](shots/S4b.png)

What's next shows "Final for submission · Blocked" with the reason until the approvals land.

## Rules that hold across every flow

### Publishing

- A draft can be published at any time; findings never block it.
- A final needs every selected standard approved, none excluded by a send back, no uncleared injection flag, readiness not out of date, and 3 of 3 confirmations.
- Confirmations unlock only after all 16 sections are viewed, and are blocked while impersonating.
- Editing or Auto-format clears the confirmations and marks readiness out of date.
- Published versions can't be deleted; drafts can, after confirming, with an audit entry.

### AI

- AI is opt-in, costed in credits before it runs, and recorded in the audit trail.
- AI suggests; a person accepts. Auto-format never changes wording.
- Rule-based checks are free and never labelled AI.
- One accent colour marks everything AI.

### Quality

- Every selected standard can be opened from Readiness, approved or not: read it, comment on it, or send it back. Content problems leave Publish through Send back, to the writer, reader or editor, with the findings as a comment.
- Formatting is fixed in Preview, by the publisher, in one pass.

### Accessibility

- One primary action per screen; disabled controls say why in text.
- Status is never colour alone; scores have text equivalents.
- Dialogs are real modals; focus returns on close.
- 44 px targets and stacked layouts on a phone ([example](shots/S1-phone.png)).

Screens rendered at 1390 px from the prototype canvas. Companion pages: the polish plan (originals beside proposals) and the PRD.
