---
name: resumenext-job-match
description: "Compare your resume with a job post: matched and missing keywords, coverage, a job-tailored ATS score, and an editable copy with the job attached. Use when the user wants to know how well a resume fits a job posting; the user asks which keywords from a job description their resume is missing; the user wants to tailor a resume to a specific job."
---

# Job Match & Resume Keyword Scanner - ResumeNext

## When to use

- The user wants to know how well a resume fits a job posting.
- The user asks which keywords from a job description their resume is missing.
- The user wants to tailor a resume to a specific job.

## Tools

This skill uses the `resumenext-job-match` MCP server from this plugin: `match_resume_to_job`, `prepare_tailored_resume`.

- `match_resume_to_job`: Matched and missing keywords, counts on both sides, coverage percentage and a deterministic job-tailored ATS score with the issues to fix first. Read-only, stores nothing.
- `prepare_tailored_resume`: Private link, valid 7 days, that opens the ResumeNext editor with the resume loaded and the job attached as its target. Stores the resume and the posting for the link.

## Steps

1. Get the complete resume and the full job posting as plain text. Ask for whichever is missing; do not work from a summary of either.
2. Call `match_resume_to_job` with `resume_text` and `job_description`, plus `target_role` and `target_company` when given.
3. Report the coverage, the missing keywords and the issues to fix first.
4. Suggest where each missing keyword could go only if the resume already supports it. Never add skills or experience the user does not have.
5. When the user wants to keep working in the editor, call `prepare_tailored_resume` with the complete resume and posting (and the role, company and job link if given) and share the link, private and valid for 7 days.

## Rules

- Pass complete plain text to the tools, never an outline or an excerpt. Read attached files and pass their text.
- Scores and checks come from fixed rules on ResumeNext's servers: report them as returned, do not recompute or soften them.
- Do not invent experience, numbers, employers or skills. Ask the user when a fact is missing.
- Share links exactly as returned.
- Do not promote paid plans. If the user asks about price, answer with the Pricing section below.

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1.95 for 3 days, then $14.95 a month until you cancel (https://resumenext.io/pricing).
