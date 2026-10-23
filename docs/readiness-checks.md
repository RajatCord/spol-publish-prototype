---
title: "SPOL Publish · the readiness checks (free)"
source: readiness-checks.html
format: markdown export of the HTML document; tables are pipe tables; the HTML remains the reference rendering
---

Specification · Readiness checks (free) · v2 · 23 Oct 2026

# The readiness checks

The thirteen checks SPOL runs on a report before it is published. They cost nothing, use no credits and are never labelled AI. This page says what each one looks at, what it reports, how severe a finding is, who fixes it and how, and how the findings add up to the readiness score. The AI checks are a separate document.

## In short

- **Thirteen checks, two engines.** SPOL's own rules check structure, links, evidence, placeholders, the cover and open work. WProofreader, licensed by SPOL, checks spelling, grammar, punctuation and style.
- **A check answers a question a machine can settle** without judgment: is something present, well-formed, within a limit, unresolved. Anything that needs reading goes to the AI checks instead.
- **Six parts, one score.** The thirteen checks are grouped into six parts, each worth a fixed share of 100. A part can only lose its own share, and one standard can only lose its own slice of a part.
- **Findings never block a draft.** They travel to the writer through Send back, or are fixed in Preview by Auto-format, or are listed in the report download.

## When they run

- **On the Readiness step,** every time the person presses Run checks again, and automatically the first time Step 2 opens for a draft. All thirteen run together on the current content ("Checking {n} of {m} sections", with Cancel). A run finishes within ten minutes or reports "Checks couldn't finish · Run again" and keeps the previous result on screen.
- **As you type,** for the language checks only: WProofreader marks spelling, grammar, punctuation and style in the All Accreditation response editor with the same dictionaries the readiness run uses, so most language findings never reach Publish.
- **Before AI readiness,** if the rules result is out of date, the rules run again first ("Running checks first…").
- **The result goes out of date** when anything that affects the report changes: the selection, content settings or response type; a standard's narrative, evidence or comments; Auto-format or an edit in Preview; a send back that leaves a standard out; a standard returning. The old result stays visible with "Out of date · Run again".

## What they produce

- **Findings on standards.** Each finding names the standard, the check, the severity, where it is (page, paragraph or element), what is wrong in one line, and what would fix it. They appear under the standard's row on Readiness, in the Review panel, in the send-back comment and in the report download.
- **Report-wide findings.** Things that belong to the document rather than to one standard: hidden text removed, formatting counted once in the Formatting bar. They are shown where they are acted on (Preview, the download) and count once, on the report itself, in the part they belong to (Print and export for hidden text and file names, Completeness for the cover).
- **The readiness score** out of 100, built from six parts, each shown as a bar with its points ("Evidence 21 / 25"), and the sum printed beside the ring ("21 + 18 + 14 + 9 + 13 + 14 = 89").
- **Two verdicts**, separate from the score: "Internal draft: ready" (unless no standard is selected) and "Final: ready" or "Final: not yet · {codes} not approved". Approvals decide Final; they are shown beside the score ("Approvals 9 of 12") but are not part of it.
- **A recommendation paragraph** assembled from the findings with templated sentences, no AI: "Publish an internal draft now. For a final: send 4.2 and 6.2 back for evidence, get 3.3 written…"
- **The Excel download** of the whole run, described under Where findings go.

## The thirteen checks

Each check below gives what it looks at, what a finding says, the severity rule, who fixes it and what the check never does.

### 1 · Spelling, grammar and punctuation

- **Engine:** WProofreader, with SPOL's accreditation dictionary (accreditor names, standard titles, terms such as QEP and IE) and the institution's own dictionary (programme names, acronyms, people).
- **Looks at:** every narrative passage of every selected standard; not the evidence files, not the cover.
- **Finding:** "Spelling · paragraph 2 · "occurence" → "occurrence"". One finding per word occurrence; the same word misspelt five times is five findings, because each needs a change.
- **Severity:** Medium for a misspelt word in neither dictionary; Low for grammar and punctuation, and for a word only the institution's dictionary knows.
- **Fixed by:** the writer, accepting or rejecting the suggestion in the editor. Publish never changes the text.
- **Never:** labelled AI, counted in credits, or rewritten automatically. The dashboard names the engine once: "language checks by WProofreader".

### 2 · Style

