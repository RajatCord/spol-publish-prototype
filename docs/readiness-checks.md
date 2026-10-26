---
title: "SPOL Publish · the readiness checks (free)"
source: readiness-checks.html
format: markdown export of the HTML document; tables are pipe tables; the HTML remains the reference rendering
---

Specification · Readiness checks (free) · v5 · 26 Oct 2026

# The readiness checks

SPOL runs thirteen checks on a report before it is published, grouped into six categories. Each category is worth a fixed share of the readiness score out of 100. The checks cost nothing, use no credits and are never labelled AI. This page defines the six categories, then each check within its category: what it looks at, what it reports, how severe a finding is and who fixes it. It ends with how the findings add up to the score. The AI checks are a separate document.

## In short

- **Six categories, thirteen checks, one score.** Attachments and links 25, Completeness 20, Open items 15, Language 10, Print and export 15, Accessibility 15. The weights add up to 100, and the score is the sum of the six categories.
- **Each category can lose only its own share.** A category loses points only for its own findings, averaged over the standards it applies to. One standard can only lose its own slice of a category.
- **A check answers a question a machine can settle** without judgment: is something present, well-formed, within a limit, unresolved. Anything that needs reading goes to the AI checks instead.
- **Two engines.** SPOL's own rules run eleven of the checks. WProofreader, licensed by SPOL, runs the two Language checks.
- **Findings never block a draft.** They travel to the writer through Send back, are fixed in Preview by Auto-format, or are listed in the report download. Approvals decide whether a final can go; they are shown beside the score, not inside it.

## The six categories

Each category answers one question a coordinator asks before publishing, carries a fixed weight, and contains only its own checks. Every check belongs to exactly one category.

| Category | The question it answers | Checks | Weight | Applies to |
| --- | --- | --- | --- | --- |
| **Attachments and links** | Is every expected document attached, and does every link open? | 1 Missing attachments · 2 Link validation | 25 | Each standard with a response |
| **Completeness** | Is everything that should print actually there? | 3 Placeholder text · 4 Required cover fields | 20 | Each selected standard, and the report itself (the cover) |
| **Open items** | Is anything still being discussed or edited? | 5 Open comments and unresolved edits | 15 | Each standard with a response |
| **Language** | Does it read correctly? | 6 Spelling, grammar and punctuation · 7 Style | 10 | Each standard with a response |
| **Print and export** | Will it print and export cleanly? | 8 Table format · 9 Image sizes · 10 Illegal characters · 11 Hidden text | 15 | Each standard with a response, and the report itself (output file name, hidden text) |
| **Accessibility** | Can everyone read it? | 12 Alt text · 13 Headings | 15 | Each standard with a response |
| **Total** | **100** |  |  |  |

Why these weights: the attached evidence is the first thing an accreditor opens; completeness is what makes a report submittable; review, print and export, and accessibility each carry a real cost if missed; language matters least to the outcome and is mostly fixed as people type. The weights are set by SPOL, are the same for every institution, and are printed in "How the score is built" on the dashboard.

## Free and AI: one owner per question

The free readiness checks and the paid AI checks never measure the same thing. Each question about a report has exactly one owner, and each score is built only from its own side's findings.

| Question about the report | Answered by the free readiness checks | Answered by the AI checks |
| --- | --- | --- |
| Is every expected document attached, and does every link open? | Attachments and links (checks 1, 2) | Never |
| Does the text back each claim with something it cites, and does the cited extract agree? | Never | Evidence sufficiency |
| Is everything that should print filled in? | Completeness (checks 3, 4; a standard not started) | Never |
| Does the response make its case and answer every reviewer question? | Never | Argument strength |
| Is anything still being discussed or edited? | Open items (check 5) | Never |
| Is the spelling, grammar, punctuation and house style right? | Language (checks 6, 7) | Never |
| Will a reviewer misread a passage? | Never | Clarity |
| Do numbers, dates and named roles agree across standards? | Never | Consistency |
| Will tables, images and file names print and export cleanly? | Print and export (checks 8, 9, 10) | Never |
| Is there text no reader can see? | Print and export (check 11, hidden text, removed before AI reads anything) | Never |
| Does visible text try to steer a reader or an AI? | Never | Manipulation |
| Can everyone read it (alt text, headings)? | Accessibility (checks 12, 13) | Never |
| Which standards would a committee likely cite? | Never | Reviewer readiness (from AI findings only) |
| Is every standard approved? | Neither score. Approvals are shown beside the readiness score and decide whether a final can be published. |  |

