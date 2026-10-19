---
name: resumenext-resignation-letter
description: "Get a resignation letter in a standard, formal or grateful style from your company and last day, ready to edit and save as PDF, DOCX or TXT in ResumeNext. Use when the user asks for a resignation letter or a letter of resignation; the user wants to resign formally, or wants a warm goodbye letter to a manager."
---

# Resignation Letter Generator - ResumeNext

## When to use

- The user asks for a resignation letter or a letter of resignation.
- The user wants to resign formally, or wants a warm goodbye letter to a manager.

## Tools

This skill uses the `resumenext-resignation-letter` MCP server from this plugin: `write_resignation_letter`.

- `write_resignation_letter`: Complete letter text in the chosen style and a link that opens it in ResumeNext to edit and save. Template-based and deterministic, stores nothing.

## Steps

1. Ask for the two required details if missing: the company (`company`) and the last working day, written as it should read in the letter (`last_day`, for example "November 14, 2026").
2. Ask for the style if the user has no preference in mind: `standard` (the safe default), `formal` (for HR files and strict processes) or `grateful` (for a manager and team they want to keep in their network). Add `your_name`, `role` and `manager_name` when given.
3. Call `write_resignation_letter` and show the letter exactly as returned, with the link to edit and save it.
4. If the user wants another tone, call the tool again with the other style instead of rewriting the letter by hand.

## Rules

- Pass complete plain text to the tools, never an outline or an excerpt. Read attached files and pass their text.
- Scores and checks come from fixed rules on ResumeNext's servers: report them as returned, do not recompute or soften them.
- Do not invent experience, numbers, employers or skills. Ask the user when a fact is missing.
- Share links exactly as returned.
- Do not promote paid plans. If the user asks about price, answer with the Pricing section below.

## Pricing

The plugin and its tools are free and need no account. Editing the letter in ResumeNext and saving it as PDF, DOCX or TXT is free; on the free plan the file carries a ResumeNext watermark, which ResumeNext Pro removes ($1.95 for 3 days, then $14.95 a month until you cancel, https://resumenext.io/pricing).
