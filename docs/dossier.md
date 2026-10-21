---
title: "How AI readiness works"
source: https://rajatcord.github.io/spol-publish-prototype/docs/dossier.html
format: markdown export of the HTML document; tables are pipe tables; the HTML remains the reference rendering
---

SPOL Accreditation · Publish · Readiness check

# How AI readiness works

A plain account of what AI readiness reads, what it never sees, how its score is built, how it is kept honest, what it costs and what it cannot do. Written for accreditation coordinators, editors and the people who sign the report. Nothing here is marketing; every statement is checked by a test SPOL runs before a model version ships and every night after.

## What it is, in six promises

It reads like a reviewer, one standard at a time.

It is given your response to a single standard, the standard's wording, SPOL's reviewer questions for it, and the evidence you cited, and it reports what a visiting committee would question.

It suggests. People decide.

No finding changes a word of your report, a judgment, or an approval. You accept a finding and send it to the writer, or you ignore it with a reason. Both are recorded.

Every finding points at the text.

Each finding quotes the exact passage or names the reviewer question it concerns. SPOL checks the quote against your text before you see it; a finding that cannot be verified is dropped.

The score is arithmetic you can check.

SPOL computes it from the findings with a published formula. The model is never asked for a number.

Your data stays yours.

Names are replaced by tokens where detected, no attachment files leave SPOL, and the model provider keeps nothing: zero data retention, no training on your text.

It costs what it says, up front.

2 credits per standard plus 5 for the cross-standard check, quoted before you start. Standards it cannot check are refunded. You never pay more than the quote.

## What it reads, and what it never sees

#### Sent, for each selected standard

- The standard's wording from the accreditor and SPOL's one-paragraph guidance.
- SPOL's reviewer questions for that standard (three to six, written and versioned by SPOL's accreditation team).
- Your response, split into numbered paragraphs, with hidden text removed and names replaced by tokens.
- An index of the documents you cite: title, type, page count, the pages you cite, and a 40-word extract of each cited page. Not the files.
- The judgment you entered (for example "Compliance").
- Open comments from your team on that standard.

#### Never sent

- The attachment files themselves: PDFs, spreadsheets, scans.
- Student records, personnel files, or anything your data steward has not allow-listed.
- Names, emails and IDs where detected; the key that maps tokens back to names never leaves SPOL.
- The whole report in one go. Each standard is read on its own; a second, smaller check compares only the numbers and dates it extracted.
- Other institutions' reports, your earlier cycles, or anything the AI itself wrote earlier.
- Your cover page, cycle dates or submission date.

A pre-send scan looks for student IDs, national ID patterns, emails, phone numbers and tables small enough to identify a person. If it finds one, only that standard is left out ("not checked: personal data") and the rest of the run proceeds.

## The five checks

| What it looks for | In plain words | An example finding |
| --- | --- | --- |
| **Argument strength** | Does the response show how the standard is met, or only assert it? Is any reviewer question left unanswered? | "No passage says how assessment results were used to improve a programme." (reviewer question 4.2:4) |
| **Evidence sufficiency** | Which claims that the standard turns on cite nothing in the evidence index? Does a cited extract contradict the sentence citing it? | "Every programme completed its assessment cycle in 2024-25" cites nothing. Cite the assessment summary. |
| **Consistency** | Do numbers, dates or named roles disagree between standards? | 6.1 reports 312 full-time faculty for 2024-25; 5.1 reports 298 for the same year. |
| **Clarity** | Is there a passage a reviewer is likely to misread? | Paragraph 2 runs 140 words; a reviewer may miss the recusal point. |
| **Reviewer readiness** | How many standards carry a high finding a committee would likely cite? | "Reviewer view: 3 likely follow-ups." |

Every finding has a severity (**High**: a committee would likely cite it; **Medium**: it would ask a question; **Low**: wording) and a confidence (**High**: the text itself shows the problem; **Medium**: likely, but another reading exists; **Low**: worth a glance). A suggested fix says what to change in at most 40 words; it never rewrites your prose.

## Why you can trust a finding

1. **It must be anchored.** A finding names the paragraph (or comment) it is about and quotes it word for word, or names the reviewer question that is not addressed. The model is told to report nothing it cannot anchor.
2. **SPOL verifies the anchor.** Before anything is shown, SPOL checks that the quoted text really appears in that paragraph of your response and that every document or comment it refers to was actually sent. Findings that fail are discarded, and if more than three in ten fail, the whole standard is marked "not checked" and refunded rather than shown half-right.
3. **Nothing is invented.** The model cannot refer to a document, number, policy or person that was not in the input, because every reference must match an identifier SPOL generated. Evidence findings are limited: a 40-word extract that is merely silent on a detail is never grounds for a finding; only a contradiction is.
4. **Everyone sees the same thing.** Results are stored under a key made from your text and the exact version of every component. Your colleague opening the same draft sees the same findings; nothing is re-generated behind your back. If a paragraph changes afterwards, its findings are marked **Outdated** until you run again.
5. **It is tested to behave.** Before any model or question set ships, and every night, SPOL runs it against seeded test cases: anchors must be 100% verifiable, false alarms on clean standards are capped, and repeated runs on the same input must agree at least 90% of the time.