- **One owner per question.** Every question above is answered by exactly one side. The free checks never judge meaning; the AI checks never report anything a free check owns.
- **AI findings in free territory are dropped.** The AI is told what it must not report, and SPOL drops any AI finding about spelling, grammar, punctuation, style, file counts, broken links, layout, alt text, headings, placeholders, hidden text or open comments before anyone sees it.
- **No finding is in both scores.** The readiness score is built only from the thirteen free checks; the AI review score only from AI findings. Neither ever reads the other's findings.
- **Two scores, two names, never combined.** "Readiness score" (free, six categories, out of 100) and "AI review score" (paid, out of 100). They are shown side by side and are never added, averaged or merged into one number.
- **No shared words.** The six free categories and the five AI areas use different names, so a bar on one side can never be mistaken for a bar on the other.
- **Neither score decides publishing.** A final needs every selected standard approved and the free blocking conditions met; the AI manipulation flag also blocks a final until a coordinator clears it, as a condition, not as a score.

## When they run

- **On the Readiness step,** every time the person presses Run checks again, and automatically the first time Step 2 opens for a draft. All thirteen checks run together on the current content ("Checking {n} of {m} sections", with Cancel). A run finishes within ten minutes or reports "Checks couldn't finish · Run again" and keeps the previous result on screen.
- **As you type,** for the two Language checks only: WProofreader marks spelling, grammar, punctuation and style in the All Accreditation response editor with the same dictionaries the readiness run uses, so most Language findings never reach Publish.
- **Before AI readiness,** if the result is out of date, the checks run again first ("Running checks first…").
- **The result goes out of date** when anything that affects the report changes: the selection, content settings or response type; a standard's narrative, evidence or comments; Auto-format or an edit in Preview; a send back that leaves a standard out; a standard returning. The old result stays visible with "Out of date · Run again".

## What they produce

- **Findings.** Each finding names its category, its check, the standard (or "Report" for the cover and output), the severity, where it is (page, paragraph or element), what is wrong in one line, and what would fix it.
- **Six category scores,** each shown as a bar with its points ("Attachments and links 21 / 25").
- **The readiness score** out of 100, the sum of the six category scores, printed beside the ring as that sum ("21 + 18 + 14 + 9 + 13 + 14 = 89").
- **Two verdicts,** separate from the score: "Internal draft: ready" (unless no standard is selected) and "Final: ready" or "Final: not yet · {codes} not approved". Approvals decide Final and are shown beside the score ("Approvals 9 of 12 · they decide Final, not the score").
- **A recommendation paragraph** assembled from the findings with templated sentences, no AI: "Publish an internal draft now. For a final: send 4.2 and 6.2 back for evidence, get 3.3 written…"
- **The Excel download** of the whole run, described under Where findings go.

## The checks, by category

Within each category, each check gives what it looks at, what a finding says, the severity rule and who fixes it. The full severity table follows in Severity and points.

### Attachments and links · weight 25

#### 1 · Missing attachments

- **Looks at:** the number of evidence documents attached to each standard with a response, against the number the coordinator set as expected, and whether every cited file still exists.
- **Finding:** "Expected document missing · Evidence list · Assessment report 2024–25 · expected 3 attachments, 1 attached" or "Expected evidence count not set · 0 documents".
- **Severity:** High when the expected count is set and nothing is attached, when no expected count is set at all (the standard cannot be judged complete), or when a cited file was deleted after upload; Medium for fewer than expected; Low for more than expected.
- **Fixed by:** the writer uploads; the coordinator sets the expected count.

