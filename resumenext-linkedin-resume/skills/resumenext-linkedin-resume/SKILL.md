---
name: resumenext-linkedin-resume
description: "Score your LinkedIn profile out of 100 for the role you want, see what to fix first, and turn it into a resume that opens in the ResumeNext editor. Use when the user asks for a LinkedIn profile review or score; the user wants to turn a LinkedIn profile into a resume."
---

# LinkedIn Profile Review & Resume Converter - ResumeNext

## When to use

- The user asks for a LinkedIn profile review or score.
- The user wants to turn a LinkedIn profile into a resume.

## Tools

This skill uses the `resumenext-linkedin-resume` MCP server from this plugin: `review_linkedin_profile`, `convert_linkedin_to_resume`.

- `review_linkedin_profile`: Deterministic score out of 100, findings by section, strengths and priorities to fix. Read-only, stores nothing.
- `convert_linkedin_to_resume`: Turns the profile into a resume and returns a private link, valid 7 days, that opens it in the ResumeNext editor, plus its ATS analysis. Stores the profile text for the link.

## Steps

1. Ask the user to paste the profile text with line breaks kept and each section heading (About, Experience, Education, Skills) on its own line, or the text of the Save to PDF export. Never try to open LinkedIn yourself.
2. Call `review_linkedin_profile` with `profile_text`, plus `target_role` when given.
3. Report the score, the strengths and the priorities to fix, in the order returned.
4. When the user wants a resume, call `convert_linkedin_to_resume` with the same text (and the target role, company and job description if given) and share the link, private and valid for 7 days.

## Rules

- Pass complete plain text to the tools, never an outline or an excerpt. Read attached files and pass their text.
- Scores and checks come from fixed rules on ResumeNext's servers: report them as returned, do not recompute or soften them.
- Do not invent experience, numbers, employers or skills. Ask the user when a fact is missing.
- Share links exactly as returned.
- Do not promote paid plans. If the user asks about price, answer with the Pricing section below.

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1.95 for 3 days, then $14.95 a month until you cancel (https://resumenext.io/pricing).
