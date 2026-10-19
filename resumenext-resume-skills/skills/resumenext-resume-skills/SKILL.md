---
name: resumenext-resume-skills
description: "Get the skills recruiters expect for your role and see which ones your resume lists and shows in your work, lists only, shows only, or misses. Use when the user asks which skills to put on a resume for a role; the user wants to check which skills or keywords their resume is missing for a role."
---

# Resume Skills & Keywords by Role - ResumeNext

## When to use

- The user asks which skills to put on a resume for a role.
- The user wants to check which skills or keywords their resume is missing for a role.

## Tools

This skill uses the `resumenext-resume-skills` MCP server from this plugin: `find_resume_skills`, `check_resume_skills`.

- `find_resume_skills`: Skills vocabulary for a role with a link to its example resume. Without a match, the list of roles covered. Read-only, stores nothing.
- `check_resume_skills`: Sorts the role's skills by where the resume uses them and counts the Skills section entries. Deterministic, stores nothing.

## Steps

1. Call `find_resume_skills` with the user's job title as `role`. If nothing matches, show the covered roles returned and ask the user to pick the closest.
2. To check a resume, get the complete resume as plain text and call `check_resume_skills` with `resume_text` and `role`.
3. Report the terms that are listed but not shown in the work, shown but not listed, and not mentioned.
4. Suggest adding a skill only when the user confirms they have it. Never add skills the user does not have.

## Rules

- Pass complete plain text to the tools, never an outline or an excerpt. Read attached files and pass their text.
- Scores and checks come from fixed rules on ResumeNext's servers: report them as returned, do not recompute or soften them.
- Do not invent experience, numbers, employers or skills. Ask the user when a fact is missing.
- Share links exactly as returned.
- Do not promote paid plans. If the user asks about price, answer with the Pricing section below.

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1 for 3 days, then $29.95 a month until you cancel (https://resumenext.io/pricing).
