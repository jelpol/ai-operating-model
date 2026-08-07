# ATS Upload Notes - Quick Reference

**Version:** 1.0 (public starter kit release)
**Type:** Reference doc, not a module
**Purpose:** Just-in-time checklist for handling common ATS upload quirks. Read this immediately before submitting any application.

**Field note:** Some examples below use cybersecurity roles and a no-completed-degree education profile; adapt the specifics to your own field and history. The playbook structure is the product.

## Use this when
- You're about to upload the ATS version of a resume to a company's application portal
- The portal is asking for fields that don't map cleanly to your resume
- You suspect parsing went wrong after upload

---

## Knockout questions playbook

Knockout questions are the top killer of cold applications. An auto-reject fires before a human ever sees the resume. Handle every knockout field deliberately.

**a) Degree question.** Answer truthfully. If you do not hold the degree, the answer is No. Never misstate. A false degree claim is a background-check failure and worse than any rejection.

**b) Screen the JD BEFORE building.** If the JD says "Bachelor's required" WITHOUT "or equivalent experience" language and you lack the degree, that is a knockout-risk target. Flag it in Module 01's application context so you decide to invest (or not) with eyes open.

**c) Free-text and "other education" fields.** Where the form offers a free-text or "other education" field, use a one-line equivalency statement built from your fact registry, following this pattern: "[X]+ years [field] experience including [senior roles held], active certifications, [relevant coursework]."

**d) Log suspected degree auto-rejects.** OPTIONAL - becomes useful once you are juggling multiple applications. Every application suspected of dying on a degree knockout gets logged in your session notes (my-data/). Those employers get deprioritized in future targeting - no point re-feeding the same filter.

**e) Years-of-experience dropdowns.** Answer from the full career. Don't undercount by answering from a single role or title.

**f) Salary fields.** Pick ONE stance BEFORE any screen and hold it. Never write "negotiable". Prefer leaving the field blank where allowed; where mandatory, enter the researched band top.

**g) Clearance or headline-credential fields.** [Optional: one line for an active clearance or headline certification, if you have one.] State exactly what you hold, nothing more specific. Never claim a level or credential that is not confirmed in your fact registry.

---

## Education fields

This section matters most if your education is coursework rather than a completed degree. Lock your education presentation once in prompts/principles.md and reuse it everywhere:

- **PRINT education line:** a coursework line such as "[University], coursework toward B.S. [Field] (paused for professional commitments)". No degree claim, ever.
- **ATS-file education line:** "[University] - undergraduate coursework in [Field] (paused for professional commitments)". Rationale: portal parsers (Greenhouse/Oracle/Workday/Paycor class) extract degree level from the "B.S." token anywhere in the education entry and ignore parentheticals, auto-filling a completed Bachelor's that contradicts a truthful degree screening answer in the same application. Removing the degree token entirely is the only wording that defeats the parser; the "(paused for professional commitments)" rationale stays for human readers. The manual education-card review below remains the real gate.
- **ATS forms demanding full history:** may list every institution you attended, accurately. Full history exists only where the form requires it.
- **"Highest level of education completed" dropdowns:** "Some college" or the nearest truthful option. Never select a degree level you have not earned.
- **Graduation year fields:** for coursework-only entries, enter the most recent year of coursework activity (ATS engines require a year).
- **Always review the auto-parsed education card** after upload and correct any auto-filled degree before submitting - integrity requirement, not optional.

---

## ATS-vs-PRINT decision tree

- Portal upload = ATS docx (or PDF where the portal prefers it: Greenhouse, Lever)
- Email to a human = PRINT PDF
- Recruiter asks for "your resume" with no portal = PRINT PDF
- Interview handoff = PRINT PDF, printed

The file actually uploaded or emailed uses the submission filename ("[Your Full Name] Resume - [Target Role]") per Module 11 - never the internal "[YourName]-..." working-file naming.

---

## Common ATS portals and their quirks

### Workday
- **File format:** docx preferred over PDF (parsing is better)
- **Quick Apply gotcha:** pre-fills fields incorrectly. Review every field before submission
- **Page count:** 4 pages reliable; some configurations cut at 3
- **Education year:** Workday requires a graduation year. For coursework-only, enter the most recent year of activity
- **Skills field:** Workday weights this field heavily. Paste your "Core Competencies" content verbatim
- **Cover letter:** usually a separate field; don't paste into the resume

### Cover-letter delivery decision tree (some sites do not allow attaching a cover letter)
1. **Attachment field exists:** attach the CL PDF.
2. **Textbox exists (cover letter / additional info / why-interested):** paste the CL body as plain text (opener paragraph only if the box is why-interested class - it outranks an attachment).
3. **NO field of any kind:** do NOT force the letter (never embed it in the resume file, never cram it into an unrelated question). The letter still gets built and packaged - it becomes recruiter-outreach and follow-up-email material. Note the no-field fact in the package manifest at submission.

### Greenhouse
- **File format:** PDF acceptable here (formatting preserved better)
- **"Why interested" textbox:** if present, paste your cover letter opener paragraph - this box outranks the attached letter (see Module 08 COLD PORTAL MODE)
- **Multi-column resumes:** Greenhouse parses single-column more reliably - ATS version with single-column layout is critical
- **Custom questions:** recruiters actually read these. Don't skip; answer briefly

