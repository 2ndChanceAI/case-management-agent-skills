---
name: "untapped-form-audit"
description: "Check Untapped Solutions for participants missing a Case Management Assessment Form or case manager notes. Use when RJ says check for missing assessments, who needs an assessment, audit forms, or check a participant's forms."
---

# Untapped Form Audit

RJ needs to know which participants have no Case Management Assessment Form on file, and which ones are behind on case manager notes. Untapped Solutions links a submitted form to a participant's record when an identifier on the form matches the record, usually the case number and sometimes the email. A participant with no linked assessment either never had one done, or had one submitted with a case number that didn't match. Either way, it needs a look.

The outcome: a short list showing, for each participant checked, whether an assessment is on file, when the last one was submitted, and when the last case manager note was submitted.

## Scope

Ask only if it isn't clear:
- **One participant.** He gives a last name.
- **His caseload.** Records under the **[caseload filter]** filter.
- **A house.** Records whose program or house is House A, House B or House C.

If he says "check for missing assessments" with nothing else, run his caseload.

## Steps

Use the Claude in Chrome tools in RJ's work Chrome. This is read only. Do not edit, add, message or submit anything.

1. **Open Clients & Cases** at `[crm-host]/app/lifePathDashboard` (CRM menu, then Clients & Cases).
   - For one participant, set Filters to **All (show all staff)** and search the last name. If several records match, list them by first name, house and program, and ask which one.
   - For his caseload, use the **[caseload filter]** filter and set per page to 100 so the whole list shows.

2. **Open each participant's record** with View. The record page lives at `[crm-host]/app/view/<id>`. Collect the record IDs from the list with `read_page`, so you can go to each one directly.

3. **Open the Forms tab** on the record. It is at the end of the tab row, past Documents. The Form Submissions panel lists every linked submission, and **Filter by form** narrows it by form type. Read it with `get_page_text`.
   - **Case Management Assessment Form:** count and most recent date.
   - **Case manager notes** (the Case Management Notes form, or PSS NOTES ONLY): most recent date.
   - Also note the "Why linked" identifier (Case # or Email). It shows how the match was made.

4. **Close the panel and move to the next record.** For a caseload run, work through the records one after another. Report progress in one line every ten or so records.

## Flags

- **Missing assessment:** no Case Management Assessment Form linked.
- **Note overdue:** no case manager note in the last 7 days. Use a different window if RJ names one.
- **Possible unlinked form:** RJ remembers doing an assessment but none is linked. The case number on the submission likely didn't match the record. Suggest checking the case number, since the untapped-assessment-prefill skill copies it exactly to prevent this.

## Reporting back

No names. Use initials and house only, the same as the week ledger.

```
Missing assessment
- A.A., House A

Note overdue (last note)
- B.B., House C (9/2/26)

Up to date
- C.C., House A: assessment 9/1/26, note 9/18/26
```

Then offer one next step: prefill the assessment for anyone missing one (untapped-assessment-prefill), or draft notes for anyone overdue (soap-case-note).

Do not put case numbers, emails, phone numbers or dates of birth in the report, even though the Forms panel shows them.

## If something blocks

If the extension can't reach Untapped, a record won't load, or the Forms tab has moved, stop after two tries on that step. Tell him which participants were checked and which were not.