#### 2 · Link validation

- **Looks at:** every hyperlink, linked SPOL document, evidence file reference, and every reference to an objective or outcome in the standard.
- **Finding:** "Changed link · paragraph 5 · Mission statement page now redirects; the text still reads as before" or "Broken link · Board Minutes, 12 Sep 2025 · the document no longer exists".
- **Severity:** High when a linked SPOL document or evidence file no longer exists or cannot be opened; Medium for an external address that fails twice, or a reference to a deleted objective or outcome; Low for a redirect or a certificate warning.
- **Fixed by:** the writer relinks; a Validate button re-checks one link without a full run.

### Completeness · weight 20

#### 3 · Placeholder text

- **Looks at:** the narrative of each selected standard, and the cover, for text that was never replaced: bracketed or templated placeholders such as "[Name of Institution]" or "<< Enter address here >>", "TBD", "lorem".
- **Finding:** "Placeholder · cover · "[Name of Institution]"".
- **Severity:** High, always: a placeholder in print is the most visible failure a reviewer can see.
- **Fixed by:** the writer, or Step 3 for the cover.
- **A standard not started** has nothing to print. It scores 0 in Completeness without a finding being raised; its row says "No response yet".

#### 4 · Required cover fields

- **Looks at:** the institution name and address, the preparer, the required signers and the submit date on the cover. Counted on the report itself.
- **Finding:** "Cover · Accreditation Liaison · no one holds this role · Assign in Admin".
- **Severity:** High when a required field is missing (blocks a final, never a draft); Medium when a signer is named but their date is unsigned.
- **Fixed by:** Step 3, or Admin for the profile and role holders. Also listed under "Before you publish" on Step 4.

### Open items · weight 15

#### 5 · Open comments and unresolved edits

- **Looks at:** the comment thread and the pending tracked changes of each standard with a response.
- **Finding:** "Open comment · paragraph 2 · "Clarify the recusal rule." · Priya Natarajan, 15 Oct 2026", quoting the comment with its author and date.
- **Severity:** Medium. Nothing undecided should go to print.
- **Fixed by:** resolving the comment in the thread or accepting the edit in the editor.

### Language · weight 10

#### 6 · Spelling, grammar and punctuation

- **Engine:** WProofreader, with SPOL's accreditation dictionary (accreditor names, standard titles, terms such as QEP and IE) and the institution's own dictionary (programme names, acronyms, people).
- **Looks at:** every narrative passage of each standard with a response; not the evidence files, not the cover.
- **Finding:** "Spelling · paragraph 2 · "occurence" → "occurrence"". One finding per word occurrence: the same word misspelt five times is five findings, because each needs a change.
- **Severity:** Medium for a misspelt word in neither dictionary; Low for grammar and punctuation, and for a word only the institution's dictionary knows.
- **Fixed by:** the writer, accepting or rejecting the suggestion in the editor. Publish never changes the text, never labels this AI and never charges credits; the dashboard names the engine once: "language checks by WProofreader".

#### 7 · Style

- **Engine:** WProofreader style-guide rules: SPOL's accreditation style guide (third person, one name for the accreditor, date form, no first-person plural) plus rules the institution adds in its admin panel.
- **Finding:** "Style · paragraph 3 · "We believe" · first person; the style guide uses "the University"", with the rule's name.
- **Severity:** Medium for a rule the institution marked "required"; Low for every other rule.
- **Fixed by:** the writer.

### Print and export · weight 15

#### 8 · Table format