### Lever
- **File format:** PDF preferred
- **Resume parsing:** strips formatting on display. Structure matters less, content matters more
- **Cover letter field:** usually a single textbox; paste the cover letter as plain text

### iCIMS
- **Older ATS, more brittle parsing**
- **Format:** use ATS version with simplest formatting
- **Em-dashes:** iCIMS sometimes renders as question marks. Use regular hyphens (Principle #14 bans em-dashes anyway)
- **Headers/footers:** stripped on parse. Never put contact info there
- **Date handling:** iCIMS is picky. Use "MMM YYYY" format consistently ("Feb 2025" not "February 2025")

### Taleo
- **Worst parser of the majors.** Assume the parse will mangle anything non-trivial
- **Plainest file wins:** ATS docx, single column, zero decoration
- **Expect manual field re-entry:** budget time to retype titles, dates, and education after upload; verify every parsed field

### SuccessFactors
- **Very literal parser.** Keep formatting minimal
- **Verify the parsed preview carefully** before submitting - it will take what it parsed, not what you uploaded

### SmartRecruiters
- Modern parser, generally well behaved; standard ATS docx works
- Still preview and verify every auto-filled field

### Ashby
- **Common at AI-sector companies** - expect it on those targets
- Clean parser; custom questions are prominent and read by humans - answer them deliberately

### ADP portal
- HR-suite portal, form-heavy; parsing is secondary to the forms
- Expect to enter most data manually; the resume attaches as a document

### LinkedIn Easy Apply
- **ALWAYS verify the submission confirmation arrives.** A real-world application once produced only an error notice, and its status could never be verified afterward
- Screenshot or save the confirmation for every Easy Apply submission; record it in your session notes
- If no confirmation appears, treat the application as NOT submitted and follow up

### Generic email-based applications
- Use PRINT version, not ATS - a human reads it
- Attach as PDF (preserves formatting), using the submission filename: "[Your Full Name] Resume - [Target Role].pdf"

---

## Universal rules for any ATS

1. **Always preview after upload.** Most ATS portals show you what they parsed. Fix anything that looks wrong before submitting.

2. **Don't trust the auto-fill.** ATS engines guess your job titles, dates, education. Verify every field.

3. **Headline-title rule.** Mirroring the JD's job title applies to the HEADLINE line under the contact block and to summary framing ONLY. If the JD says "Director, Identity Access Management" and the headline says "Director, IAM Operations," adjust the headline to the JD's exact wording where truthful. Actual job-title lines in the Experience section are NEVER retitled - the real titles stay, and content bridges the gap (title-to-content bridge lock, Principle #10).

4. **Keyword density check.** Make sure must-have JD keywords appear at least 2 times. Use Module 02's keyword density check before upload.

5. **Date format consistency.** Use the same format throughout: "Feb 2025 - Present" - don't mix with "February 2025 - Present" elsewhere.

6. **Education year handling.** If your education is "Coursework" rather than a completed degree, enter the most recent year of coursework. ATS engines require a year for education entries. (See the Education fields section above for the full playbook.)

7. **References.** Never include references on the resume. If the application asks for references, provide separately when requested.

8. **Salary expectations field.** Pick ONE stance before any screen. Never write "negotiable". Leave blank where the field allows it; where mandatory, enter the researched band top. Do not improvise a number mid-application.

9. **Diversity/EEO section.** Always optional. Your call.

---

## Pre-submission checklist

Before clicking submit on any application:

- [ ] Resume ATS version uploaded (not PRINT), using the submission filename per Module 11
- [ ] Cover letter uploaded or pasted per Module 08's placement decision (separate field, not embedded)
- [ ] Every auto-filled field verified
- [ ] Job title in HEADLINE matches JD vocabulary (where truthful); Experience titles untouched
- [ ] Degree question answered truthfully; equivalency statement used where a free-text field exists
- [ ] Years-of-experience fields answered from the full career
- [ ] Clearance/credential field (if applicable): state exactly what you hold, nothing more
- [ ] Salary field handled per the single pre-chosen stance
- [ ] LinkedIn URL provided and current
- [ ] All custom questions answered (don't skip)
- [ ] Diversity/EEO section completed if you choose
- [ ] Hiring manager personalization in cover letter (if name known)
- [ ] Submission confirmation captured (screenshot or saved email - mandatory for LinkedIn Easy Apply)
- [ ] Application submission timestamp captured in your session notes

---

## After-submission notes (capture in your session notes, my-data/)

For each application, record:
- Date submitted
- Portal used
- Recruiter or hiring manager name (if known)
- Application ID or confirmation number (plus the saved confirmation for Easy Apply)
- Suspected knockout risks (degree, credential) so outcomes can be interpreted later
- Notes on portal quirks encountered (so future applications skip the friction)

This builds a searchable application history that informs future tailoring decisions and the degree auto-reject deprioritization list. OPTIONAL - becomes useful once you are juggling multiple applications.

---

## When to revisit this doc

Update when:
- A specific ATS portal surfaces a new quirk worth tracking
- You encounter a parsing issue not yet documented
- A new ATS engine becomes relevant to a target role family
- A successful submission reveals a non-obvious portal-specific tip
- A suspected knockout auto-reject pattern is confirmed or disproven
