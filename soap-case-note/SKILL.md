---
name: soap-case-note
description: "Draft SOAP case notes in the agency's Untapped Solutions house style from rough session notes, voice memos, or fragments. Leaves participant name and ID blank for the case manager to fill in."
---

# SOAP Case Note Drafting

Turn rough session input (voice-to-text fragments, bullet notes, "didn't show, called twice") into a finished Case Manager Note matching the house style used in Untapped Solutions.

## Which fields to fill and which to leave blank

**Always fill:**

- **Note Date**: the date of the contact, format `YYYY-MM-DD`.
- **Case Manager Initial**: always `RJ`.

**Always leave blank:**

- **Participant Name**
- **Participant ID** and case number

RJ withholds participant identity deliberately and fills those in himself. Never write a participant name or ID in those fields or inside the narrative. This holds even when a name appears in the input. If he dictates "met with Jane Doe today," the narrative says PT and the name does not reach the draft. Do not guess at an ID or carry one forward from an earlier note.

Initials are the one exception, and only as a block label outside the note body so he can tell drafts apart while filling them in. Never inside Subjective, Objective, Assessment or Plan.

A missing name or ID is never thin input. Those stay blank by design and are not something to ask about. A missing date is worth asking for, since that field does get filled.

## Two note types

An assessment is documented on a separate assessment form, not here. What follows that form is an **initial note**. Everything after it is a **follow-up note**.

**Initial note** (written after an assessment form is completed) carries the consent block in Objective, verbatim:

```
CM reviewed the consent forms with PT and PT consented to services. CM disclosed mandated reporter status and explained that CM is required to report any disclosure indicating risk of harm to PT or to another person.
```

**Follow-up notes** (check-ins, texts, calls, service coordination, drop-ins) never carry the consent block. Adding it to a note documenting a single text message would put a false statement in a legal record.

If it is unclear which type a note is, ask. Do not default to including the block.

## Output format

```
Participant Name: ______________________
Participant ID: ______________________
Case Manager Initial: RJ
Note Date: YYYY-MM-DD

Subjective:
Objective:
Assessment:
Plan:
```

When several notes go out together, keep each one a separate block and label the blocks by date, participant initials, and contact type.

Do not invent the goal fields. If they are needed and were not dictated, ask, or note they carry forward from the prior note.

## Typing notes into the Untapped Solutions portal

The Case Manager Note form at `[crm-host]/untapped-forms/forms/<uuid>` has seven rich text boxes: three Goal fields and the four SOAP fields. Fill those seven plus Case Manager Initial and Note Date. Leave Name, Email, Case Number and the phone-change radio for RJ.

Never press Submit. RJ reviews and submits every note himself. The form autosaves locally only, so nothing reaches the server until he does.

The rich text boxes grow when text is long, which pushes everything below them down the page. Clicking by coordinate after typing a long entry lands in the wrong box. Take a fresh screenshot after any entry longer than about two lines, and verify the whole form with page text before telling him it is ready.

One note per form. After he submits, reload the form URL for a blank one.

## Voice rules (non-negotiable)

- Third person only. Never "I" or "we."
- Two actors: **PT** (participant) and **CM** (case manager). Use the abbreviations, not the full words.
- Past tense throughout. Reported speech: "PT reported...", "PT shared...", "CM received...", "CM attempted to contact..."
- Short declarative sentences. No compound flourishes, no em dashes.
- Dates inside prose use `M/D/YY` (7/23/26), even though the Note Date form field is `YYYY-MM-DD`.
- No diagnoses, no clinical labels, no speculation about mental health or substance use. Record only what PT stated or what CM observed.
- Third person is absolute, which means reflection-style phrasing from CHW coursework does not carry over. Do not reach for "I have seen this before" to avoid the word pattern; drop the claim and state only what happened.

## Section discipline

**Subjective**: attendance status, or what PT said in their own account. Health, mood, employment, housing, and family updates as PT reported them.
- No-show standard line: `PT was not present during the scheduled session.`
- Present example: `PT reported stable health and feeling good this week. PT shared continued full-time employment and plans to provide CM with a copy of the current paystub.`

**Objective**: verifiable facts only. Outreach attempts with dates, documents received or pending, notifications from other staff or programs, appointments confirmed. On an initial note, the consent block goes here.
- Examples: `CM attempted to contact PT on 7/23/26 and 7/24/26; PT did not respond to outreach attempts.` / `CM received notification on 7/21/26 that PT successfully completed the housing program and transitioned to another housing program.`
- Never put CM's opinion here.

**Assessment**: CM's read on progress and whether services are still needed. One or two sentences.
- Examples: `PT's transition indicates completion of program goals and successful movement to the next level of housing support. No further CM services are needed at this time.` / `CM will continue efforts to establish contact with PT.`

**Plan**: the forward action, usually one line with a date. Commonly written without a closing period.
- Examples: `CM will follow up with PT on 7/27/26` / `CM will proceed with closing PT's file according to program procedure and policy` / `No further CM services required at this time`

## One note per participant

Each note covers one PT. When a single piece of work covered more than one participant, such as outreach to a provider on behalf of two people nearing exit, write a separate note for each, since the portal takes one note per participant.

Work done for a participant without the participant present is service coordination, not collateral contact. Standard Subjective line: `PT was not present. CM conducted service coordination on PT's behalf.`

## Recurring names that voice-to-text mangles

RJ dictates by voice and these come through wrong. Correct them silently:

- **[partner legal clinic]**: often garbled. Handles expungement and relief from probation conditions.
- **[agency employment program]**: often garbled.
- **expungement**: heard as "expansion."
- **IEHP**: heard as "IHP."
- **[site names]**: assessment sites.
- **clothing closet**: heard as "closing closet."
- **interview clothes**: heard as "interview flows."
- **DOR** (Department of Rehabilitation), route for participants needing work tools.

When a name is garbled and not on this list, write a neutral placeholder and ask rather than guessing. Never guess at the letters of an acronym in a legal record.

## Standard abbreviations

PT, CM, [agency abbreviation], [program abbreviation], SSC (Social Security card), DL (driver's license), DOR (Department of Rehabilitation), AB 109, CalFresh, General Relief, Medi-Cal, SSI, HVAC, PO (probation officer).

## Goal fields (when asked to produce them)

Carried forward between notes, rarely rewritten. Lowercase comma-separated phrases, no periods. Keep each field short, since a long entry grows the box and breaks the form layout.
- 1st Goal: immediate stabilization, documents, benefits, health access. `get birth certificate, get ssc, get drivers license, apply for CalFresh`
- 2nd Goal: education, employment, financial. `enroll in adult school, find employment, credit repair, open bank account`
- 3rd Goal: housing and transportation, with housing tagged by number. `housing(42), transportation`

## Handling thin input

If the input only covers one or two sections, draft those and leave the others as a single line asking what's missing. Do not pad a section with filler to make it look complete. A no-contact note is legitimately four short lines, and an incomplete assessment is legitimately a short note saying what was not obtained.