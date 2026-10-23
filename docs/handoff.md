---
title: "SPOL Publish · functional handoff"
source: handoff.html
format: markdown export of the HTML document; tables are pipe tables; the HTML remains the reference rendering
---

Product specification · Publish workflow · v4 · 22 Oct 2026

# Publish: what it does and how it behaves

The functional specification for the polished Publish workflow, as prototyped. It describes what people see and do, the rules the product enforces, the words it uses, and how we will know it is right. It does not prescribe data structures, service contracts or implementation; those are the build team's design, and the earlier technical notes are kept beside this page for reference.

## In short

- **What:** the Publish tab becomes a landing page plus four steps: Standards & content → Readiness check → Cover & signers → Preview & publish. The old Generate Report step is folded into step 4.
- **Quality leaves the workflow through Send back;** nothing in the content is fixed inside Publish. Formatting is fixed in Preview by Auto-format (AI, 4 credits). AI readiness is opt-in (2 credits per standard + 5).
- **A draft can be published at any time.** A final needs every selected standard approved, the three confirmations after every section has been read, and no unresolved manipulation flag.
- **Everything is recorded:** runs, decisions, confirmations, publishes and deletions, with who, when and which version of the report.

## Scope

#### In

- The Publish landing page (with its empty state) and the four steps, with every state the prototype shows: send back (single and all), review a standard, AI readiness (locked, unlocked, finding detail, decisions), Auto-format (ask, progress, after, before-and-after), reading mode, order sections, output options, published.
- Phone and tablet layouts for every screen.
- The two AI features as described in the AI behaviour section and the dossier.
- Credits: quoting, charging and refunds for the two AI actions, in the terms the coordinator sees.
- The audit record of every action listed under What is recorded.

#### Out (unchanged from today)

- All Accreditation, the approval chain, the comment threads on standards and the Document Repository. Publish reads from them and writes comments and status into them; it does not change their screens.
- Signature capture: the cover carries typed names and optional dates, as in V10.
- A versions overview, a signer workflow, and AI credit administration beyond what PRD R26 already defines. Copy link and Share with reviewers use the existing share dialog.

#### Reference set