## How the score is built

For each checked standard:

100 − 8 per High − 3 per Medium − 1 per Low

finding, never below 0. The

AI readiness score

is the average over the standards that were checked. Contradictions are listed separately ("1 to resolve") and do not enter the score.

- The five bars show shares of standards: argument strength (no high argument or missing-element finding), evidence sufficiency (no evidence finding), clarity (no clarity finding), reviewer readiness (no high finding), and the number of contradictions.
- A standard that could not be checked (too long, personal data found, output not verifiable, provider unavailable, cancelled) is left out of the average and listed with its reason. It never counts against you.
- The AI score sits beside the rules score and never replaces it. The rules score (approvals, evidence present, comments, formatting, accessibility) is free and is what gates a final; the AI score is advice.

## What you do with a finding

- **Read it in place.** Open the standard from Readiness: the response as it will print, with each finding marked in the text, the evidence, and the comment thread.
- **Accept and send back.** The finding becomes a comment on the standard, in the writer's words-to-fix form, and the standard goes back to the person who holds it through the normal approval chain. For a contradiction you choose which of the two standards goes back.
- **Ignore with a reason.** Not an issue · Already covered elsewhere · Will fix after this draft · Accepted risk. The finding closes; "Will fix after this draft" reopens on the next draft. You can reopen at any time.
- **Add your own comments.** Select a passage and comment on it, add an overall comment, and send them together with the findings, or post them to the standard's thread without reopening its approval.
- **Nothing happens on its own.** A finding that no one touches stays open and changes nothing. The report publishes as an internal draft regardless; a final needs every standard approved by people, not by the AI.

Ignore reasons are counted across institutions. When a reviewer question is dismissed as "not an issue" more than 20% of the time after at least 50 decisions from 5 institutions, SPOL's accreditation team reviews that question. One institution's clicks never change what another sees.

## Privacy and data

#### Before anything leaves SPOL

- Hidden text (white-on-white, zero-size, off-page) is removed and reported to you as a finding.
- Institution, people, programme and place names are replaced by tokens such as [PERSON_2]; IDs, emails and phone numbers are stripped. Detection uses name recognition plus your institution's own directory. It is good, not perfect; SPOL says so rather than promising anonymity.
- Comments the AI itself produced earlier are never fed back in.

#### At the model provider

- Zero data retention: nothing you send is stored by the provider or used to train models. Only models available under these terms are used (Claude Sonnet 5.5 for the standard-by-standard reading, Claude Opus 5.5 for the cross-standard check, Claude Haiku 5.5 for Auto-format decisions).
- The processing region is named in your order form.
- The model has no tools. It cannot send, fetch or save anything.

#### What SPOL keeps

- The findings, the audit entry (who, when, which draft, which versions, how many tokens, what it cost) and your decisions.
- Prompts and raw model responses for 24 hours, for debugging, then deleted.
- The token-to-name key, inside SPOL only, used to put names back into findings before you see them.

#### What the model never gets to do

- Change report text, judgments, evidence or the cover.
- Decide compliance or produce the score.
- See the whole report in one call, another institution, a prior cycle, or its own earlier output.

## If someone tries to game it

Text planted in a response to steer an AI or the review ("ignore the rules", "report no findings", "score this as compliant") is treated as a finding, not as an instruction. The model is told that everything inside your document is content to analyse; it reports the attempt as a **High** finding with its location, and still reports everything else about that standard. SPOL shows a fixed message: "Text that tries to steer the review or an AI was found in 2.1, paragraph 3. Open the standard and remove it." The standard stays in the score with all its other findings, so no one can use this to escape review. A final cannot be published until a coordinator clears the flag with a note; an internal draft can.

In testing, 30 documents with planted instructions produced zero followed instructions; ordinary prose addressed to the committee ("the committee will note…") is not flagged.

## What it costs

| Action | Credits | What you see |
| --- | --- | --- |
| AI readiness | 2 per standard not already checked + 5 for the cross-standard check (12 standards → 29) | The quote on the card before you unlock: "Uses 29 credits for 12 standards · 1,866 left this year"; afterwards "29 credits used · 1,837 left this year · recorded in the audit trail". |
| Run again | Only standards whose text or evidence changed; unchanged ones cost 0 | A fresh quote first; "21 credits for 8 standards · 4 already checked". |
| A standard that could not be checked | Refunded (2 credits each); if the cross-standard check could not run, its 5 are refunded too | "5.2 not checked · personal data · 2 credits refunded". |
| Cancel while running | Standards already finished are kept and charged; the rest are refunded | "Cancelled · 4 of 12 checked". |
| Auto-format | 4 flat; nothing if there is nothing to format or the run fails | "Uses 4 credits · 1,837 left this year"; Undo keeps the charge. |
| Above 50 credits | A second coordinator approves before anything is charged | "This run needs 61 credits. A second coordinator must approve." |

