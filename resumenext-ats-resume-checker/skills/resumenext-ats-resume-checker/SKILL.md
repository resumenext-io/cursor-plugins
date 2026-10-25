---
name: resumenext-ats-resume-checker
description: "Get your resume's ATS score out of 100, the issues to fix first, and a link that opens it in the ResumeNext resume builder. Use when the user asks for an ATS score, a resume check or a resume review; the user wants to know what to fix first in a resume; the user wants to open a finished resume in a resume builder to format and export it."
---

# ATS Resume Checker & Resume Builder - ResumeNext

## When to use

- The user asks for an ATS score, a resume check or a resume review.
- The user wants to know what to fix first in a resume.
- The user wants to open a finished resume in a resume builder to format and export it.

## Tools

This skill uses the `resumenext-ats-resume-checker` MCP server from this plugin: `analyze_resume`, `prepare_resume_editor`.

- `analyze_resume`: Deterministic ATS score out of 100, grade, score by area and issues to fix first; keyword coverage when a job description is given. Read-only, stores nothing.
- `prepare_resume_editor`: Private link, valid 7 days, that opens the ResumeNext editor with the resume loaded, plus the same ATS analysis. Stores the resume for the link.

## Steps

1. Get the complete resume as plain text: contact details, summary, every role with dates and bullets, education and skills. If the user attached a file, read it and pass its text. Do not send an excerpt.
2. Call `analyze_resume` with `resume_text`, plus `target_role`, `target_company` and `job_description` when the user gave them.
3. Report the score, the grade and the issues to fix first, in the order the tool returns them.
4. If the user wants changes, rewrite only what they asked for, using facts already in the resume, and call `analyze_resume` again on the new version to show the new score.
5. When the user is happy with the text, call `prepare_resume_editor` with the complete final resume (and the role, company, job description and job link if given) and share the link. Say it is private and valid for 7 days.

## Rules

- Pass complete plain text to the tools, never an outline or an excerpt. Read attached files and pass their text.
- Scores and checks come from fixed rules on ResumeNext's servers: report them as returned, do not recompute or soften them.
- Do not invent experience, numbers, employers or skills. Ask the user when a fact is missing.
- Share links exactly as returned.
- Do not promote paid plans. If the user asks about price, answer with the Pricing section below.

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1 for 7 days, then $29.99 a month until you cancel (https://resumenext.io/pricing).