- **Looks at:** every table against the template's printable page width and page breaks.
- **Finding:** "Table wider than the page · Table 3.1 · Board composition, page 15 · 7 columns at 100 % exceed the print width; Auto-format can scale or turn it landscape".
- **Severity:** High when cells would be cut off at full size; Medium for a missing header row or a row split across pages; Low when it fits only after scaling below 85 % (Auto-format turns the page landscape instead).
- **Fixed by:** Auto-format in Preview, which shows every change before and after.

#### 9 · Image sizes

- **Looks at:** every image's dimensions, file size and resolution at the size it prints.
- **Finding:** "Oversized image · Figure 4.2, page 61 · 4.1 MB · limit 1 MB; Auto-format can resize it".
- **Severity:** High when larger than the page so it would be cropped; Medium when over 1 MB or too low a resolution to print; Low when within limits but without a caption.
- **Fixed by:** Auto-format in Preview (resampled to the page width, nothing cropped). A missing image file is reported by Missing attachments instead.

#### 10 · Illegal characters

- **Looks at:** the file names of evidence (on each standard) and of the output (on the report itself), and the narrative, against the character list kept in System Settings.
- **Finding:** "Illegal character · Board Minutes 12/09/2025.pdf · "/" is not allowed in a file name" or "Illegal character · paragraph 4 · a control character that breaks export".
- **Severity:** High for a file name the export or file system rejects; Medium for a narrative character on the institution's list that breaks export or rendering; Low for one SPOL substitutes silently (smart quotes, non-breaking spaces).
- **Fixed by:** Auto-format substitutes file-name characters; the writer fixes narrative ones.

#### 11 · Hidden text

- **Looks at:** the whole document, on every run, for text that would not print or would not be seen: white-on-white, zero-size, zero-width characters, text outside the page, hidden comments in the markup. Counted on the report itself.
- **Finding:** "Hidden text removed from 2.1 · see the standard", shown as a banner on Readiness and in the download.
- **Severity:** High. The text is removed from what is sent to print and to AI; the standard in All Accreditation is unchanged so the writer can see what was there.
- **Why it exists:** it protects the institution from accidental leftovers and from text planted to steer a reader or an AI.

### Accessibility · weight 15

#### 12 · Alt text

- **Looks at:** every image for a text alternative.
- **Finding:** "Alt text missing · Figure 6.1, page 119".
- **Severity:** Medium for a missing alternative; Low when the alternative is just the file name.
- **Fixed by:** the writer in the editor.

#### 13 · Headings

- **Looks at:** the document outline as it will print.
- **Finding:** "Heading level · "Results", page 62 · H4 directly under H2 · one level skipped".
- **Severity:** Medium for a skipped level or an empty heading; Low for duplicate numbering.
- **Fixed by:** Auto-format in Preview (the words are unchanged).

## Severity and points

Three levels, one meaning each, applied by the rule, never by a person, and each worth a fixed number of points in its category's score.

| Level | Meaning | Points |
| --- | --- | --- |
| **High** | The published document would be wrong, incomplete or unprintable for a reviewer, or a final could not be submitted | 3 |
| **Medium** | A reviewer would notice and ask, or evidence or review is incomplete | 1 |
| **Low** | Polish, fixed by a tool or safely ignored | 0 |