- **Engine:** WProofreader style-guide rules: SPOL's accreditation style guide (third person, one name for the accreditor, date form, no first-person plural) plus rules the institution adds in its admin panel.
- **Finding:** "Style · paragraph 3 · "We believe" · first person; the style guide uses "the University"", with the rule's name.
- **Severity:** Low, except rules the institution marked "required", which are Medium.
- **Fixed by:** the writer. Not checked when no style guide is configured.

### 3 · Link validation

- **Looks at:** every hyperlink, linked SPOL document, evidence file reference, and every reference to an objective or outcome in the selected standards.
- **Finding:** "Changed link · paragraph 5 · Mission statement page now redirects; the text still reads as before" or "Broken link · Board Minutes, 12 Sep 2025 · the document no longer exists".
- **Severity:** High when a linked SPOL document or evidence file no longer exists or cannot be opened (the reader would hit a dead end); Medium for an external address that fails twice or a reference to a deleted objective or outcome; Low for a redirect or a certificate warning.
- **Fixed by:** the writer relinks; a Validate button re-checks one link without a full run. Not checked when there is no network or the target needs a sign-in.

### 4 · Table format

- **Looks at:** every table against the template's printable page width and page breaks.
- **Finding:** "Table wider than the page · Table 3.1 · Board composition, page 15 · 7 columns at 100 % exceed the print width; Auto-format can scale or turn it landscape".
- **Severity:** High when cells would be cut off at full size; Medium for a missing header row or a row split across pages; Low when it fits only after scaling below 85 % (Auto-format will turn the page landscape instead).
- **Fixed by:** Auto-format in Preview, which shows before and after. One finding per table, never per cell.

### 5 · Image sizes

- **Looks at:** every image's dimensions, file size and resolution at the size it prints.
- **Finding:** "Oversized image · Figure 4.2, page 61 · 4.1 MB · limit 1 MB; Auto-format can resize it".
- **Severity:** High when larger than the page so it would be cropped; Medium when over 1 MB or too low a resolution to print; Low when within limits but without a caption.
- **Fixed by:** Auto-format in Preview (resampled to the page width, nothing cropped). Not checked when the image file is missing, which the Missing attachments check reports instead.

### 6 · Alt text

- **Looks at:** every image for a text alternative.
- **Finding:** "Alt text missing · Figure 6.1, page 119".
- **Severity:** Medium for a missing alternative; Low when the alternative is just the file name.
- **Fixed by:** the writer in the editor. Counted in the Accessibility bar.

### 7 · Headings

- **Looks at:** the document outline as it will print.
- **Finding:** "Heading level · "Results", page 62 · H4 directly under H2 · one level skipped".
- **Severity:** Medium for a skipped level or an empty heading; Low for duplicate numbering.
- **Fixed by:** Auto-format in Preview (the words are unchanged). Counted in the Accessibility bar.

### 8 · Illegal characters

- **Looks at:** file names of evidence and of the output, and the narrative, against the character list kept in System Settings.
- **Finding:** "Illegal character · Board Minutes 12/09/2025.pdf · "/" is not allowed in a file name" or "Illegal character · paragraph 4 · a control character that breaks export".
- **Severity:** High for a file name the export or file system rejects; Medium for a narrative character on the institution's list that breaks export or rendering; Low for one SPOL substitutes silently (smart quotes, non-breaking spaces).
- **Fixed by:** Auto-format substitutes file-name characters; the writer fixes narrative ones.

### 9 · Missing attachments

- **Looks at:** the number of evidence documents attached to each selected standard against the number the coordinator set as expected.
- **Finding:** "Expected document missing · Evidence list · Assessment report 2024–25 · expected 3 attachments, 1 attached" or "Expected evidence count not set · 0 documents".
- **Severity:** High when the expected count is set and nothing is attached, or when no expected count is set at all (the standard cannot be judged complete); Medium for fewer than expected; Low for more than expected.
- **Fixed by:** the writer uploads; the coordinator sets the expected count. Not checked for a standard not started. A cited file that was deleted after upload is also reported here, as High.

### 10 · Placeholder text

- **Looks at:** the narrative and the cover for text that was never replaced: bracketed or templated placeholders such as "[Name of Institution]" or "<< Enter address here >>", "TBD", "lorem".
- **Finding:** "Placeholder · cover · "[Name of Institution]"".
- **Severity:** High, always: a placeholder in print is the most visible failure a reviewer can see.
- **Fixed by:** the writer, or Step 3 for the cover.

### 11 · Required cover fields

