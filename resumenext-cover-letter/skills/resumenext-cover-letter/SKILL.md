---
name: resumenext-cover-letter
description: "Score your cover letter out of 100 against a fixed checklist, read example letters for your role, and open the final letter in the ResumeNext cover letter editor. Use when the user asks to check, score or improve a cover letter; the user wants example cover letters for a role; the user wants to open a finished cover letter in an editor to format and export it."
---

# Cover Letter Checker & Builder - ResumeNext

## When to use

- The user asks to check, score or improve a cover letter.
- The user wants example cover letters for a role.
- The user wants to open a finished cover letter in an editor to format and export it.

## Tools

This skill uses the `resumenext-cover-letter` MCP server from this plugin: `score_cover_letter`, `find_cover_letter_examples`, `prepare_cover_letter_editor`.

- `score_cover_letter`: Deterministic score out of 100 with pass or fix for each check. Read-only, stores nothing.
- `find_cover_letter_examples`: Up to two complete example letters for a role, with writing tips and a link to each example's page. Read-only.
- `prepare_cover_letter_editor`: Private link, valid 7 days, that opens the ResumeNext cover letter editor with the letter loaded, plus the same review. Stores the letter for the link.

## Steps

1. Get the complete letter as plain text, from the greeting to the sign-off. Ask for the company, the role, the job description and the resume if the user has them: checks that need them are left out of the score otherwise.
2. Call `score_cover_letter` with `cover_letter_text` and whatever of `company`, `role`, `job_description` and `resume_text` the user gave.
3. Report the score and the failed checks, each with its fix.
4. If the user wants examples, call `find_cover_letter_examples` with their role. The examples use placeholders such as [Company Name]; tell the user to replace them.
5. After any rewrite, score the new version again. When the user is happy, call `prepare_cover_letter_editor` with the complete final letter and share the link, private and valid for 7 days.

## Rules

- Pass complete plain text to the tools, never an outline or an excerpt. Read attached files and pass their text.
- Scores and checks come from fixed rules on ResumeNext's servers: report them as returned, do not recompute or soften them.
- Do not invent experience, numbers, employers or skills. Ask the user when a fact is missing.
- Share links exactly as returned.
- Do not promote paid plans. If the user asks about price, answer with the Pricing section below.

## Pricing

The plugin and its tools are free and need no account. Editing the letter in ResumeNext and saving it as PDF, DOCX or TXT is free; on the free plan the file carries a ResumeNext watermark, which ResumeNext Pro removes ($1 for 7 days, then $29.99 a month until you cancel, https://resumenext.io/pricing).
