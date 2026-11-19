---
name: "untapped-assessment-prefill"
description: "One pass from RJ's single dictation to a filled Case Management Assessment Form in Untapped Solutions: drafts the SOAP note and goals, pulls the participant's profile from the CRM edit screen, and fills the form. Use when RJ says fill the assessment, start an assessment, or prefill the assessment for a participant."
---

# Untapped Assessment: One Pass

RJ runs case management assessments on site (House A, House B, House C). He gives **one input**: the participant's name, plus his summary or read-through of the session. That covers what came up, the outcomes, the goals, and anything he read off the paper assessment. From that single input, this skill does the whole job:

1. Draft the SOAP note and goals.
2. Find the participant's profile in Untapped and pull their file information from the Edit screen.
3. Fill the Case Management Assessment Form with the profile information, the session details, the SOAP note and the goals.
4. Stop before Submit so RJ can review.

Do not ask him for the pieces one at a time. If something essential is missing (usually the session date), take your best pass, then ask one question at the end. If a SOAP note for this contact was already drafted this session, use it rather than drafting a new one.

## 1. Read the input

Confirm the participant's name and session date in one line, since voice input garbles both. Correct voice-to-text garbles silently, using the list in the soap-case-note skill (partner names, expungement, IEHP, DOR and the others).

Sort what he said into:
- **Session details:** what PT reported, what CM did, documents, referrals, dates.
- **Outcomes:** what got done this session.
- **Goals:** what PT is working toward.
- **Direct answers to assessment questions:** anything he read off the paper form.

## 2. Draft the SOAP note and goals

Follow the soap-case-note skill exactly. This is an **initial note**, since it follows an assessment, so the consent block goes in Objective. Leave Participant Name and ID blank.

Build the three goal fields in the soap-case-note format: short, lowercase, comma-separated phrases, no periods.
- 1st Goal: stabilization (documents, benefits, health access)
- 2nd Goal: education, employment, financial
- 3rd Goal: housing and transportation

Show him the SOAP note and goals in chat, with no participant name in them, and keep going. Add the contact to the week ledger (`claude/week-ledger.md`) as an assessment, with initials only.

## 3. Pull the participant's profile

Use the Claude in Chrome tools in RJ's work Chrome. Do not use desktop clicks. The CRM is read only here: never press Update Contact or change a field.

**Finding the record** (tested 9/22/26):
- **His caseload:** on the staff dashboard (`[crm-host]/app/staffDashboard`), type the last name into "Search contacts by name, email, or organization" and click the result. It opens `/app/analytics/<id>`. The record is at `/app/view/<id>`.
- **Not on his caseload:** open the CRM menu (the second icon in the left rail; click it, don't hover), choose Clients & Cases, set Filters to All (show all staff), then use Filter, Basic Info, Last Name, Apply Filters. Going straight to the `lifePathDashboard` URL sends you back to the dashboard, so always go through the menu.
- If several records match, list them by first name and house, and ask which one.
- If none match, stop and tell him. Do not create a client.

**Reading the file:** from the record, open **Edit** (Edit Service Recipient). Read every field in the panel, scrolling to the bottom: name, date of birth, phone, case number, email, ethnicity, gender, marital status, preferred language, address, barriers, goals and anything else it holds.

**Check for a mislink before filling.** Open the record's **Forms** tab. If it already has a Case Management Assessment Form under a different participant's name, or this participant's form shows up on someone else's record, stop and tell RJ. A form submitted with the wrong case number gets attached to the wrong participant, and Untapped has no way to move it afterward. (This happened on a 9/2/26 submission.)

## 4. Fill the assessment form

Open the blank form in its own tab:
`[assessment form link]`
If that link no longer loads, go to `[crm-host]/app/iframe/untapped-forms`, search "case management", open **Case Management Assessment Form**, choose **Share**, and open the shareable link.

Read the form's full field list first with `get_page_text`, then fill:

- **From the Edit screen:** Case Number (copy it character for character, since it's what links the form to the file), First, Middle and Last Name, Date of Birth (mm/dd/yyyy), Contact Number (from Phone), Email, and every other field whose label matches a profile field (gender, ethnicity, marital status, preferred language, housing, program, house). Work out Current Age from the date of birth and today's date.
- **From RJ's input:** Today's Date, Date of Entry, Exit Date, emergency contact, and each assessment question he answered.
- **Desired results and goals:** the three goal fields from step 2. Use the SOAP Assessment and Plan for any "desired result" or outcome box.
- **Session and notes boxes:** the SOAP text, or the matching part of it, wherever the form asks for session details or case notes.
- Leave a field blank when neither source answers it. Do not guess. No diagnoses, no clinical labels, nothing inferred about mental health or substance use. Record only what PT said or what CM observed.

Rich text boxes grow with long entries and push fields down the page. After any long entry, take a fresh screenshot before clicking the next field.

## 5. Verify and stop

- Read the whole form back with `get_page_text`. Check by reading the page, not by where you clicked.
- Confirm that the case number and the name on the form both match the Edit screen.
- **Never press Submit or Print.** RJ reviews and submits it himself.

## Reporting back

One short message:
- The form is ready for review.
- Which fields came from the profile, which from his input, and which are still blank. Use field names only.
- The one question, if any.

Do not put the participant's date of birth, phone, email, address or case number in chat. They stay in the form.

## If something blocks

If a page won't load, the extension can't reach Untapped, a menu won't open, or the form layout has changed, stop after two tries on that step. Tell him what got done and what didn't. Do not work around it.