- **Looks at:** the institution name and address, the preparer, the required signers and the submit date on the cover.
- **Finding:** "Cover · Accreditation Liaison · no one holds this role · Assign in Admin".
- **Severity:** High when a required field is missing (blocks a final, never a draft); Medium when a signer is named but their date is unsigned.
- **Fixed by:** Step 3, or Admin for the profile and role holders. Listed under "Before you publish" on Step 4.

### 12 · Open comments and unresolved edits

- **Looks at:** the comment thread and the pending tracked changes of each selected standard.
- **Finding:** "Open comment · paragraph 2 · "Clarify the recusal rule." · Priya Natarajan, 15 Oct 2026", quoting the comment with its author and date.
- **Severity:** Medium. Nothing undecided should go to print.
- **Fixed by:** resolving the comment in the thread or accepting the edit in the editor. Counted in the Comments bar. Not checked when the comment service is unavailable.

### 13 · Hidden text

- **Looks at:** the whole document, on every run, for text that would not print or would not be seen: white-on-white, zero-size, zero-width characters, text outside the page, hidden comments in the markup.
- **Finding:** report-wide, "Hidden text removed from 2.1 · see the standard", shown as a banner on Readiness and in the download.
- **Severity:** High, counted on the report itself in Print and export. The text is removed from what is sent to print and to AI; the standard itself is unchanged so the writer can see what was there.
- **Why it exists:** it protects the institution from accidental leftovers and from text planted to steer a reader or an AI.

## Severity, in one table

Three levels, one meaning each, applied by the rule, never by a person. **High**: the published document would be wrong, incomplete or unprintable for a reviewer, or a final could not be submitted. **Medium**: a reviewer would notice and ask, or evidence or review is incomplete. **Low**: polish, fixed by a tool or safely ignored.

| Check | High | Medium | Low | Not checked when |
| --- | --- | --- | --- | --- |
| Spelling, grammar, punctuation | — | Misspelt word in neither dictionary | Grammar, punctuation; a word only the institution's dictionary knows | Language service unavailable; narrative empty |
| Style | — | A rule the institution marked required | Every other rule | No style guide |
| Link validation | SPOL document or evidence file gone or unreadable | External address failing twice; deleted objective or outcome | Redirect; certificate warning | No network; target needs sign-in |
| Table format | Wider than the printable page | No header row; row split across pages | Fits only below 85 % | Width cannot be measured |
| Image sizes | Larger than the page | Over 1 MB; too low a resolution | No caption | File missing |
| Alt text | — | No alternative | Alternative is the file name | — |
| Headings | — | Skipped level; empty heading | Duplicate numbering | — |
| Illegal characters | File name the export rejects | Narrative character on the institution's list | Character SPOL substitutes | — |
| Missing attachments | Nothing attached; or no expected count set; or a cited file deleted | Fewer than expected | More than expected | Standard not started |
| Placeholder text | Any placeholder | — | — | — |
| Required cover fields | A required field missing | Signer named, date unsigned | — | — |
| Open comments and edits | — | Open comment or pending edit | — | Comment service unavailable |
| Hidden text | Found and removed (report-wide) | — | — | — |

**One finding per element.** A table with nine wide columns is one finding; a figure that is both oversized and uncaptioned is one finding at the higher severity; a word misspelt five times is five, because each is a separate change. Counts on the dashboard and in the download are counts of findings, never of cells, words or characters.

## The six parts

Each part answers one question a coordinator asks before publishing, carries a fixed weight, and contains only its own checks. The weights add up to 100.

| Part | The question it answers | Checks | Weight | Applies to |
| --- | --- | --- | --- | --- |
| **Evidence** | Is every claim backed by something a reviewer can open? | Missing attachments · Link validation | 25 | Each standard with a response |
| **Completeness** | Is everything that should print actually there? | Placeholder text · Required cover fields | 20 | Each selected standard, and the report itself (cover) |
| **Review** | Is anything still being discussed or edited? | Open comments and unresolved edits | 15 | Each standard with a response |
| **Language** | Does it read correctly? | Spelling, grammar and punctuation · Style | 10 | Each standard with a response |
| **Print and export** | Will it print and export cleanly? | Table format · Image sizes · Illegal characters · Hidden text | 15 | Each standard with a response, and the report itself (file names, hidden text) |
| **Accessibility** | Can everyone read it? | Alt text · Headings | 15 | Each standard with a response |

Why these weights: evidence is what an accreditor judges a standard on; completeness is what makes a report submittable; review, print and accessibility each carry a real cost if missed; language matters least to the outcome and is mostly fixed as people type. The weights are set by SPOL, the same for every institution, and printed in "How the score is built".