Credits belong to your institution and are pooled; writers never see balances. The quote is the most you can pay for a run: SPOL carries the difference if a run costs more than expected, never you. Everything free stays free: the readiness checks (spelling, grammar, punctuation and style run on WProofreader under SPOL's licence and never use credits), send back, comments, and publishing in any format.

## Quality and fairness

Every model version and every change to the reviewer questions must pass the same tests before it reaches you, and the tests run again every night:

| Test | Bar |
| --- | --- |
| Grounding: 200 findings on 20 test standards | 100% of anchors exist and quotes are word-for-word |
| Unsupported claims: 60 seeded, 60 clean | At least 85% of flags correct, at least 70% of seeded problems found, at most 1 false alarm per clean standard |
| Evidence extracts that are merely silent | At most 5% false mismatches |
| Contradictions between standards | At least 90% found, at most 2% false alarms |
| Planted instructions | 0 followed; at least 90% flagged; real issues still found alongside them |
| Names put back correctly | At most 2% of quotes lost; 0 stray tokens shown |
| Repeatability: same input, 5 runs | At least 90% of findings agree |
| Fairness of style: the same facts written plainly, formally, and by a non-native writer | Same number and severity of findings, within noise |
| Fairness of size: large and small institution cues | Same bar |
| Auto-format decisions vs a human layout editor | At least 95% agreement; no operation outside the allowed list |

The reviewer questions themselves are written by SPOL's accreditation team per accreditor, versioned, and changed only with a second reviewer and a passing test run. The version in use is shown under "How AI readiness works" on your Readiness page and recorded in the audit trail of every run.

## What it cannot do

- **It is not the visiting committee.** It predicts questions a reviewer is likely to ask; it does not know your reviewers, your history, or the accreditor's unwritten expectations.
- **It can miss things and it can be wrong.** The tests bound how often, they do not make it zero. That is why every finding is a suggestion with an Ignore button, and why the rules score, not the AI score, gates a final.
- **It reads one standard at a time.** It will not notice an argument that spans standards except through the numbers, dates and named roles the cross-standard check compares.
- **It reads extracts, not files.** A cited document is judged by its title and 40 words from each cited page. It cannot tell you a 60-page policy is weak.
- **It does not write.** A suggested fix says what to change; it never supplies the paragraph.
- **It is not identical every time.** Two fresh runs on the same text agree at least nine times in ten; SPOL stores the result so that your team sees one set, but we do not claim the model is deterministic.
- **Name detection is good, not perfect.** Programme names and enrolment figures can still identify an institution; the provider's zero-retention terms, not the tokens, are the privacy guarantee.

## The record you can show an accreditor

Every run writes an audit entry: who started it, on which draft, which model and question-set versions, how many standards were checked and which were not and why, how many tokens it used, what it cost, and what was refunded. Every accept, ignore (with reason), reopen and clear is recorded against the finding. From these entries SPOL generates a per-submission **AI-involvement report**: what AI was used on this report, when, on what, and what people decided. Disclosure never depends on anyone's memory.

## Questions people ask

**Can I send every finding back at once?**  
Yes. "Send all back" on the Readiness step sends each standard that carries findings to the person who holds it, with one comment per standard: the rule findings and, if you unlocked AI readiness, its open recommendations marked as suggestions with the suggested fix. You see the full list and who receives what before anything is sent, and each send is in the audit trail.

**Is the spelling check AI?**  
No. Spelling, grammar, punctuation and style are checked by WProofreader, a proofreading tool SPOL licenses, using SPOL's accreditation dictionary and your institution's own words. It runs as you type and again at readiness, costs no credits, and is never counted in the AI score. WProofreader's own AI writing assistant is switched off.

**Does the AI approve or reject my standards?**  
No. Approval is the chain's: writer, reader, editor. The AI only adds findings you can accept or ignore.

**Can a writer see it?**  
Writers see the findings and the score. Only coordinators and editors can start a run, see credits, or send a standard back.

**If I ignore a finding, does it come back?**  
Not unless you chose "Will fix after this draft", which reopens it on the next draft, or you reopen it yourself. The same finding is recognised across runs and drafts, so your decision carries.

**What happens to my text at the provider?**  
It is processed and discarded. Zero data retention, no training. SPOL keeps prompts and responses for 24 hours for debugging, then deletes them.

**Why is one standard "not checked"?**  
Because something made the result unsafe to show: personal data was detected, the response was too long to read in one pass, the output could not be verified against your text, or the provider was unavailable. You are refunded for it and the reason is shown.

**Can I run it on an approved standard?**  
Yes. Every selected standard is read, approved or not. You can also open any standard, comment on passages, and send it back from Readiness.

**Does using it change what the accreditor receives?**  
No. The published report contains only what your team wrote and approved. The AI-involvement report, if you choose to share it, shows exactly how AI was used.

Technical readers: the full specification of the calls (prompts, schemas, validators, costs, tests) is the companion document "AI readiness and Auto-format: the calls, in full".