| Category | Check | High | Medium | Low | Not checked when |
| --- | --- | --- | --- | --- | --- |
| Attachments and links | 1 Missing attachments | Nothing attached; no expected count set; a cited file deleted | Fewer than expected | More than expected | Standard not started |
| 2 Link validation | SPOL document or evidence file gone or unreadable | External address failing twice; deleted objective or outcome | Redirect; certificate warning | No network; target needs sign-in |  |
| Completeness | 3 Placeholder text | Any placeholder | — | — | — |
| 4 Required cover fields | A required field missing | Signer named, date unsigned | — | — |  |
| Open items | 5 Open comments and unresolved edits | — | Open comment or pending edit | — | Comment service unavailable |
| Language | 6 Spelling, grammar, punctuation | — | Misspelt word in neither dictionary | Grammar, punctuation; a word only the institution's dictionary knows | Language service unavailable |
| 7 Style | — | A rule the institution marked required | Every other rule | No style guide configured |  |
| Print and export | 8 Table format | Wider than the printable page | No header row; row split across pages | Fits only below 85 % | Width cannot be measured |
| 9 Image sizes | Larger than the page | Over 1 MB; too low a resolution | No caption | Image file missing |  |
| 10 Illegal characters | File name the export rejects | Narrative character on the institution's list | Character SPOL substitutes | — |  |
| 11 Hidden text | Found and removed | — | — | — |  |
| Accessibility | 12 Alt text | — | No alternative | Alternative is the file name | — |
| 13 Headings | — | Skipped level; empty heading | Duplicate numbering | — |  |

**One finding per element.** A table with nine wide columns is one finding; a figure that is both oversized and uncaptioned is one finding at the higher severity; a word misspelt five times is five, because each is a separate change. Every count on the dashboard and in the download is a count of findings, never of cells, words or characters.

## The score

### Units

A category is scored over its **units**: each standard it applies to, plus the report itself where the category covers the cover or the output (see "Applies to" in The six categories).

### The calculation

For each category *c* with weight *wc*, scored over *nc* units:

1. For each unit *u*, add up the points of its findings in that category: *Pc,u*.
2. The unit keeps *qc,u* = 1 − min(*Pc,u*, 6) ÷ 6 of the category, a number between 0 and 1. Six points empties the category for that unit; nothing beyond six counts.
3. The category's quality is the average over its units: *Qc* = (Σu *qc,u*) ÷ *nc*.
4. The category's score is *wc* × *Qc*, rounded **down** to a whole number.
5. The readiness score is the sum of the six category scores.

Why it behaves:

a category can never give or take more than its weight; one unit can never move a category by more than its weight ÷ its number of units; one High finding moves it by at most half of that. Rounding each category down means a category shows full marks only when it has nothing scored left to fix, and the total always equals the sum of the six bars on screen. Adding standards neither dilutes nor inflates the score, because every category is an average.

### Rules at the edges

- **Not started.** A selected standard with no response scores 0 in Completeness and is left out of the other five categories, which have nothing to check.
- **Left out by a send back.** The standard is removed from every category until it returns; the score is about what would print now.
- **Not checked.** A unit a check could not run on is left out of that category's average, and the check shows "Partially checked". If a whole category could not run, its bar shows "—" and the total reads "{points} of {available}" (for example "80 of 90" for the demo report with the language service down) until it runs.
- **Nothing to score.** When no selected standard has a response (or every one is left out), the ring and the bars show "—" with "No responses to check yet"; the score is not shown as a partial number.
- **Approvals** are not in the score. They decide whether a final can be published, and they are shown beside the score so nobody mistakes 100 for "ready to submit".
- **The AI review score** is separate: these six categories never include an AI finding, and the AI review score never includes one of these findings. See Free and AI: one owner per question.

### Worked example: the demo report

Twelve standards selected; 3.3 not started, so eleven have a response; the report itself has no findings.

| Category | Units | Units that lost points | Q | Score |
| --- | --- | --- | --- | --- |
| Attachments and links (25) | 11 standards | 4.2: 2 High = 6 → 0 · 6.2: High + Medium = 4 → ⅓ | 9.33 ÷ 11 = 0.848 | 21 |
| Completeness (20) | 12 standards + report | 3.3: not started → 0 | 12 ÷ 13 = 0.923 | 18 |
| Open items (15) | 11 standards | 1.1, 3.1, 5.2: 1 Medium each → ⅚ | 10.5 ÷ 11 = 0.955 | 14 |
| Language (10) | 11 standards | 1.1: 1 Medium → ⅚ · 2.1: 2 Medium → ⅔ (its Low style finding counts 0) | 10.5 ÷ 11 = 0.955 | 9 |
| Print and export (15) | 11 standards + report | 3.1: 1 High → ½ · 4.2: 1 Medium → ⅚ · 6.1: High + Medium → ⅓ | 10.67 ÷ 12 = 0.889 | 13 |
| Accessibility (15) | 11 standards | 4.2: 1 Medium → ⅚ | 10.83 ÷ 11 = 0.985 | 14 |
| **Readiness score** | **89** |  |  |  |