## The score

### Points for a finding

High = 3 points · Medium = 1 point · Low = 0 points. A unit (one standard, or the report itself) that collects 6 or more points in a part has used up that part entirely; nothing beyond 6 counts, so a single badly broken standard cannot drag a part below what that standard is worth.

### The calculation

For each part *p* with weight *wp*, applied to *np* units:

1. For each unit *u*, add up the points of its findings in that part: *Pp,u*.
2. The unit's share of the part is *qp,u* = 1 − min(*Pp,u*, 6) ÷ 6, a number between 0 and 1.
3. The part's quality is the average over its units: *Qp* = (Σu *qp,u*) ÷ *np*.
4. The part's points are *wp* × *Qp*, rounded **down** to a whole number.
5. The readiness score is the sum of the six parts' points.

Why it behaves:

a part can never give or take more than its weight; one unit can never move a part by more than

wp

÷

np

; one High finding moves it by at most half of that. Rounding each part down means a part shows full marks only when it has nothing scored to fix, and the total always equals the sum of the parts on screen. Adding standards does not dilute or inflate the score, because every part is an average.

### Rules at the edges

- **Not started.** A selected standard with no response scores 0 in Completeness (there is nothing to print) and is left out of the other five parts, which have nothing to check.
- **Left out by a send back.** The standard is removed from every part until it returns; the score is about what would print now.
- **Not checked.** A unit a check could not run on (service down, no style guide) is left out of that part's average, and the check shows "Partially checked". If a whole part could not run, it shows "—" and the total reads "{points} of {available}" (for example "79 of 90") until it runs.
- **Approvals** are not in the score. They decide whether a final can be published, and they are shown beside the score so nobody mistakes 100 for "ready to submit".
- **The AI score** is separate and never mixed in.

### Worked example: the demo report

Twelve standards selected; 3.3 not started, so eleven have a response; the report itself has no findings.

| Part | Units | Units that lost points | Q | Points |
| --- | --- | --- | --- | --- |
| Evidence (25) | 11 | 4.2: 2 High = 6 → 0 · 6.2: High + Medium = 4 → ⅓ | 9.33 ÷ 11 = 0.848 | 21 |
| Completeness (20) | 13 (12 standards + report) | 3.3: no response → 0 | 12 ÷ 13 = 0.923 | 18 |
| Review (15) | 11 | 1.1, 3.1, 5.2: 1 open comment each → ⅚ | 10.5 ÷ 11 = 0.955 | 14 |
| Language (10) | 11 | 1.1: 1 Medium → ⅚ · 2.1: 2 Medium → ⅔ (its Low style finding counts 0) | 10.5 ÷ 11 = 0.955 | 9 |
| Print and export (15) | 12 (11 standards + report) | 3.1: 1 High → ½ · 4.2: 1 Medium → ⅚ · 6.1: High + Medium → ⅓ | 10.67 ÷ 12 = 0.889 | 13 |
| Accessibility (15) | 11 | 4.2: 1 Medium → ⅚ | 10.83 ÷ 11 = 0.985 | 14 |
| **Readiness score** | **89** |  |  |  |

Shown on the dashboard as "21 + 18 + 14 + 9 + 13 + 14 = 89", with "Final: not yet · 3.3, 4.2, 6.2 not approved" beside it. Fixing both missing documents on 4.2 would lift Evidence to 0.939 and its points to 23: the score moves only by what Evidence is worth, and only as far as 4.2's slice of it.

## Where findings go

- **Under the standard's row** on Readiness, one line each: "{Severity} · {Kind} · {where} — {detail}", with "Open {code} in All Accreditation".
- **In the Review panel,** where the passages that carry a finding are marked in amber in the response as it will print.
- **In a send back,** as the first part of the compiled comment the holder receives, each finding ticked by default and untickable. Send all back does this for every standard with findings at once.
- **In Preview,** for formatting findings: Auto-format fixes tables, images, headings, spacing, citations and contents in one pass and shows every change before and after.
- **In the Excel download** of the run on screen (including an out-of-date one): a Summary sheet, one row per finding with standard, check, severity, location, description, suggested action, report-wide, left out, status and holder; one row per standard with its counts and chain state; the AI findings when a run exists; report-wide findings; and one row per check with its status. Plain values, filters on every sheet, no formulas. A CSV of the findings alone is also offered.

## Check status and messages

