---
name: resumenext-resume-bullet-points
description: "Check resume bullet points line by line for action verbs, numbers, first person and phrases to delete, and get action verbs by type of work. Use when the user asks to check, improve or rewrite resume bullet points; the user asks for action verbs or stronger words for a resume."
---

# Resume Bullet Point Checker & Action Verbs - ResumeNext

## When to use

- The user asks to check, improve or rewrite resume bullet points.
- The user asks for action verbs or stronger words for a resume.

## Tools

This skill uses the `resumenext-resume-bullet-points` MCP server from this plugin: `check_resume_bullets`, `find_action_verbs`.

- `check_resume_bullets`: Per-line check against ResumeNext's action verb guide and ATS line checks, totals, and the lines to rewrite first. Deterministic, stores nothing.
- `find_action_verbs`: Action verbs for a type of work (leadership, building, process-improvement, analysis, finance, communication, sales, teaching, care), phrases to delete and rules for picking a verb. Read-only.

## Steps

1. Get the bullet points exactly as the user wrote them, one per line (up to 60 lines).
2. Call `check_resume_bullets` with them as `bullets`.
3. Report the lines to rewrite first and, for each, what to change.
4. When a line needs a better verb, call `find_action_verbs` with the matching `work_type`, and propose rewrites that keep the user's facts. Never invent numbers: if a line needs one, ask the user for it.
5. Run `check_resume_bullets` again on the rewritten lines to confirm they pass.

## Rules

- Pass complete plain text to the tools, never an outline or an excerpt. Read attached files and pass their text.
- Scores and checks come from fixed rules on ResumeNext's servers: report them as returned, do not recompute or soften them.
- Do not invent experience, numbers, employers or skills. Ask the user when a fact is missing.
- Share links exactly as returned.
- Do not promote paid plans. If the user asks about price, answer with the Pricing section below.

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1 for 7 days, then $29.99 a month until you cancel (https://resumenext.io/pricing).
