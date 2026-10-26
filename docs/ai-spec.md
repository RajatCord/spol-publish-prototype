---
title: "SPOL Publish · AI behaviour spec"
source: ai-spec.html
format: markdown export of the HTML document; tables are pipe tables; the HTML remains the reference rendering
---

Specification · AI behaviour in Publish · v6 · 22 Oct 2026

# AI readiness and Auto-format: what they do

The two places in Publish where a model is used, described as product behaviour: what each feature reads, what it returns, what SPOL does with the result, what it may cost, what it must never do, and the quality bar it has to meet before and after it ships. The user-facing explanation is the dossier "How AI readiness works"; the screens are in the functional handoff. Prompts, schemas and the technical pipeline are the build team's design, kept in the engineering notes.

## In short

- **Two features only.** AI readiness reads each selected standard the way a visiting reviewer would and returns findings; a second, smaller pass compares the numbers, dates and named roles it extracted across standards. Auto-format lays the document out to the template and returns layout changes, never text. Nothing else in Publish uses a model.
- **Grounded or nothing.** Every finding points at a quoted passage or a named reviewer question. SPOL checks that against the report before anyone sees it; a finding that cannot be verified is dropped.
- **Suggest, never act.** Model output changes nothing. A person accepts or ignores each finding; Auto-format applies only changes from a fixed list, each of which can be undone.
- **Quoted up front, never more.** 2 credits per standard not already checked + 5 for the cross-standard pass (12 standards → 29); Auto-format 4. The quote is the most the institution can pay.
- **Computed once, shared.** A result is stored and shown identically to everyone; a standard whose text has not changed costs nothing to check again.

## Principles that bind both features

- **One standard at a time.** Each standard is read on its own, with its own wording, reviewer questions, response and evidence index. No call ever receives the whole report. The cross-standard pass sees only the facts extracted from each standard, never the text.
- **Documents are data.** The report text is treated as content to be reviewed, never as instructions. Hidden text is removed before anything is sent and reported as a finding. Text that tries to steer the review is itself reported.
- **Structured answers only.** The model answers in a fixed form (kinds, severities, anchors, short fixes). No free prose reaches the screen; a malformed answer is a failed call, not a thinner answer.
- **The score is arithmetic you can check.** SPOL computes the AI review score from the findings with a published formula. The model is never asked for a number.
- **Refuse rather than degrade.** A standard whose result cannot be verified, that was too long, or that the provider could not process is reported "not checked" with its reason and refunded. The rest of the run proceeds.
- **Zero data retention only.** Models run under the provider's zero-retention, no-training terms, pinned to a version; a version changes only after the quality bar passes again.
- **Recorded.** Every run, decision, charge and refund is in the audit trail with who, when and which version.
- **Never the free checks' territory.** AI readiness does not report spelling, grammar, punctuation, style, attachment counts, broken links, layout, alt text, headings, placeholders, hidden text or open comments; the free readiness checks own those. The AI is told so, and SPOL drops any such finding before it is shown. The AI review score is built only from AI findings and the readiness score only from the free checks; the two are never combined.

## AI readiness

### What it reads, per standard

#### Sent

- The standard's wording from the accreditor and SPOL's one-paragraph guidance.
- SPOL's reviewer questions for that standard (three to six, written and versioned by SPOL's accreditation team).
- The response, split into numbered paragraphs, with hidden text removed and names, emails and IDs replaced by tokens.
- An index of the cited documents: title, type, page count, the pages cited and a 40-word extract of each cited page. Not the files.
- The judgment entered (for example "Compliance") and the open comments on that standard.

#### Never sent

- The attachment files themselves: PDFs, spreadsheets, scans.
- Student or personnel records, or anything the institution's data steward has not allow-listed.
- Names, emails and IDs where detected; the key that maps tokens back to names never leaves SPOL.
- The whole report at once, other institutions' reports, earlier cycles, or anything the AI itself wrote earlier.
- The cover, cycle dates and submission date.