Shown on the dashboard as "21 + 18 + 14 + 9 + 13 + 14 = 89", with "Final: not yet · 3.3, 4.2, 6.2 not approved" beside it. Fixing both missing documents on 4.2 lifts Attachments and links to 0.939 and its score to 23: the readiness score moves only within the share of Attachments and links, and only by 4.2's slice of it.

## Exact calculation for the build

This is the normative definition the build implements and tests against. It produces exactly the numbers in the worked example above. Scoring rules version: **readiness-score v1**.

### Inputs, all from the stored run

- The run's rule findings, each with its check, severity and unit (a standard code, or `REPORT` for the cover and output). AI findings are never inputs.
- For each selected standard: has a response, not started, or left out by an open send back.
- For each check and unit: whether the check ran on that unit.

### Constants

| Constant | Value |
| --- | --- |
| Points per finding | High 3 · Medium 1 · Low 0 |
| Cap per unit per category | 6 points |
| Weights | Attachments and links 25 · Completeness 20 · Open items 15 · Language 10 · Print and export 15 · Accessibility 15 |
| Check → category | 1, 2 → Attachments and links · 3, 4 → Completeness · 5 → Open items · 6, 7 → Language · 8, 9, 10, 11 → Print and export · 12, 13 → Accessibility |
| Categories that include the report unit | Completeness (checks 3, 4 on the cover) · Print and export (checks 10, 11 on the output and the whole document) |

### Algorithm

```
for each category c with weight w:
    units = []
    for each selected standard s:
        if s is left out:                skip
        if s is not started:
            if c is Completeness:        units.append(6)        # nothing to print = full penalty
            skip
        if no check of c ran on s:       skip                   # "Partially checked"
        P = sum(points of s's findings from the checks of c that ran)
        units.append(min(P, 6))
    if c includes the report unit and at least one check of c ran on REPORT:
        P = sum(points of REPORT's findings from the checks of c)
        units.append(min(P, 6))
    n = len(units)
    if n == 0:                           category[c] = NOT_AVAILABLE; continue
    kept = sum(6 - p for p in units)     # integer
    category[c] = floor(w * kept / (6 * n))   # integer division, never floating point

if no selected standard has a response and is not left out:
    show "—", "No responses to check yet"
else:
    score     = sum(category[c] for available c)
    available = sum(w for available c)
    show score if available == 100 else "{score} of {available}"
```

- **Integers only.** Compute `(w × kept) div (6 × n)` in integer arithmetic. Floating point turns an exact 24 into 23.999… and floors it to 23.
- **Bar width** is `kept ÷ (6 × n)` as a percentage. Colour: below 70 % red, below 90 % amber, otherwise the neutral bar.
- **Stored, not recomputed.** The six category values, their `kept` and `n`, the total, the available maximum and the rules version are stored with the run. Displays and the download read the stored values. A score is compared with another only when both carry the same rules version.
- **Formula line.** The dashboard prints the six stored values in the fixed order Attachments and links, Completeness, Open items, Language, Print and export, Accessibility, joined by " + ", then " = " and the total. A category that is not available prints "—" and is left out of the sum.
- **Download.** The Summary sheet lists, per category, the weight, `n`, `kept`, the score and the rules version, so any score can be rechecked by hand.

### Test cases

Built on the demo report unless stated. Each line gives the six category scores in the fixed order, then what the ring shows.

