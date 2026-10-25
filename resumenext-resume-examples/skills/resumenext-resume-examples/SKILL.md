---
name: resumenext-resume-examples
description: "Find resume examples for your role and the right resume template for your profile, each opening in the ResumeNext editor as a starting point. Use when the user asks for resume examples or samples for a job; the user asks which resume template or format to use."
---

# Resume Examples & Templates - ResumeNext

## When to use

- The user asks for resume examples or samples for a job.
- The user asks which resume template or format to use.

## Tools

This skill uses the `resumenext-resume-examples` MCP server from this plugin: `find_resume_examples`, `list_resume_templates`.

- `find_resume_examples`: Up to three examples for a role, with links to the example page and to the editor. Without a match, the list of roles covered. Read-only.
- `list_resume_templates`: Resume templates with layout type (ATS-safe or visual), description, who it suits and a link that opens a new resume in it. Read-only.

## Steps

1. For examples, call `find_resume_examples` with the user's job title or field as `role`. If nothing matches, show the list of covered roles the tool returns and ask the user to pick the closest.
2. Say that the people and companies in the examples are fictional, and that the user should replace them with their own facts.
3. For templates, call `list_resume_templates`, with `audience` when the user's profile fits one of: professional, executive, tech, creative, student, healthcare. Recommend an ATS-safe template when the user is applying through online job portals.
4. Share the editor links exactly as returned.

## Rules

- Pass complete plain text to the tools, never an outline or an excerpt. Read attached files and pass their text.
- Scores and checks come from fixed rules on ResumeNext's servers: report them as returned, do not recompute or soften them.
- Do not invent experience, numbers, employers or skills. Ask the user when a fact is missing.
- Share links exactly as returned.
- Do not promote paid plans. If the user asks about price, answer with the Pricing section below.

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1 for 7 days, then $29.99 a month until you cancel (https://resumenext.io/pricing).