A pre-send scan looks for student IDs, national-ID patterns, emails, phone numbers and tables small enough to identify a person. A hit leaves only that standard out ("not checked: personal data"); the rest of the run proceeds and that standard is not charged.

### What it returns

| Finding kind | What it means | What it points at |
| --- | --- | --- |
| Unsupported claim | A claim the standard turns on that cites nothing in the evidence index | The sentence, quoted |
| Weak argument | The response asserts that the standard is met instead of showing how | The passage, quoted |
| Missing element | A reviewer question the response does not address | The reviewer question |
| Evidence mismatch | A cited extract that contradicts the sentence citing it | The sentence and the extract |
| Clarity | A passage a reviewer is likely to misread, with why | The passage, quoted |
| Contradiction (cross-standard pass) | Two standards give different values for the same measure and period | Both passages |
| Manipulation | Text inside the document that tries to instruct the reader or an AI | The passage, not quoted |

Every finding carries a **severity** (High: a committee would likely cite it · Medium: it would ask · Low: wording), a **confidence** (High: the text itself shows the problem · Medium: likely, another reading exists · Low: worth a glance), **why it matters** in one or two sentences, and a **suggested fix** of at most 40 words that says what to change and never supplies the paragraph. The five areas on the panel (argument strength, evidence sufficiency, consistency, clarity, reviewer readiness) are built from these kinds; "Reviewer view: {n} likely follow-ups" counts the High findings.

### How SPOL treats a result

- **Verification.** Every quote is matched against the text that was sent; every reviewer question and document reference must exist. Findings that fail are dropped. If more than three in ten findings on a standard fail, the standard is "not checked" and refunded rather than shown with gaps.
- **Score.** Per checked standard: 100 − 8 per High − 3 per Medium − 1 per Low, never below 0; the AI review score is the average over checked standards. Contradictions are listed separately and do not enter it. A standard that could not be checked is left out and never counts against the institution. The AI review score sits beside the readiness score and is never added to it; neither score decides publishing, which needs approvals and the free blocking conditions.
- **States.** A finding is open, sent back (accepted and included in a send back), closed (ignored with a reason, or cleared), outdated (its passage changed since the run; its actions stay available) or resolved by the latest run (not reproduced after the text changed; shown greyed).
- **Decisions.** Two only: **Accept and send back**, which carries the finding to the person who holds the standard as a comment, marked as a suggestion; and **Ignore** with one of four reasons: not an issue, already covered, fix after this draft, accepted risk. "Fix after this draft" reopens on the next draft. A closed finding can be reopened. Decisions attach to the finding, so when a later run reproduces it the decision carries, whatever draft it was made in.
- **Manipulation.** A manipulation finding is shown with a fixed message, never with the planted text; it cannot be accepted or ignored, only cleared by a coordinator with a note; it blocks a final (not a draft) until cleared; the standard stays in the score and its other findings are still reported.
- **Stored and shared.** Results are kept against the exact text and settings they were produced for. Everyone sees the same findings; "Run again" charges only standards whose text or evidence changed; a run on text that changed meanwhile is marked out of date when it finishes.

### A run, start to finish

- **Quote.** The unlock card shows "{n} credits for {m} standards · {left} left this year", naming standards that will be skipped (too long, personal data). Writers see no cost line and cannot unlock.
- **Approval.** Above 50 credits a second coordinator approves; the credits are reserved meanwhile; the request expires after 7 days; nothing is blocked while waiting, and a draft can be published.
- **Progress.** "Reading {n} standards… started by {name}"; a second person who unlocks the same draft joins the run. People can keep working; only publishing waits.
- **Cancel.** Standards already finished are kept and charged; the rest, including the cross-standard pass, are refunded: "Cancelled · 4 of 12 checked".
- **Not finished.** After the planned time plus 15 minutes: "AI readiness didn't finish · credits for unchecked standards refunded · Try again". If nothing could be checked: "AI readiness couldn't run · {n} credits refunded" and the card locks again.
- **Not checked, per standard,** with the reason shown on its row: too long · personal data · couldn't be grounded · retry budget · provider unavailable · provider refused · cancelled · timed out. Each is refunded except the two found at quote time, which were never charged.
- **Large reports.** More than 24 selected standards are read in groups; the cross-standard pass runs within each group and once across groups on counts, money and dates.