| # | Case | Attachments and links | Completeness | Open items | Language | Print and export | Accessibility | Ring |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Demo report | 21 | 18 | 14 | 9 | 13 | 14 | **89** |
| 2 | Clean report, every standard started, no findings | 25 | 20 | 15 | 10 | 15 | 15 | **100** |
| 3 | Demo, both missing documents on 4.2 attached | 23 | 18 | 14 | 9 | 13 | 14 | **91** |
| 4 | Demo, 4.2 and 6.2 left out by send back | 25 | 18 | 14 | 9 | 13 | 15 | **94** (Final still blocked) |
| 5 | Demo, language service unavailable | 21 | 18 | 14 | — | 13 | 14 | **80 of 90** |
| 6 | Demo, a placeholder on the cover (High on REPORT) | 21 | 17 | 14 | 9 | 13 | 14 | **88** |
| 7 | Demo, hidden text found (High on REPORT) | 21 | 18 | 14 | 9 | 12 | 14 | **88** |
| 8 | Demo, plus ten High findings in Attachments and links on 3.2 | 18 | 18 | 14 | 9 | 13 | 14 | **86** (3.2 capped at 6 points) |
| 9 | One standard selected, one Medium spelling finding | 25 | 20 | 15 | 8 | 15 | 15 | **98** |
| 10 | Every selected standard not started | — | — | — | — | — | — | **—** "No responses to check yet" |

Case 4 is intended: the score describes what would print now, and standards left out do not print; Final stays blocked until they return approved. Case 8 shows the cap: ten High findings cost 3.2 its full slice of Attachments and links (25 ÷ 11 ≈ 2.3 points) and no more.

## Where findings go

- **Under the standard's row** on Readiness, one line each: "{Severity} · {Check} · {where} — {detail}", with "Open {code} in All Accreditation". Findings on the report itself appear as a banner above the standards.
- **In the Review panel,** where the passages that carry a finding are marked in amber in the response as it will print.
- **In a send back,** as the first part of the compiled comment the holder receives, each finding ticked by default and untickable. Send all back does this for every standard with findings at once.
- **In Preview,** for the Print and export findings and Headings: Auto-format fixes tables, images, file-name characters and heading levels in one pass and shows every change before and after.
- **In the Excel download** of the run on screen (including an out-of-date one), six sheets:  Plain values, filters on every sheet, no formulas. A CSV of the Findings sheet alone is also offered.
    - **Summary:** the readiness score, the six category scores with their weights, the verdicts, approvals, the run date and who ran it.
    - **Findings:** one row per finding with category, check, standard, severity, points, location, description, suggested action, left out, status and holder.
    - **Standards:** one row per standard with its points in each category, its chain state and holder.
    - **Report:** the findings on the report itself.
    - **Checks:** one row per check with its category and status.
    - **AI findings:** present only when an AI run exists.

## Check status and messages

| Status | Meaning | Shown as |
| --- | --- | --- |
| Passed | The check ran on every unit and found nothing | Green "Passed"; a clean standard reads "All 13 checks passed · approved {date}" |
| Issues found | The check ran and found findings | The count of findings, never of cells or words |
| Partially checked | The check ran but some units could not be checked | "{n} not checked" with the reason, for example "1 standard not started" |
| Not checked | The check did not run | "Not checked" with the reason (service unavailable, no style guide, cancelled) |

- Before any run: the ring and the six bars show "—", the verdicts read "Not checked yet", the lists are hidden, Next is still available.
- While running: "Checking {n} of {m} sections", Cancel. Cancelled: "Checks cancelled · Run checks". Not finished in ten minutes: "Checks couldn't finish · Run again", previous result kept.
- After a change: "Out of date · Run again" on the dashboard and on Step 4.
- The last-run line: "Last run {date, time} · {k} of 13 checks completed · language checks by WProofreader".

## Acceptance