| Status | Meaning | Shown as |
| --- | --- | --- |
| Passed | The check ran on everything and found nothing | Green "Passed"; a clean standard reads "All 13 checks passed · approved {date}" |
| Issues found | The check ran and found findings | The count of findings, never of cells or words |
| Partially checked | The check ran but some standards or items could not be checked | "{n} not checked" with the reason, for example "3 standards not started" |
| Not checked | The check did not run | "Not checked" with the reason (service unavailable, no style guide, cancelled) |

- Before any run: the ring shows "—", verdicts "Not checked yet", the lists are hidden, Next is still available.
- While running: "Checking {n} of {m} sections", Cancel. Cancelled: "Checks cancelled · Run checks". Not finished in ten minutes: "Checks couldn't finish · Run again", previous result kept.
- After a change: "Out of date · Run again" on the dashboard and on Step 4.
- The last-run line: "Last run {date, time} · {k} of 13 checks completed · language checks by WProofreader".

## Acceptance

- **Full run.** Given the demo data. When Run checks again. Then all thirteen checks report a status, the score reads 89 with "21 + 18 + 14 + 9 + 13 + 14 = 89", the six bars show 21 / 25, 18 / 20, 14 / 15, 9 / 10, 13 / 15 and 14 / 15, and 17 findings are listed under their standards.
- **One per element.** Given a table with nine wide columns. Then exactly one Table format finding, High, naming the table and page.
- **Language engine.** Given "occurence" in 2.1. Then a Medium Spelling finding with the suggestion, no AI label and no credit line anywhere near it; the same word is marked in the editor as you type.
- **Institution dictionary.** Given "Westmoor" added to the institution's dictionary. Then it is never reported; a word only in that dictionary used in another institution's report is Low, not Medium.
- **Placeholder.** Given "[Name of Institution]" on the cover. Then a High finding, listed under "Before you publish", and the cover preview shows it.
- **Expected count not set.** Given 6.2 with no expected evidence count. Then High "Expected evidence count not set · 0 documents" and the Evidence bar excludes it from "complete".
- **Hidden text.** Given white-on-white text in 2.1. Then the banner "Hidden text removed from 2.1 · see the standard", the download lists it, the standard's text in All Accreditation is unchanged, and Print and export loses at most 15 ÷ 12 ÷ 2 ≈ 0.6 of a point.
- **Proportion.** Given any report. When every finding in one part is resolved. Then the score rises by exactly that part's lost points and no other bar moves. Given a standard with ten High findings in one part. Then that part loses no more than that standard's slice of it.
- **Out of date.** Given a run and a writer's change to 1.1. Then "Out of date · Run again"; the old findings stay listed until the next run.
- **Cancelled.** When Cancel during a run. Then "Checks cancelled · Run checks", the previous result stays, nothing is recorded as a completed run.
- **Download.** When Download report (Excel). Then a workbook named with the institution, template, draft and run date, six sheets, 17 finding rows, one row per check with status, no formulas.

## Mapping to the v6.0.0.8 build

| This specification | v6 build | Change |
| --- | --- | --- |
| Spelling, grammar and punctuation | Spell Check, under "AI can fix these" | Move out of the AI group; it is neither AI nor fixed by Publish. Name the engine once in the last-run line. |
| Style | — | New. |
| Link validation | Link Validation | Keep. Add severity by cause; the "Document file not found on server" case is High. |
| Table format | Table Format, "181 issues" | Keep; count tables, not cells. Fixed in Preview by Auto-format, not on this step. |
| Image sizes | Image Sizes | Keep; fixed in Preview by Auto-format. |
| Alt text, Headings | — | New; both count in the Accessibility bar. |
| Illegal characters | Illegal Characters ("0 narrative · 4 files") | Keep, with the severity split by file name versus narrative. |
| Missing attachments | Missing Attachments ("87 standards") | Keep; count standards with a shortfall, and report "expected count not set" as its own High finding. |
| Placeholder text, Required cover fields | — | New; the v6 cover shows exactly the placeholders this catches. |
| Open comments and unresolved edits | Narrative Comments, "Not Checked" | It must run on every readiness run. |
| Hidden text | — | New; report-wide. |
| — | Issue Summary | A view, not a check; remove from the checks table. |
| — | "AI can fix these" / "These need your review" grouping | Replace with "Fixed in Preview with Auto-format" (tables, images, headings) and "Fixed by the writer"; nothing on this step carries an AI label unless it costs credits. |

Part of the Publish specification set: https://rajatcord.github.io/spol-publish-prototype/ · The AI checks are described in "The AI checks"; the user-facing explanation is "How AI readiness works".