## Auto-format

- **What it does.** Lays every page out to the accreditor's template in one pass: fits tables to the page (scaled, or turned landscape when scaling would drop below 85 %), scales images to the page width and size limit, corrects skipped heading levels, evens out paragraph spacing to the template's value, puts evidence citations in the template's one style and links them to the evidence index, and rebuilds the contents, bookmarks and page numbers.
- **Where AI decides.** Only the how: whether a table is scaled or turned, which heading level fits, which citation form the template wants. Every decision is from a fixed list of allowed changes; anything outside the list is refused. The alternative the model did not choose is shown next to each change.
- **What never changes.** Narrative text down to the punctuation, compliance judgments, which evidence is cited, the cover and signatures, and any number, name or table value.
- **What the person gets.** The dialog first lists what will be done in this report with counts and pages, kind by kind, each of which can be left out. Afterwards: a change list, a before-and-after view of every change with the page edge marked where content was cut off, Undo per change or Undo all, changed pages marked in the margin, confirmations cleared and the readiness check marked out of date, and an audit entry naming each change.
- **Cost.** 4 credits, charged only when the run completes. Nothing to change or a failed run: nothing charged, and the message says so. Undo keeps the charge.

## Cost, charging and refunds

| Situation | Credits | What the coordinator sees |
| --- | --- | --- |
| AI readiness | 2 per standard not already checked + 5 for the cross-standard pass (12 standards → 29; 1 standard → 7; 70 standards → 145) | "Uses 29 credits for 12 standards · 1,866 left this year", then "29 credits used · 1,837 left this year · recorded in the audit trail" |
| Run again | Only standards whose text or evidence changed; stored ones cost 0 | "21 credits for 8 standards · 4 already checked" |
| Standard not checked | Refunded (2 each); the 5 for the cross-standard pass refunded whenever that pass does not run | "5.2 not checked · personal data · 2 credits refunded" |
| Cancel while running | Finished standards kept and charged; the rest refunded | "Cancelled · 4 of 12 checked" |
| Above 50 credits | A second coordinator approves before anything is charged; reserved meanwhile, released on decline or after 7 days | "This run needs 61 credits. A second coordinator must approve." |
| Not enough credits | Nothing starts, nothing charged | "Not enough credits · 29 needed, 20 left this year · Ask your administrator" |
| Provider unavailable before any call | Nothing charged | "AI readiness isn't available right now · nothing was charged · Try again" |
| Auto-format | 4 flat; nothing if there is nothing to format or the run fails; Undo keeps the charge | "Uses 4 credits · 1,837 left this year" |

The quote is a ceiling. SPOL gives every run an internal spending limit above the charge and carries any difference; a standard that cannot be finished within that limit is reported "not checked: retry budget" and refunded. Credits belong to the institution and are pooled; writers never see balances. Everything else in Publish is free: the readiness checks, send back, comments and publishing in any format.

## Privacy, data and safety

