# Case Management Agent Skills (Claude)

Three Claude skills Richard Jones built and used every workday on his own caseload as a case manager in reentry housing (Sept to Oct 2026). They turn one voice dictation into a finished SOAP note, prefill the agency's assessment form in its CRM (Untapped Solutions), and audit a caseload for missing paperwork.

Agency, site and partner names, and internal links, have been replaced with placeholders like `[agency]` and `House A`.

| Skill | What it does |
|---|---|
| `soap-case-note` | Rough notes or voice memos become a SOAP note in the agency's house style |
| `untapped-assessment-prefill` | One dictation becomes a SOAP note and goals, reads the participant's profile in the CRM, and fills the assessment form |
| `untapped-form-audit` | Checks each participant's record for a missing assessment or late case notes |

## Guardrails built in

- **Read only in the CRM.** The agent never edits a record, creates a client or presses Update.
- **A human submits.** The agent stops before Submit and Print. The case manager reviews every form.
- **No identifiers in drafts or chat.** Participant name and ID fields stay blank by design, and dates of birth, phones and case numbers never appear in chat.
- **Accurate legal records.** The consent statement only goes on initial notes. Adding it to a follow-up would put a false statement in a legal record.
- **No guessing.** Garbled names get a placeholder and a question. Acronyms in legal records are never guessed. Blank fields stay blank.
- **Mislink check.** Before filling, the agent checks that no form is already attached to the wrong participant. A real misfiled form on 9/2/26 is why this rule exists.

## How they're used

Load a folder as a Claude skill. The CRM steps use Claude in Chrome on the case manager's own signed-in browser.