- **Full run.** Given the demo data. When Run checks again. Then all thirteen checks report a status, the six bars read Attachments and links 21 / 25, Completeness 18 / 20, Open items 14 / 15, Language 9 / 10, Print and export 13 / 15 and Accessibility 14 / 15, the ring reads 89 with "21 + 18 + 14 + 9 + 13 + 14 = 89", and 17 findings are listed under their standards.
- **Proportion.** Given any report. When every finding in one category is resolved. Then the readiness score rises by exactly that category's lost points and no other bar moves. Given a standard with ten High findings in one category. Then that category loses no more than that standard's slice of it.
- **One per element.** Given a table with nine wide columns. Then exactly one Table format finding, High, naming the table and page.
- **Expected count not set.** Given 6.2 with no expected evidence count and no documents. Then a High "Expected evidence count not set" and a Medium "No documents attached", and Attachments and links keeps ⅓ of 6.2's slice.
- **Placeholder.** Given "[Name of Institution]" on the cover. Then a High Placeholder text finding on the report, listed under "Before you publish", and Completeness loses half of the report's slice.
- **Not started.** Given 3.3 with no response. Then no finding is raised, 3.3 scores 0 in Completeness, and it does not appear in the other five categories.
- **Language engine.** Given "occurence" in 2.1. Then a Medium Spelling finding with the suggestion, no AI label and no credit line; the same word is marked in the editor as you type.
- **Institution dictionary.** Given "Westmoor" added to the institution's dictionary. Then it is never reported; a word known only to that dictionary is Low, not Medium.
- **Hidden text.** Given white-on-white text in 2.1. Then the banner "Hidden text removed from 2.1 · see the standard", the download lists it on the Report sheet, the standard in All Accreditation is unchanged, and Print and export drops from 13 to 12 (0.63 of a point before rounding down), so the score reads 88.
- **Out of date.** Given a run and a writer's change to 1.1. Then "Out of date · Run again"; the old findings and scores stay until the next run.
- **Cancelled.** When Cancel during a run. Then "Checks cancelled · Run checks", the previous result stays, nothing is recorded as a completed run.
- **Download.** When Download report (Excel). Then a workbook named with the institution, template, draft and run date, with the six sheets above, 17 rows on Findings and the six category scores on Summary, no formulas.

## Mapping to the v6.0.0.8 build

| Category | This specification | v6 build | Change |
| --- | --- | --- | --- |
| Attachments and links | 1 Missing attachments | Missing Attachments ("87 standards") | Keep; count findings, not standards, and report "expected count not set" as its own High finding. |
| 2 Link validation | Link Validation | Keep; add severity by cause ("Document file not found on server" is High). |  |
| Completeness | 3 Placeholder text | — | New; the v6 cover shows exactly the placeholders it catches. |
| 4 Required cover fields | — | New; v6 collects these fields on "Structure & Branding". |  |
| Open items | 5 Open comments and unresolved edits | Narrative Comments, "Not Checked" | It must run on every readiness run. |
| Language | 6 Spelling, grammar and punctuation | Spell Check, under "AI can fix these" | Move into Language; it is neither AI nor fixed by Publish. |
| 7 Style | — | New. |  |
| Print and export | 8 Table format | Table Format, "181 issues" | Keep; count tables, not cells. |
| 9 Image sizes | Image Sizes | Keep. |  |
| 10 Illegal characters | Illegal Characters ("0 narrative · 4 files") | Keep, with severity split by file name versus narrative. |  |
| 11 Hidden text | — | New. |  |
| Accessibility | 12 Alt text | — | New. |
| 13 Headings | — | New. |  |
| — | — | Issue Summary | A view, not a check; replaced by the six category bars. |
| — | — | "AI can fix these" / "These need your review" | Replaced by the six categories; nothing on this step carries an AI label unless it costs credits. |

Part of the Publish specification set: https://rajatcord.github.io/spol-publish-prototype/ · The AI checks are described in "The AI checks"; the user-facing explanation is "How AI readiness works".