- **At the provider:** zero data retention, no training on the institution's text, the region named in the order form. Only models available under those terms are used for institutional content. The three features use Claude models from Anthropic, each pinned to a version; a version changes only after the quality bar below passes again, and the version in use is recorded with every run.
- **Names and identifiers** are replaced by tokens before sending, across narratives, comments, evidence titles and extracts, and mapped back only inside SPOL. Detection is good, not perfect: programme names and enrolment figures can still identify an institution, which is why the provider agreement, not the tokens, is the privacy guarantee.
- **What SPOL keeps:** the findings, the decisions, the audit entries and usage counts. Prompts and raw responses are kept for 24 hours for support, then deleted; the order form states this.
- **Manipulation resistance.** Report text is content, never instructions. Planted instructions are reported as a High finding with a fixed message and the standard's other findings are still reported; nothing the model returns is executed, rendered as formatting or fed to another AI call; accepted findings become comments marked as AI suggestions and are left out of future inputs.
- **What the model never gets to do:** change report text, judgments, evidence or the cover; approve, send back, sign, publish or submit; set a score; see attachments, personal data or other institutions' reports; run without a person starting it and a quote being shown.

## The quality bar

Every statement in the dossier is backed by a test SPOL runs before a model, prompt or rubric version ships and every night afterwards. A failing nightly pauses the feature and tells the named contacts.

| Commitment | Bar |
| --- | --- |
| Every finding points at the text | 100 % of anchors exist and quotes are verbatim, on a fixed set of synthetic standards |
| Unsupported claims are found, not invented | At least 85 % of flagged claims are genuinely unsupported; at least 70 % of seeded unsupported claims are found; at most one false alarm per clean standard |
| Evidence mismatches are real | At most 5 % false mismatches when an extract is merely silent; at least 80 % of genuine contradictions between a sentence and its extract found |
| Contradictions across standards | At least 90 % of seeded contradictions found; at most 2 % false alarms |
| Manipulation | 0 planted instructions followed; at least 90 % flagged; ordinary reader-addressed prose ("the committee will note…") not flagged more than once in 30 standards |
| Every finding kind | At least 80 % precision for weak argument, missing element and clarity |
| Names stay inside SPOL | At most 2 % of quotes lost when names are mapped back; 0 unknown tokens ever shown |
| Never more than the quote | Charging simulated for 1 to 70 standards: no refusal of a report that fits, spending inside the limit on every retry pattern |
| Stable | Five fresh runs on the same text agree at least nine times in ten on what they find and where |
| Fair | The same facts and evidence written plainly, formally or by a non-native writer, or with institution-size cues varied, get the same number and severity of findings within the run-to-run noise |
| Auto-format | At least 95 % agreement with a human layout editor on tables, headings and citations; no change outside the allowed list; no citation to a document that is not in the index |

**Rubric governance.** The reviewer questions are written and versioned by SPOL's accreditation team; each change needs a second reviewer and a passing quality run before it is used. Every accept and ignore decision, with its reason, feeds a review queue per accreditor: when a question's findings are ignored as "not an issue" more than one time in five, across at least 50 decisions from at least 5 institutions, the question is flagged for the accreditation team to decide. Nothing changes automatically, and one institution's clicks never change what another sees.

## What is recorded

Every run: who started it, which draft, which rubric and model versions, the standards checked and not checked with reasons, the credits quoted, charged and refunded. Every decision: accept, ignore with its reason, reopen, clear with its note. Every Auto-format run and undo with each change. From these entries SPOL produces the per-submission **AI-involvement report** an institution can hand to an accreditor: what AI suggested, what a person accepted, and what was changed as a result.

## Limits, stated plainly

- It is not the visiting committee. It predicts questions a reviewer is likely to ask; it does not know the reviewers, the institution's history or the accreditor's unwritten expectations.
- It can miss things and it can be wrong. The quality bar bounds how often, not to zero, which is why every finding has Ignore and why publishing never depends on the AI review score.
- It reads one standard at a time, and extracts rather than files. A cited document is judged by its title and 40 words from each cited page; it cannot tell that a 60-page policy is weak.
- It never writes. A suggested fix says what to change; it does not supply the paragraph.
- It is not identical every time; results are stored so that a team sees one set.

Technical detail for the build team (prompts, answer formats, verification rules, keys and versions, cost model): the engineering AI spec, kept beside this page.