1. **This page**: the functional specification.
2. **Prototype** (interactive, 24 screens plus sizes): [live site](https://rajatcord.github.io/spol-publish-prototype/) · [canvas](../index.html).
3. **Flows**, every path screen by screen: [flows](flows.html).
4. **How AI readiness works**, the user-facing dossier that also ships as the in-product help panel: [dossier](dossier.html).
5. **The readiness checks** (the thirteen free checks, one by one, with severity and the score) and **The AI checks** (the five AI checks, findings, decisions, cost): [readiness checks](readiness-checks.html) · [AI checks](ai-checks.html).
6. **AI behaviour specification** (what the two AI features read, return and never do; cost; safety; quality bar): [AI spec](ai-spec.html).
7. **PRD** R10, R14, R15, R24–R30: [PRD](https://claude.ai/artifact/TZEpQk1SHaK6j5TkxqZZj5).
8. **Engineering notes**: the earlier, technical version of this handoff (data model, service contracts, ledger rules, per-control accessibility attributes). Kept for the build team's own design work; where it and this page differ, this page wins.

## People and roles

| Who | Can | Cannot |
| --- | --- | --- |
| Coordinator | Everything in Publish: start, delete and rename drafts, run checks, unlock AI readiness, send back, confirm, Auto-format, publish drafts and finals, withdraw a final, regenerate a file, clear a manipulation flag, approve another coordinator's large AI run. | Approve their own large AI run. |
| Editor | The same as a coordinator except withdraw, regenerate and clear. | Withdraw, regenerate, clear flags. |
| Writer, reader | Open any version and read every step, including findings and the AI results. | Any action that changes the publication. Those controls are shown disabled with "Only coordinators and editors can do this". Writers never see credit balances or cost lines. |
| Anyone impersonating a user | Read everything. | Start, publish, send back, unlock, Auto-format, delete and confirm ("Not available while impersonating"). Their reading never counts as the impersonated person having viewed a section. |
| Signers (CEO, liaison) | Are named on the cover; attest on the printed cover, not in Publish. | — |

A person who loses access while a page is open sees "You no longer have access to this publication. Back to Publish." A published version opened from the landing shows the Published screen; its earlier steps are read-only with "Published versions can't be changed".

## Concepts (one meaning each)

| Term | Meaning here |
| --- | --- |
| Source · accreditor | The accreditor instance a cycle belongs to ("SACSCOC-2018" in the UI, printed as "SACSCOC 2018"). The UI says **source**. |
| Publication · version | A **publication** is one report template in one cycle ("Compliance Certification, 2024–2025"). It has **versions**: "Draft 1, 2, 3…" while being worked on and "Final 1, 2…" when published for submission. Numbers are never reused, even after a delete. |
| Standard · part | A **standard** is a numbered requirement (4.2); a **part** is a sub-requirement (4.2.a). Counts, charging and AI checks always count standards, never parts. |
| Template section · document section | A **template section** is a numbered group of standards in Step 1 ("6 Resources"). A **document section** is a unit of the printed report in Step 4 (cover, contents, each standard, documents, links); it is what "sections viewed" counts. |
| Finding | Any check result, from the rules or from AI. Never "issue" or "item". |
| Holder | The person the approval chain currently places a standard with: its writer while being written or after approval, its reader while in review, its editor while with the editor. A send back goes to the holder unless the sender chooses otherwise. |
| Send back · left out | Sending a standard back returns it to a person in the chain with a comment. The sender can also **leave it out** of this draft until it returns; a standard left out does not print, does not count in the score and is not read by AI. |
| Out of date | The readiness result no longer matches the draft: something that affects the report changed since the checks last ran. The old result stays visible, marked, until the checks run again. |
| Confirmations | Three statements the publisher ticks on Step 4 after reading every section: sections and standards, formatting and branding, findings and comments. They are cleared whenever the document changes. |
| Credits · quote · left this year | Credits are the institution's pooled AI allowance. A **quote** is the most a run can cost and is shown before anything starts. "**{n} left this year**" is what is available now, after any run that is still reserving credits. |
| Coordinator · editor | The two roles that can act in Publish; the text says "coordinator or editor" wherever both may act. |

## Rules that apply everywhere

#### Drafts and finals

- A **draft** is an internal, watermarked copy. It can be published whenever at least one standard is in it, the file name is not empty, the submit date is in the future and the three confirmations are ticked. Open findings and comments never block a draft; they are listed under "Before you publish".
- A **final** is the submission copy. On top of the draft conditions it needs: every selected standard approved and none left out by a send back; the three signers assigned; the readiness check current (not out of date); and no manipulation flag that a coordinator has not cleared.
- When something blocks, the product names the first blocker in this order: published already → not your role → impersonating → nothing to publish → wait for a running Auto-format, AI run or publish to finish → file name empty → submit date → confirmations → signers → "Not yet: {codes} not approved or excluded by send back" → manipulation flag → readiness out of date. The same wording appears wherever the block is shown (Step 2 verdict, Step 4 Final option, Published screen).
- A published version is immutable. Drafts can be deleted after a confirmation; published versions never. A final can be withdrawn by a coordinator with a reason; the file stays downloadable and is marked Withdrawn, and the next final is numbered as usual.
- "Start Draft n+1" and "Duplicate" create the next draft from a published version's selection, settings, cover and output choices. Not inherited: confirmations, sections viewed, readiness and Auto-format results. AI finding decisions carry over while the finding still matches the text; "Will fix after this draft" reopens. Standards left out by a send back stay left out until they return.

#### What makes the readiness check out of date

A change to the selection, the content settings or the response type; a standard removed from the cycle; a change to a selected standard's narrative, evidence or comments in All Accreditation; Auto-format applied or undone; an edit saved in Step 4; a send back that leaves a standard out; a standard returning from send back. The last result stays on screen with "Out of date · Run again" (or "Not checked yet · Run checks" when there has never been a run).

#### What clears the confirmations

- Any saved edit in Step 4 (a discard clears nothing); Auto-format applied or undone; a change to the selection, content settings or response type; a standard removed from the cycle; a send back that leaves a standard out; a standard returning from send back; a change of section order.
- A readiness or AI run whose findings differ from the previous run clears only "Findings and comments", because that summary changed.
- **Not cleared:** a narrative, evidence or comment change arriving from All Accreditation. The draft is marked out of date and Step 4 shows the banner, but the confirmations stand: a draft tolerates text that moved under it; a final cannot be published while out of date.
- Any coordinator or editor can untick a confirmation, not only the person who ticked it; the record names both.

#### Saving, reloading, working together

- Every change saves on its own within a second: "Saving…" then "Saved"; on failure "Couldn't save · Retry".
- Each step has its own address; reloading opens that step, never one the draft has not reached; browser Back moves one step.
- Two people on the same draft: when someone else saved first, the control returns to their value and the page announces "Someone else saved this draft. Reload." Nothing is merged silently.
- A draft deleted by someone else: "This draft was deleted by {name}. Back to Publish." A draft published by someone else while open: "Draft 4 was published by {name} at {time} and can't be edited. Start Draft 5 · View published"; unsaved edits are lost and the notice says so.
- Writes during a running AI run are allowed; the run's result is marked out of date when it finishes. Only publishing waits for a running Auto-format, AI run or publish.

#### Defaults

- Rename: 1 to 120 characters, unique within the cycle ("A publication with this name already exists").
- File name: prefilled "{Institution}_{Source}_{Title}_{Version}_{date}" without spaces; characters that file systems reject are removed; over 120 characters it is shortened with a note.
- Dates print as "17 Oct 2026", with ", 4:31 PM" when the time matters. Sizes print as "2.3 MB".
- A section counts as viewed, per person, when most of its first page has been on screen for two seconds or its thumbnail is opened. Views carry over between drafts while the section still exists; a new section counts as unviewed.
- The preview starts building on entry to Step 4 and after every change; it is ready within two minutes or shows "Couldn't build the preview · Retry". Publishing finishes within five minutes or tells the person it is still running and they can leave the page; the landing row then shows "Publishing…".
- An AI run above 50 credits needs a second coordinator's approval; the request expires after 7 days. When no second coordinator exists: "A second coordinator must approve · none is set up · Ask your administrator".

## Landing (Publish tab)

#### What it is for

Start a publication, or pick up a draft where you left off. Two tabs separate **In progress** drafts from **Published** versions.

#### Controls

| Control | Behaviour | Copy |
| --- | --- | --- |
| Source, Cycle, Report template | Three required selects. Source defaults to the cycle shown in the header; changing it resets Cycle to that source's current cycle and clears the template. Cycle lists the source's cycles, current first. Template has no default. Each select is disabled with a hint until the one before it is chosen. | Labels "Source", "Cycle", "Report template"; placeholder "Select a template…"; one legend "* Required" |
| Start publication | Enabled once all three are chosen, for coordinators and editors who are not impersonating. Starts Draft 1 of the publication and opens Step 1. If a draft of that publication is already in progress: "Draft 4 is in progress · Open Draft 4 · Start Draft 5 anyway"; starting anyway copies the last *published* version, never the live draft. | Disabled reason "Choose a report template to start" |
| Tabs | **In progress ({n})** and **Published ({n})**. In progress columns: Report · Version · Where it is (Step n · name) · Owner · Last edited. Published columns: Report · Version · Format · Pages · Published by · Published on. Search filters the active tab. The chosen tab is remembered per person. | Empty states "No drafts in progress" / "Nothing published yet" |
| Row menu (⋯), drafts | Open (resumes at the step shown) · Rename publication · Duplicate as new draft · Delete draft. Delete asks "Delete Draft 2 of Compliance Certification? This can't be undone. The deletion is recorded in the audit trail." and adds "An AI readiness run is in progress and will be cancelled" when one is running or awaiting approval. |  |
| Row menu (⋯), published | Open · Download {format} · Copy link · Withdraw final (finals only, coordinators, with a required reason: "Withdraw Final 1? The file stays downloadable and is marked Withdrawn. This is recorded."). For a published draft the menu says "Published versions can't be deleted". |  |
| Table | Every version of the cycle's publications, newest edit first. Status is a dot plus a word: In progress · Published · Withdrawn. The title opens the row. |  |
| Loading, failure, empty | Placeholder rows while loading; "Couldn't load publications · Retry" on failure; when the cycle has no versions, an illustration with "No publications for this cycle yet" and one line of guidance, and the selects still work. |  |

#### Acceptance

- **Tabs.** Given the demo data. Then "In progress 3" is selected with Draft 4, Online MBA Draft 2 and Draft 2; "Published 3" shows Draft 3, Final 1 and Draft 1 with format, pages, published by and on; search filters the active tab only.
- **Start gated.** Given no template chosen. Then Start is disabled with the visible reason "Choose a report template to start" and does nothing when pressed.
- **First draft.** Given a template with no publication. When Start. Then Step 1 opens with the chip "Draft 1" and the start is recorded.
- **Draft already open.** Given Draft 4 in progress. When Start for the same template. Then the notice offers Open Draft 4 or Start Draft 5 anyway; the latter copies Draft 3 (the last published), shows "Draft 5" and no confirmations.
- **Delete.** Given Draft 2 in progress. When Delete draft and confirm. Then the row is gone, the deletion is recorded, and a later Start creates "Draft 5", never "Draft 2".
- **Published row.** Given Draft 3 published. Then its menu has neither Delete nor Withdraw.
- **Withdraw.** Given Final 1 and a coordinator. When Withdraw final with a reason. Then the status is "Withdrawn", Download still works, the next final will be "Final 2", and the withdrawal with its reason is recorded. An editor cannot withdraw.

## Step 1 · Standards & content

#### What it is for

Choose which standards go into this report and what prints with them.

#### Controls

| Control | Behaviour | Copy |
| --- | --- | --- |
| Context row | Breadcrumb Publish › title; chip "Draft 4"; template · cycle; the stepper (completed steps can be opened, future steps not); "Saved". |  |
| Heading line | "Standards · {selected} of {total} selected · {n} not approved"; the count is a link that applies the Not approved filter. |  |
| Search, filter, menu | Search by code or title (sections with no match hide). Filter: All · Not approved · Unselected, with live counts. Select all and Clear all beside the count; the ⋯ menu repeats them and adds Expand all · Collapse all. | "Search standards" |
| Section row | Chevron (collapse state remembered per person per draft); a three-state checkbox that selects or clears every standard and part in the section; "{n} Name · {k} of {m} selected". |  |
| Standard and part rows | Checkbox, code, title, status dot and word (Approved · In review · Not started · Sent back). Selecting a standard selects its parts; a part can be unselected alone; selecting a part selects its standard. |  |
| Note under the list | "{n} selected standards are not approved yet ({codes}). You can still publish an internal draft; a final needs every selected standard approved." or "Every selected standard is approved." |  |
| Content settings | For Documents, Links, Objectives and Outcomes: Linked in narrative · All linked · Don't publish, defaulted from the template; a switch "List documents and links at the end". | "What prints with each standard." |
| Response type | Narrative · Institutional Effectiveness · Institutional, each with a one-line description (wording to confirm with the team), defaulted from the template. |  |
| Changes since the draft began | A standard removed from the cycle is unselected on load with the banner "{code} was removed from this cycle and is no longer selected". A template revised after the draft began: "This template changed on {date}. Draft {n} keeps the version it started with; Draft {n+1} will use the new one." |  |
| Footer | Save and exit · Next, disabled with "Select at least one standard" when nothing is selected. |  |

#### Acceptance

- **Section checkbox.** Given section 6 with nothing selected and "9 of 12 selected". When the section box is ticked. Then 6.1, 6.2, 6.3 are selected, the row reads "6 Resources · 3 of 3 selected" and the heading "12 of 12 selected". When 6.3 is unticked. Then the section box shows the mixed state and "2 of 3 selected".
- **Part alone.** When 4.2.b is unticked. Then 4.2 stays selected. When 4.2.b is ticked while 4.2 is unselected. Then 4.2 becomes selected too.
- **Not approved filter.** When "Not approved 3" (or the heading link) is used. Then exactly 3.3, 4.2 and 6.2 show, and the note names them.
- **Zero selection.** When Clear all. Then Next is disabled with "Select at least one standard" and Step 2 would read "Internal draft: not ready".
- **Change clears.** Given a completed readiness check and three confirmations. When Documents changes to "Don't publish". Then Step 2 shows "Out of date · Run again" and Step 4 "0 of 3 confirmed"; the same for unselecting a standard or changing the response type.
- **Keyboard.** Given Expand all. Then every checkbox is reachable in reading order, Space toggles it, and Left/Right collapse and expand a section row.

## Step 2 · Readiness check

#### What it is for

Show what the checks found and whether the report is ready to publish, let the publisher read, comment on and send back any standard, and offer AI readiness as an opt-in second opinion. Findings never block a draft.

#### Controls

| Control | Behaviour | Copy |
| --- | --- | --- |
| Top line | "Last run {date, time} · {k} of 13 checks completed · language checks by WProofreader" · Run checks again (progress "Checking {n} of {m} sections", with Cancel) · Download report (Excel). Before any run: the ring shows "—", verdicts "Not checked yet", the lists are hidden, Next is still enabled. Cancelled: "Checks cancelled · Run checks". Not finished in ten minutes: "Checks couldn't finish · Run again", the previous result stays. |  |
| Readiness (rules, free) | Score ring; "Internal draft: ready / not ready"; "Final: ready" or "Final: not yet · {codes} not approved"; the score out of 100 as the sum of six categories, printed beside the ring ("21 + 18 + 14 + 9 + 13 + 14 = 89"); "Approvals 9 of 12 · they decide Final, not the score"; six bars with their points: Evidence 21 / 25, Completeness 18 / 20, Review 14 / 15, Language 9 / 10, Print and export 13 / 15, Accessibility 14 / 15; an expandable "How the score is built"; a recommendation paragraph assembled from the findings (templated sentences, no AI). How the score is built: see Checks and findings. | Chip "Rules · free"; link "How the score is built" |
| AI readiness, locked | A blurred preview behind an unlock card: what it adds (the five checks), "Suggestions only. Nothing changes without you", the quote "{n} credits for {m} standards · {left} left this year", Unlock AI readiness, How AI readiness works. Writers see no cost line and a disabled Unlock ("Ask a coordinator or editor to unlock AI readiness"). Unlocking first re-runs the rules if they are out of date, then starts the AI run; above 50 credits it asks for a second coordinator and shows "Waiting for approval from {name}". Progress "Reading {n} standards… started by {name}"; Cancel keeps what finished and refunds the rest ("Cancelled · {n} of {N} checked"); a run that cannot finish refunds the unchecked standards ("AI readiness didn't finish · credits for unchecked standards refunded · Try again"); a run where nothing could be checked refunds everything and locks the card again. |  |
| AI readiness, unlocked | AI score ring; "Reviewer view: {n} likely follow-ups"; "Contradictions: {n} to resolve"; five bars; the findings list; "Run again" (shows a fresh quote; standards whose text has not changed cost nothing); "What it checks and how"; a tally "{open} open · {sent} sent back · {closed} closed · {credits} credits used · {left} left this year · recorded in the audit trail". |  |
| AI panel, hidden | Both states have a × that collapses the panel to a one-line strip ("AI readiness · Locked · hidden from view · unlock any time for 29 credits · Show", or "AI readiness 58 · {n} open findings · 1 contradiction · hidden from view, nothing lost · Show"). The rules dashboard then takes the full width. The choice persists per person and draft; nothing is stopped or lost. |  |
| AI finding row | Standard, severity, one line; View details reveals Kind · Where · Reviewer question · What it saw (quote) · Why it matters · Suggested fix · Confidence. Actions: **Accept and send back** (opens the Send back dialog for that standard with the finding ticked; a cross-standard contradiction first asks which of the two standards goes back) and **Ignore** (a reason is required: not an issue, already covered, fix after this draft, accepted risk; the row becomes "Closed · ignored" with Reopen). Rows whose text has changed since the run show "Outdated". A manipulation finding (text that tries to steer the review) cannot be accepted or ignored, only cleared by a coordinator, and blocks a final until cleared. Standards that could not be checked appear as "{code} not checked · {reason} · {n} credits refunded". |  |
| Standards in this draft | One expandable row per selected standard, approved or not: code and title · "{n} findings" · what they are · severity counts · "Status · held by" · Review · Send back (or Remind for a standard not started, which sends the existing reminder and then reads "Reminded"). Expanded: one line per finding "{Severity} · {Kind} · {where} — {detail}", then "Open {code} in All Accreditation". A clean standard reads "All 13 checks passed"; a not-started one "No response has been written yet, so there is nothing to check. Due {date} · Writer {name}." Above the list: **Send all back…** with "{n} of 12 standards carry findings or AI recommendations". | Intro: "Open any standard to read it, comment on it, or send it back, approved ones too. Formatting is fixed in Preview." |
| Review panel | Opens from Review or the standard's title, for any selected standard. Header: code, title, status chip, "{judgment} · written by {writer} · approved {date} by {editor} after review by {reader} · {n} findings · {m} open comments". Body: the response as it will print, with the passages that carry a finding or an open comment marked in amber; selecting a sentence opens "Comment on the selected text" and adds a lettered blue mark; "Your review of {code}" lists the inline comments (edit, remove) with an Overall comment box; then Findings, Evidence (missing files flagged) and the standard's comment thread with a reply box. Footer: "Send back {code} with {n} comments" (compiles everything into one send-back comment) and "Post {n} comments · stays Approved" (adds them to the thread without touching the approval). Drafts of the review are private to the author and kept until posted or sent; the same drafts appear in reading mode. | "A send back reopens the chain; posting alone does not." |
| Send back dialog | "Send {code} {title} back". Send to: Writer (default, "holds it" when they do) · Reader · Editor, each with a one-line effect. Findings to include (each ticked, can be unticked). AI recommendations to include (shown when AI readiness is unlocked; suggestions only, each with its suggested fix). Comment, prefilled from the ticked items and editable (template under Comments). "Leave {code} out of this draft until it comes back": on by default for an unapproved standard, off for an approved one ("its current text still prints"). On Send: the comment is written to the standard, the chain moves, the row shows "Sent back to {name}", the ticked AI findings become "Sent back", the readiness result is marked out of date, and a status line confirms. A standard already sent back cannot be sent again ("Already sent back by {name}"). If every standard is left out: "Internal draft: not ready · no standards left in this draft". |  |
| Send all back dialog | "Send all standards with findings back". One row per standard with findings or AI recommendations that is not already sent back and has been started: checkbox (on), code and title, what its comment will include ("2 findings · 1 AI"), who holds it, whether it keeps printing or is left out. An optional line added to every comment. Cancel · "Send back {n} standards" (disabled until one is ticked). Each standard gets its own comment, exactly as the single Send back writes it; unapproved standards are left out; approved ones keep printing. Afterwards: "{n} standards sent back to the people who hold them, each with its findings and AI recommendations as a comment · {codes} left out of this draft until they return · recorded in the audit trail." |  |
| How AI readiness works | A panel with the dossier: six promises, what it reads and never sees, the five checks, why a finding can be trusted, how the score is built, privacy, manipulation, cost, limits, the record. Reached from the unlock card, the unlocked panel header and both hidden strips. Content is maintained by SPOL, not editable by institutions. |  |
| Footer | Back · Save and exit · Next (always enabled). |  |

#### Acceptance

- **Score.** Given the demo data. Then the ring reads 89 with "21 + 18 + 14 + 9 + 13 + 14 = 89", the six bars as above, "Internal draft: ready", "Final: not yet · 3.3, 4.2, 6.2 not approved".
- **Out of date after a writer's change.** Given a run and three confirmations. When a writer fixes a spelling finding. Then "Out of date · Run again" and the confirmations stand. When Run checks again. Then only "Findings and comments" is cleared if the findings changed; nothing is cleared if they did not.
- **Unlock refused.** Given 20 credits left and a 29-credit quote. When Unlock. Then the card stays locked and Unlock is disabled with "Not enough credits · 29 needed, 20 left this year · Ask your administrator"; nothing is charged.
- **Quote after a cancelled run.** Given a run cancelled at 4 of 12. When Unlock. Then "21 credits for 8 standards · 4 already checked".
- **Second approval.** Given 28 standards (61 credits). When Unlock. Then "This run needs 61 credits. A second coordinator must approve."; choosing yourself is refused ("Someone else must approve"); afterwards "Waiting for approval from {name} · Cancel".
- **Ignore.** Given an open AI finding. When Ignore. Then the four reasons are offered and Mark closed is disabled until one is chosen; afterwards "Closed · ignored" with Reopen, and the decision with its reason is recorded.
- **Accept and send back.** Given the 4.1 finding and 4.1 approved. When Accept and send back. Then the dialog opens for 4.1 with Writer preselected, the finding ticked and its why and fix in the comment, and "Leave 4.1 out" unticked (approved). When Send back. Then the finding reads "Sent back", the row reads "Sent back to Tracy Hall · {date}", and the readiness result is out of date.
- **Contradiction.** Given "6.1 vs 5.1". When Accept and send back. Then "Which standard should go back?" lists both with their values first.
- **Send all back.** Given nine standards with findings or AI recommendations. When Send all back and Send back 9 standards. Then nine rows read "Sent back", the AI findings on them read "Sent back", 4.2 and 6.2 are left out, the banner names them, and nine comments exist, one per standard.
- **Outdated finding.** Given an AI finding on a passage. When that passage is edited in Step 4 and saved. Then the row shows "Outdated" with its actions still available; a manipulation finding stays blocking a final until cleared.
- **Review an approved standard.** Given 3.1 approved. When Review, a sentence is selected and added as comment A, and an overall comment is written. Then "Your review of 3.1" lists both and the footer reads "Send back with 2 comments" / "Post 2 comments · stays Approved". When Post. Then both appear in the thread marked "from Publish" and the approval is unchanged. When instead Send back. Then the dialog shows one compiled comment and the review drafts are marked sent.
- **Remind.** Given 3.3 not started. When Remind. Then the button reads "Reminded"; a second attempt the same day reads "Reminded today".

## Step 3 · Cover & signers

#### What it is for

What prints on the cover and who signs it. Institution details come from the profile; nothing the system already knows is typed again.

#### Controls

| Control | Behaviour | Copy |
| --- | --- | --- |
| Institution | Name and address read-only from the institution profile, with "Edit in Admin › Institution". A missing address is listed under "Before you publish" on Step 4. | "From the institution profile" |
| Report preparer, CEO, Accreditation Liaison | Required pickers bound to the institution's role holders; the current holders are preselected. A vacant role shows "No one holds this role · Assign in Admin"; a person who left the cycle shows "{name} · no longer in this cycle". Either prints a blank line, is listed under "Before you publish", and blocks a final but never a draft. |  |
| Dates signed | Optional; any date, since a signature date is in the past by nature. | "Leave the dates blank until the cover has been signed. The names print on the signature lines either way." |
| Submit date | Required; must be after today. Prints as "Submit by {d Mon yyyy}". A saved date that has since passed shows a warning; Next stays enabled and publishing blocks with "Submit date must be after today". | Inline error "Submit date must be after {today}."; Next reason "Fix the submit date to continue" |
| Branding | Logo row with Replace and Remove (SVG, PNG or JPG up to 2 MB); optional cover letter (DOCX or PDF up to 10 MB). Errors: "File is larger than {limit}", "Use SVG, PNG or JPG" / "Use DOCX or PDF", "Upload failed · Try again"; the previous file is kept. | "Your institution's assets, not SPOL's." |
| Cover preview | Live rendering of the cover from the fields. |  |
| Footer | Back · Save and exit · Next (disabled with the reason while the submit date is invalid). |  |

#### Acceptance

- **Submit date.** When set to today. Then "Submit date must be after {today}." and Next is disabled with that reason. Given a saved date that has passed. Then the warning shows, Next works, and Step 4 blocks publishing with "Submit date must be after today".
- **Vacant role.** Given no liaison. Then the picker says so, "Before you publish" lists it, and a final is blocked with "Add the three signers in Cover"; a draft is not.
- **Uploads.** A 3 MB PNG → "File is larger than 2 MB"; a GIF → "Use SVG, PNG or JPG"; the previous logo stays. A 12 MB cover letter → "File is larger than 10 MB".
- **Preview.** When the CEO changes. Then the cover preview shows the new name within a second and the page reads "Saved".

## Step 4 · Preview & publish

#### What it is for

Read the document as it will print, fix formatting, confirm the three items, then choose the format and publish.

#### Controls

| Control | Behaviour | Copy |
| --- | --- | --- |
| Thumbnail rail | One thumbnail per document section with a viewed tick and a comment marker; opening one scrolls the viewer there and marks it viewed. |  |
| Section navigator | ‹ Previous · a select listing every section ("3.1 Governing Board · viewed · comments") · Next ›, in the toolbar and in reading mode; Left/Right arrows move sections while reading. Moving marks the target viewed. |  |
| Toolbar | "Page {a}–{b} of {N}" · zoom (75–200 %) · Find in document · "{v} of {S} sections viewed" · Next unviewed · Order sections · Preview \| Edit · Auto-format with AI · Reading mode. |  |
| Viewer | The generated document, page by page, from the same renderer as the output. While it builds: "Preparing the preview · {n} of {N} pages" with confirmations locked; after two minutes "Couldn't build the preview · Retry". A cited evidence file that was deleted prints "(file missing)", becomes a High finding and is listed under "Before you publish". |  |
| Order sections | A dialog listing the sections in print order. Cover and Contents stay first, Documents and Links stay last; standards move up or down with arrows; "moved" marks rows out of template order; Reset to template order; Apply. Applying reorders the thumbnails and navigation, rebuilds contents and page numbers, clears the confirmations and is recorded. Standard numbers never change. |  |
| Edit mode | Inline editing of narrative passages only. Banner: "Editing clears the confirmations and marks the readiness check out of date", a checkbox "Also update the response in All Accreditation" (unavailable while the standard is in review: "Not available while {code} is in review"), Save, Discard. Saving clears the confirmations, marks readiness out of date, and removes the option to undo an earlier Auto-format ("Can't undo after editing"). Leaving with unsaved edits asks "Save your edits? Save · Discard · Cancel". |  |
| Reading mode | Hides everything but the document and a slim bar: Exit (also Esc) · title · section navigator · page · zoom · Find · viewed count · Next unviewed · Order sections · Comments (n). The comments panel (open by default when the section has comments) shows "{n} comments on {section} · {m} open in the report", each comment with author, date, a jump to its section, Resolve or Reopen, and a reply box ("Does not reopen approval"). Review works here exactly as in the Readiness review panel: select a sentence, add a lettered comment, write an overall comment, then Send back or Post; the drafts are shared between the two places. Sections read here count as viewed. On a phone the comments panel becomes a bottom sheet. |  |
| Confirm & attest | "{c} of 3 confirmed · signers attest on the final version"; locked with "View all {N} sections to confirm" until the person has read every section; three items with their summaries (Sections and standards · Formatting and branding · Findings and comments); "Confirming as {name} · not available while impersonating. Signers attest on the cover."; Comments (n) swaps the column for the open comments list with Resolve. |  |
| Auto-format with AI | A dialog listing what it will do in this report, per kind with counts and pages (tables fitted, images scaled, heading levels, paragraph spacing, citations; contents and page numbers always rebuilt), each kind can be unticked; what never changes (wording, judgments, which evidence is cited, the cover, numbers); what you get afterwards (before-and-after per change, undo per change or all, changed pages marked, confirmations cleared, recorded); the cost "4 credits for the run, whatever you tick · {left} left this year · nothing is charged if there is nothing to change or the run fails". Then a progress modal with per-kind counts and Cancel ("nothing applied, nothing charged"). Afterwards a banner ("Auto-formatted {N} pages · {n} changes · no wording changed · 4 credits used · recorded"), a change list, and a **before-and-after view**: one entry per change with the fragment before and after, the page edge marked where content was cut off, who decided (rules or AI, with the alternative), Undo this change / Apply again, "Open this page in reading mode", the running count, Undo all. Undo never returns the credits and the dialog says so. | Button "Auto-format with AI"; chip "Auto-formatted" |
| Publish | Format: PDF · Word · HTML package · Website, each with a one-line helper. Version: Internal draft (watermarked) · Final for submission, the latter disabled with the first blocker as its reason. Options: Table of contents, Page numbers, Page break before each standard, Running headers, Documents and links listed at the end (from Step 1), Cover letter (unavailable until one is uploaded in Step 3), "Draft" watermark (follows the version). File name, prefilled. "Before you publish: {n} open findings · {m} open comments · formatting not yet run. None of it blocks a draft." |  |
| Footer | Back · Save and exit · the reason text · Publish draft / Publish final (disabled with the reason until allowed; "Wait for {Auto-format \| AI readiness \| publishing} to finish" while one runs). Publishing confirms "Publish Draft 4 as PDF? Still open: {n} findings, {m} comments. This is recorded.", shows "Publishing · {n} of {N} pages", and on failure "Couldn't publish · nothing was recorded · Try again" without using up a version number. If the draft changed after the confirmations: "This draft changed since you confirmed it. Reload." | "Confirm {3−c} more to publish · {v} of {S} sections viewed" |

#### Acceptance

- **Viewed tracking.** Given nothing viewed. When the first page of 4.2 has been mostly on screen for two seconds, or its thumbnail is opened. Then "1 of 16 sections viewed"; under two seconds nothing counts.
- **Lock.** Given 9 of 16 viewed. Then the three checkboxes are disabled with "View all 16 sections to confirm (9 viewed)".
- **Edit clears.** Given three confirmations. When a passage is edited and saved. Then "0 of 3 confirmed", the out-of-date banner, no Undo of an earlier Auto-format, and "Confirm 3 more to publish". Discard changes nothing.
- **Edit held in review.** Given 4.2 in review. Then "Also update the response in All Accreditation" is unavailable with "Not available while 4.2 is in review".
- **Order sections.** Given template order. When 4.2 is moved above 4.1 and Apply. Then the thumbnails, the navigator and Next follow the new order, the status says "2 sections out of template order", contents and page numbers are rebuilt, the confirmations are cleared, and Reset returns to the template.
- **Auto-format.** When Auto-format and confirm. Then the progress modal, then the banner with "23 changes" (2 tables, 3 images, 1 heading level, 14 spacing, 3 citations), 4 credits used, confirmations cleared, readiness out of date. Undo all returns no credits. A failed run: "Auto-format couldn't finish · no changes applied · nothing charged · Try again". Nothing to format: "Nothing to format · no credits used".
- **Before and after.** When "See before and after". Then the first change opens with the table cut at the page edge on the left and fitted on the right; Undo this change marks it Undone and the count reads "22 of 23 changes kept · 1 undone"; Apply again restores it.
- **File name.** Given "Report:final?.pdf". Then the saved name is "Reportfinal.pdf"; over 120 characters it is shortened with a note; empty → "File name can't be empty" and Publish is disabled.
- **Publish draft.** Given everything allowed. When Publish draft and confirm. Then "Publishing · {n} of 184 pages", then the Published screen with "Draft 4 published · PDF · 184 pages · {size} · {date} · Recorded in the audit trail."
- **Blocker order.** Given an empty file name and 4.2 unapproved. Then the Final reason is "File name can't be empty" (draft reasons come before final reasons).
- **Reading mode.** When Reading mode. Then only the document and the slim bar remain, Esc exits, and sections read there count. When Next ›. Then the select shows the next section, the document scrolls there, the viewed count rises and the comments panel heading changes.
- **Review in reading mode.** Given 3.1 open with the comments panel. When a sentence is selected and added as comment A. Then the mark appears, "Your review of 3.1 · 1 comment in the text" lists it, the buttons read "Send back with 1 comment" / "Post 1 comment · stays Approved", and the same draft is visible in the Readiness review panel.

## Published

- Banner "Draft 4 published · {format} · {pages} pages · {size} · {date, time} · Recorded in the audit trail."
- File card: title, file name, "Internal draft, watermarked"; Download (primary), Copy link (private link for institution users; "Couldn't copy · select the link" on failure), Share with reviewers (the existing share dialog). A file that has gone missing shows "File unavailable · Regenerate" (coordinator); if a document it cites was deleted, "A document in this report was deleted and the file can't be regenerated".
- What's next: Keep working · Start Draft 5 (from this version's settings); Final for submission, either a link or "Blocked · Not yet: {codes} not approved or excluded by send back".
- Summary: standards, readiness at publish ("{n} findings open at publish · {m} open comments"), cover, confirmed by whom, output format and options, section order.
- Footer: Done, to the landing page, where the version now appears under Published.

## Checks and findings

#### The free checks

Every readiness run performs all of these. They cost no credits and are never labelled AI. Two engines: SPOL's own rules, and WProofreader for language (licensed by SPOL; runs as you type in the editor and again here, with SPOL's accreditation dictionary and the institution's own dictionary).

| Check | Engine | Fixed by | Name in the v6.0.0.8 build |
| --- | --- | --- | --- |
| Spelling, grammar and punctuation | WProofreader | The writer, accepting suggestions in the editor | Spell Check (move it out of "AI can fix these": it is neither AI nor fixed by Publish) |
| Style | WProofreader style guide | The writer | new |
| Link validation | SPOL rule | The writer relinks; a Validate button re-checks one link | Link Validation |
| Table format | SPOL rule | Auto-format in Preview | Table Format |
| Image sizes | SPOL rule | Auto-format in Preview | Image Sizes |
| Alt text | SPOL rule | The writer | new |
| Headings | SPOL rule | Auto-format in Preview | new |
| Illegal characters (file names and narrative) | SPOL rule, list kept in System Settings | File names: Auto-format substitutes; narrative: the writer | Illegal Characters |
| Missing attachments | SPOL rule | The writer uploads; the coordinator sets the expected count | Missing Attachments |
| Placeholder text | SPOL rule | The writer, or Step 3 for the cover | new |
| Required cover fields | SPOL rule | Step 3 | new (v6 collects them on "Structure & Branding") |
| Open comments and unresolved edits | SPOL rule | Resolve in the thread or the editor | Narrative Comments (v6 shows "Not Checked"; it must run) |
| Hidden text | SPOL cleaner, every run | Removed automatically; listed report-wide so nobody is surprised | new |

"Issue Summary" in the v6 build is a view, not a check, and should not appear in the checks list. A check's row reads **Passed** (ran, nothing found), **Issues found** with the count, **Partially checked** (some standards or items could not be checked, with the reason) or **Not checked** (did not run).

#### Severity

Three levels, one meaning each, applied by the rule and never by a person. **High**: the published document would be wrong, incomplete or unprintable for a reviewer, or a final could not be submitted. **Medium**: a reviewer would notice and ask, or evidence or review is incomplete. **Low**: polish, fixed by a tool or safely ignored. One finding per element: a table with nine wide columns is one finding, not nine (the v6 build's "181 table issues" counts cells).

| Check | High | Medium | Low | Not checked when |
| --- | --- | --- | --- | --- |
| Spelling, grammar, punctuation | — | A misspelt word in neither dictionary | Grammar, punctuation; a word only the institution's dictionary knows | Language service unavailable; narrative empty |
| Style | — | A rule the institution marked "required" | Every other style rule | No style guide configured |
| Link validation | A linked SPOL document or evidence file that no longer exists or cannot be opened | An external address that fails twice, or a reference to a deleted objective or outcome | An address that redirects or whose certificate warns | No network; the target needs a sign-in |
| Table format | Wider than the printable page (cells would be cut off) | No header row; a row split across pages | Fits only after scaling below 85 % (Auto-format will turn it landscape) | A table whose width cannot be measured |
| Image sizes | Larger than the page, so it would be cropped | Over 1 MB, or too low a resolution to print | Within limits but without a caption | Image file missing |
| Alt text | — | An image with no alt text | Alt text identical to the file name | — |
| Headings | — | A skipped level; an empty heading | Duplicate numbering | — |
| Illegal characters | A file name the export or file system rejects | A narrative character on the institution's list that breaks export or rendering | A character SPOL substitutes silently (smart quotes, non-breaking spaces) | — |
| Missing attachments | Expected count set and nothing attached; or no expected count at all | Fewer attachments than expected | More than expected | Standard not started |
| Placeholder text | Bracketed or templated placeholders, "TBD", "lorem", in the narrative or on the cover | — | — | — |
| Required cover fields | Institution name, address, preparer, a required signer or the submit date missing (blocks a final, not a draft) | A signer named but their date unsigned | — | — |
| Open comments and unresolved edits | — | An open comment or a pending edit on the standard | — | Comment service unavailable |
| Hidden text | Hidden text found and removed (report-wide) | — | — | — |

#### How the rules score is built

The thirteen checks are grouped into six categories with fixed weights: Evidence 25 (missing attachments, links), Completeness 20 (placeholders, cover fields), Review 15 (open comments and edits), Language 10 (spelling, grammar, punctuation, style), Print and export 15 (tables, images, illegal characters, hidden text), Accessibility 15 (alt text, headings). A finding counts High 3, Medium 1, Low 0 points; for each standard (and, where it applies, the report itself) a category keeps 1 − min(points, 6) ÷ 6 of its value; the category's quality is the average over the units it applies to; its score is weight × quality rounded down; the readiness score is the sum. A category can never cost more than its weight and one standard never more than its slice of a category. A standard not started scores 0 in Completeness and is skipped elsewhere; standards left out by a send back are removed; approvals are shown beside the score but are not part of it. The demo data gives 21 + 18 + 14 + 9 + 13 + 14 = 89. The full method and worked example are in "The readiness checks". Only the rules score gates a final; the AI score is advice.

#### The readiness report download

"Download report (Excel)" gives the run that is on screen, including an out-of-date one, as one workbook: `Readiness_{institution}_{template}_{Draft n}_{run date}.xlsx`. It never re-runs anything, so the file says exactly what the screen said. Plain values, no formulas; header row frozen with filters on every sheet; dates written out; severity and status as words; one row per finding; no merged cells. Before the first run the button is disabled with "Run the checks first".

| Sheet | One row per | Columns, in order |
| --- | --- | --- |
| Summary | key · value | Institution; Report; Version; Run started and finished; Run by; Checks completed; Language checks (WProofreader, dictionary version); Rules score with its terms; Internal draft ready; Final ready and its blockers; Approvals a of n; Evidence e of n; Open comments; Formatting findings; Accessibility findings; Findings by severity; Standards sent back and left out; AI run present or not, AI score, credits used |
| Findings | finding | Standard code; Standard title; Check; Severity; Location (page, paragraph, element); Description; Suggested action; Report-wide (yes/no); Left out (yes/no); Status (open, sent back); Holder (role · name); Found in run (date) |
| Standards | selected standard | Code; Title; Section; Chain state; Held by; Approved on; Writer; Reader; Editor; High / Medium / Low counts; Expected evidence; Attached evidence; Open comments; Unresolved edits; In this draft (yes / left out); Sent back on; AI findings open / sent / closed |
| AI findings | AI finding (sheet present only when an AI run exists) | Standard; Kind; Severity; Confidence; Where; What it saw (quote); Reviewer question; Why it matters; Suggested fix; Decision; Reason; Decided by; Decided on; Outdated (yes/no) |
| Report-wide | finding with no standard | Check; Severity; Location; Description; Fixed by Auto-format (yes/no) |
| Checks | check | Check; Engine; Status; Items checked; Findings; Not-checked reason |

A CSV of the Findings sheet alone is also offered for people who want a flat list. Each download is recorded.

## AI readiness and Auto-format

The only two places in Publish where a model is used. Both are opt-in, quoted before they start, recorded, and only ever suggest. The user-facing dossier is the full account; the AI behaviour specification states what each feature reads, returns and never does. The behaviour that matters to the product:

- **AI readiness** reads each selected standard the way a visiting reviewer would (its wording, SPOL's reviewer questions, the response, the cited evidence index, the judgment and open comments) and returns findings in five areas: argument strength, evidence sufficiency, consistency across standards, clarity, reviewer readiness. Every finding quotes the passage or names the unanswered question; findings that cannot be matched to the text are dropped before anyone sees them. The AI score is computed by SPOL from the findings with a published formula; the model never gives a number.
- **Decisions** on an AI finding are two: accept and send back (it travels to the holder as a comment, through Send back) or ignore with one of four reasons. Both are recorded; a closed finding can be reopened; a finding on text that changed shows "Outdated"; a finding the next run no longer reproduces is shown as resolved.
- **Manipulation.** Text that tries to steer an AI or the review is reported as a High finding, blocks a final (not a draft) until a coordinator clears it, and never removes a standard from the score.
- **What is never sent:** attachment files; student or personnel records; names, emails and IDs (replaced by tokens); the whole report in one go; other institutions' reports or earlier cycles; the cover and dates. A standard where personal data is detected is left out of the run and refunded ("not checked · personal data").
- **Cost:** 2 credits per standard not already checked + 5 for the cross-standard check (12 standards → 29). Run again charges only standards whose text or evidence changed. Standards that could not be checked are refunded. Above 50 credits a second coordinator approves first. The quote is a ceiling: the institution never pays more.
- **Auto-format** lays every page out to the template. It decides only how (scale a table or turn it landscape, which heading level, which citation form); it never changes wording, judgments, which evidence is cited, the cover or any number. Every change is shown before and after and can be undone singly or all at once; undo keeps the 4-credit charge; a run that finds nothing or fails charges nothing.
- **Quality bar:** repeat runs on the same text agree at least nine times in ten; every statement in the dossier is backed by a test run before a model or rubric version ships and nightly afterwards; the models are pinned and run under zero-data-retention terms.

## Comments, send back and notifications

#### What a comment is

Every comment on a standard, whoever or whatever prompted it, is one comment in the standard's existing thread, so All Accreditation, the Publish review panel, reading mode and the writer's inbox all show the same thing. A comment carries:

- **Who wrote it and in what role**, always a person (the coordinator who sent back, the publisher who posted). AI text inside a comment is introduced as a suggestion in the body, never attributed to "AI" as the author.
- **Where it came from**, shown as a chip: from the chain, from Publish (a posted review comment), a send back, the readiness check, an AI recommendation, Auto-format. Counts and filters use this.
- **Plain text** up to 10,000 characters with line breaks; no formatting; links become clickable on display. Compiled comments follow the template below so they read the same in the thread, in email and in the export.
- **An anchor** when it points at a passage: the quoted sentence and its paragraph. Overall and send-back comments have none. If the passage later changes, the comment shows "The text changed".
- **Open or resolved.** Anyone in the chain can resolve a comment on a standard they hold or review; a coordinator can resolve any. The readiness "Open comments" count uses this. Resolving is recorded.
- **Which publication and draft** it was written from, so "Comments (3)" on Step 4 shows the right ones.
- **A reply** attaches under the comment, one level deep. A send-back comment cannot be edited after sending, only replied to.
- **Visibility:** external reviewers never see Publish-origin comments; AI recommendations are listed in the AI-involvement report.

#### The compiled send-back comment

One comment per standard, written by the person who sent it, in this order; empty parts are omitted with their heading. The single Send back and Send all back write exactly the same text.

```
Readiness check, 16 Oct 2026 · 6.1 Financial Resources:
• Table wider than the page: Table 6.1 · Operating budget, page 118. 9 columns; Auto-format can scale or turn it landscape
• Oversized image: Figure 6.1, page 119. 3.2 MB · limit 1 MB
AI recommendations (suggestions only, from the AI readiness run of 16 Oct 2026):
• AI · Contradiction: Standard 6.1, page 118, table 1 · Standard 5.1, page 96, paragraph 1. Contradictions between standards are the first thing a committee flags. Suggested fix: Agree one figure and its date and use it in both standards.
Publisher review · 17 Oct 2026 · Alex Carter
Overall: Solid and well evidenced; two clarity points before this goes to the committee.
A · paragraph 1 · "Trustees serve staggered three-year terms … turns over in any year."
Say how many trustees are in each cohort.
Please resubmit by 24 Oct so the final can go out on time.
Please address these and resubmit; formatting is handled in the published copy.
```

#### The send-back email

| Part | Content |
| --- | --- |
| When | On every send back. When one action sends several standards to the same person (Send all back), that person gets **one digest** listing all of them, not one mail each. Posting review comments without a send back sends a lighter "New comment" mail; Remind sends the "Reminder" mail. An in-app notification is created at the same time. |
| To, from, reply | To the person the send back was addressed to. From "SPOL Accreditation" (a no-reply address). Replies go to the person who sent the standard back, so a reply reaches a human. The sender can choose to receive a copy. |
| Subject | "[SPOL] 6.1 Financial Resources sent back to you · Compliance Certification Draft 4"; digest: "[SPOL] 3 standards sent back to you · Compliance Certification Draft 4". |
| Opening | "Alex Carter sent 6.1 Financial Resources back to you on 17 Oct 2026 at 4:20 PM from the Publish workflow of Westmoor University's Compliance Certification (Draft 4). It returns to Writing; the Reader and Editor review it again when you resubmit." |
| Per standard | Heading "{code} {title}"; a counts line "2 findings · 1 AI recommendation · 1 review comment"; "In this draft: left out until it returns" or "keeps printing while you revise"; the compiled comment in full; a button **Open 6.1 in All Accreditation** that lands on the response with the thread open; a link to the publication. |
| Closing | "What happens next: edit the response, resolve the comments you have addressed, and resubmit; the readiness check runs again on the next draft." Then "Sent because you hold this standard. Recorded in the audit trail of Draft 4." No unsubscribe for workflow mail; a link to notification preferences. |
| Form | Readable as plain text and as a formatted mail; no attachments; no tracking; links never sign the reader in by themselves. |
| If it cannot be delivered | The sender sees "Email to Tracy Hall bounced" on the standard's row and the bounce is recorded; the send back itself stands. Actions taken while impersonating never email the impersonated person. |

## Credits, as the coordinator sees them

- **AI readiness:** 2 credits per standard not already checked + 5 for the cross-standard check. The quote is the charge and is shown before unlocking ("29 credits for 12 standards"; later "21 credits for 8 standards · 4 already checked"). "{n} left this year" always shows what is available now.
- **Never more than the quote.** If a run costs SPOL more than expected, SPOL carries it. A standard that cannot be finished is reported "not checked" and its 2 credits come back.
- **Not enough credits:** "Not enough credits · 29 needed, 20 left this year · Ask your administrator"; nothing starts and nothing is charged.
- **Refunds:** every standard not checked after a run started (could not be grounded, provider unavailable, refused, cancelled, timed out); the 5 cross-standard credits whenever that check does not run. Standards excluded at quote time (too long, personal data) are never charged and are named in the quote.
- **Cancel** keeps and charges what finished ("Cancelled · 4 of 12 checked"); the next quote counts those as already checked.
- **Approval:** above 50 credits a second coordinator approves, never the requester. The credits are reserved while waiting and released on decline or after 7 days. The approver sees "{name} asks you to approve AI readiness on Draft 4 · 61 credits · Approve · Decline"; the requester's card then reads "Approved by {name} · Reading…" or "Approval declined by {name} · Ask again".
- **Auto-format:** 4 credits, charged only when the run completes. Nothing to format or a failed run: nothing charged, and the message says so. Undo keeps the charge.
- **Deleting a draft** with a run in progress cancels the run and releases anything reserved.
- **Everything else is free** and never labelled AI: the readiness checks, send back, remind, comments, publishing in any format. Writers never see balances or cost lines.

## What is recorded

The audit trail gets an entry, with who, when and which version, for each of the following. Nothing is recorded for an action that failed.

| Area | Entries |
| --- | --- |
| Publications and versions | Created, renamed, duplicated, deleted (with the draft number), withdrawn (with the reason); selection, settings or cover changed (with what changed); section order changed. |
| Readiness | Each run (started, completed, cancelled, failed) with its score and counts; marked out of date and why; report downloaded. |
| AI readiness | Quote shown; run started, completed, cancelled, timed out, failed; approval requested, approved, declined, expired (with who); each finding decision with its reason; manipulation flag cleared (with the note). |
| Send back and comments | Each send back (standard, recipient, whether left out, which findings and AI recommendations); each returned standard; reminders; review comments posted or sent; comments created from Publish; comments resolved. |
| Preview and publish | Sections viewed; each confirmation ticked and unticked (with the cause when cleared); edits saved (and whether All Accreditation was updated); edits refused because the standard was in review; Auto-format runs (with the changes and credits) and undos; publishes (kind, format, pages, open findings and comments at that moment); downloads; links copied; files regenerated. |
| Credits | Every charge, refund and release, tied to the run it belongs to, so the audit trail and the credit history always agree. |
| Notifications | Each email sent or bounced, tied to the comment it carried. |

From these entries SPOL produces the per-submission AI-involvement report an institution can hand to an accreditor.

## Accessibility and copy

#### Accessibility (WCAG 2.2 AA)

- Every screen works with a keyboard alone, with a visible focus indicator, and reads sensibly with a screen reader: one page title, headings in order, every control named, every status change announced.
- A disabled control stays reachable and says why it is disabled, as visible text, never only in a tooltip.
- Dialogs take focus when they open, keep it inside, and return it to where the person was when they close. When the thing the person pressed has disappeared (a Send back button replaced by a "Sent back" chip), focus lands on what replaced it.
- Status is never shown by colour alone: a dot or chip always carries a word. Scores and bars have text equivalents.
- Text contrast at least 4.5:1, controls and icons 3:1. Touch targets at least 24 px on desktop and 44 px on a phone; inline sentences selected for comment are the one exception, as text in a paragraph.
- Reading mode and the viewer are keyboard-operable: page keys, Find with Enter and Shift+Enter, Esc to exit.
- Every screen works at phone width without sideways scrolling; wide tables scroll in their own box; the reading-mode comments panel becomes a bottom sheet.
- Bulk actions are explicit: Send all back lists every standard it will touch, who receives it and what the comment contains, and names the count on the button.
- Language checks are checks, not AI: findings say "Spelling", "Grammar", "Style"; the word "AI" and any credit line never appear on them.
- Verified so far: the prototype passes an automated WCAG 2.2 AA audit on every screen; the build must add screen-reader walkthroughs of the dialogs and the send-back flow, and a keyboard-only publish from start to finish.

#### Copy rules (one form everywhere)

- One lead sentence under each page title; one hint per control, directly under it; no floating notes.
- "Finding" for every check result; never "issue" or "item". "Items" only for the three confirmations.
- Rules: "Run checks again". AI: "Run again" (then the quote). Help: "How AI readiness works".
- "Submit date" is the field; "Submit by {d Mon yyyy}" is what prints.
- Dates always carry the year ("16 Oct 2026", with ", 4:12 PM" when time matters); file names use ISO dates.
- Holder: "{Status} · {Role} {Name}" ("In review · Reader Dr. Maria Santos"); "Approved · written by {Name}".
- Credits before: "Uses {n} credits for {scope} · {left} left this year"; after: "{n} credits used · {left} left this year · recorded in the audit trail". The same balance carries through a flow.
- Auto-format: button "Auto-format with AI", primary "Auto-format · {n} changes · 4 credits", chip "Auto-formatted".
- Footer: "Confirm {3−c} more to publish · {v} of {S} sections viewed".
- The approval blocker always reads "Not yet: {codes} not approved or excluded by send back"; other blockers are plain sentences in the order given under Rules.

## Scenarios the tests must cover

#### Demo data

Westmoor University; source SACSCOC-2018; template "Compliance Certification"; cycle 2024–2025. People: Alex Carter (coordinator), Priya Natarajan (editor), Dr. Maria Santos (reader and liaison), Tracy Hall (writer), Dr. James Okonkwo (CEO); all addresses on example.edu. Draft 4 at Step 4, 184 pages, 16 sections, 9 of 16 viewed; 12 of 12 standards selected, 3.3 not started, 4.2 and 6.2 in review; 17 open findings (score 89); 3 open comments; 1,866 credits left; an AI run available as a variant (score 58, four findings including the 6.1 vs 5.1 contradiction). Draft 1 and Draft 3 published; Draft 2 in progress at Step 1 (delete target); Fifth-Year Interim Report Final 1 published (withdraw target); cycle 2025–2026 empty.

1. **Edit after confirming.** Three confirmations, then a passage is edited and saved: confirmations cleared, readiness out of date, Undo of Auto-format gone, "Confirm 3 more to publish". Discard changes nothing.
2. **Undo after Auto-format.** Undo all: no refund, confirmations cleared, out of date. Then an edit: "Can't undo after editing".
3. **Send back and return.** 4.2 sent back and left out; when it comes back: included again, out of date, confirmations cleared, its AI findings still "Sent back" until the next run; after Run again, viewing all and confirming, a draft publishes; Final still says "Not yet: 3.3, 4.2, 6.2…" until the chain approves them.
4. **Cancel an AI run.** 4 of 12 done: "Cancelled · 4 of 12 checked", the rest refunded including the 5; the next quote "21 credits for 8 standards · 4 already checked".
5. **Impersonation.** An admin impersonating a coordinator who has confirmed 2 of 3: the checkboxes are disabled, nothing the admin reads counts as viewed, the coordinator's confirmations are untouched.
6. **Two confirmers.** A confirms one item after viewing all; B, with 9 of 16 viewed, sees "1 of 3 confirmed" and the lock; after viewing all, B confirms the other two and the draft can publish; each confirmation names who ticked it.
7. **Auto-format by someone else.** Three confirmations; another person runs Auto-format and it finishes first: the confirmations are cleared and the first person's Publish says "This draft changed since you confirmed it. Reload."
8. **Final blocked by one standard.** 3.3 and 6.2 approved, 4.2 left out: "Not yet: 4.2 not approved or excluded by send back"; when 4.2 returns approved, Run again and reconfirm, the final can publish.
9. **Template revised.** Draft 4 keeps its template version with a notice; Draft 5 starts on the new one, minus the dropped standard, with the banner.
10. **Writer fixes a finding.** Three confirmations; a writer fixes a spelling finding: out of date, confirmations kept; after Run checks again only "Findings and comments" is cleared, because the findings changed.
11. **Approval expires.** A 61-credit run waiting 7 days: "Approval expired · Ask again", credits released, nothing was blocked meanwhile.
12. **Delete with a run in flight.** The confirm dialog adds the warning; the run is cancelled and settled, the draft deleted, both recorded.
13. **Send all back.** Nine standards sent in one action: nine comments, one digest email per recipient, the unapproved ones left out, the readiness out of date.
14. **Order sections.** Reorder, apply, publish: the published document and its contents follow the new order; Draft 5 inherits it.

## Open questions for the SPOL team

1. What do the three response types pull from? The descriptions in Step 1 are placeholders.
2. When a standard is sent back from Publish, does review restart at the Reader when resubmitted, or resume at the level that sent it back?
3. Is "Confirm & Attest" the right term when the CEO and liaison sign the cover separately?
4. Does a Step 4 edit that ticks "Also update All Accreditation" need the standard's approval again?
5. Is 4 credits for Auto-format and 2 per standard for AI readiness the pricing the team wants to launch with?
6. **WProofreader contract:** cloud or self-hosted? Cloud sends narrative text to the vendor's servers with no published retention period; self-hosted keeps it inside SPOL. If cloud, the dossier and the order form name WProofreader as a sub-processor. And does the team want its AI writing assistant at all? If yes it sits behind the institution's AI switches, inside the Assist menu, never as the vendor's own badge.
7. **Specified in text, not shown in the prototype:** the second-coordinator approval screen; template-revision notices; Withdraw with reason, Duplicate, Rename and Regenerate; reports with more than 24 standards; the "Which standard should go back?" picker; Remind with its once-a-day limit; loading, error and offline states. Each is defined here so the behaviour exists if built; none is required for the first release.
8. Dr. James Okonkwo is the CEO and Priya Natarajan the editor in the demo data; confirm the real role holders for the demo.

## Change log

| Date | Change |
| --- | --- |
| 23 Oct 2026 | Readiness score rebuilt: the thirteen free checks grouped into six weighted categories (Evidence 25, Completeness 20, Review 15, Language 10, Print and export 15, Accessibility 15), each category averaged over the standards it applies to and capped at its weight; approvals shown beside the score, not in it. Demo score 89. |
| 22 Oct 2026 | Two companion documents added: the readiness checks (free) and the AI checks. Rewritten as a functional specification. Data structures, service contracts, ledger rules and per-control accessibility attributes moved to the engineering notes. |
| 21 Oct 2026 | Answers for the build team: the readiness report workbook, comment structure, the send-back email, severity definitions, the free checks mapped to the v6.0.0.8 build. Markdown copies of every document published beside the HTML. |
| 20 Oct 2026 | Send all back with AI recommendations as comments; the dossier linked from the AI panel in every state; the Auto-format dialog relaid out; Order sections; output options. Accessibility audit of the live site: every finding fixed. |
| 19 Oct 2026 | Free checks aligned with WProofreader; four rule checks added; language checks never labelled AI. |
| 18 Oct 2026 | Accessibility and enterprise-UX audit of the prototype; Published landing state; prototype fixes. |
| 17 Oct 2026 | Demo feedback: working row menus, required markers, In progress and Published tabs, the AI panel can be hidden, section navigation and reading mode with comments; review in reading mode; section content per page; Auto-format shown end to end with before and after; the report-wide block removed from Step 2. |
| 16 Oct 2026 | Review any standard from Readiness; inline review comments and the compiled send-back comment; per-standard finding details; the AI readiness dossier; the AI behaviour spec rewritten clean. |
| 15 Oct 2026 | Ten review passes over the first version: consistency, states and edge cases, acceptance tests, credits, accessibility and copy. |

Prototype and documents: https://rajatcord.github.io/spol-publish-prototype/ · sources in the SPOL repository under recovery/artifacts/publish-workflow-canvas/.
