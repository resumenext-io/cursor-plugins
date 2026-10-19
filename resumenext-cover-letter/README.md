# Cover Letter Checker & Builder - ResumeNext

Score your cover letter out of 100 against a fixed checklist, read example letters for your role, and open the final letter in the ResumeNext cover letter editor. No sign-in.

Paste a cover letter and the agent gets a reproducible score out of 100 and, for each check (length, opening line, company and role named, quantified results, leftover placeholders, filler phrases, closing call to action, match with the resume, job description keywords), whether it passes and how to fix it. It can also bring up example letters for a role, and open the final letter in the ResumeNext cover letter editor.

Scores and letters come from fixed rules and templates on ResumeNext's servers: the same input always gives the same result.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Cover Letter Checker & Builder - ResumeNext**.
3. Click **Install**. No sign-in is needed.

Or run `/add-plugin resumenext-cover-letter` in chat.

## MCP

```json
{
  "mcpServers": {
    "resumenext-cover-letter": {
      "type": "http",
      "url": "https://resumenext.io/api/grok/cover-letter/mcp"
    }
  }
}
```

The plugin connects to the ResumeNext MCP server at `https://resumenext.io/api/grok/cover-letter/mcp` (Streamable HTTP). Auth: none. The tools work without an account; opening a link creates a temporary ResumeNext account for the document, so the work is still there when you come back.

## Tools

| Tool | What it does |
|---|---|
| `score_cover_letter` | Deterministic score out of 100 with pass or fix for each check. Read-only, stores nothing. |
| `find_cover_letter_examples` | Up to two complete example letters for a role, with writing tips and a link to each example's page. Read-only. |
| `prepare_cover_letter_editor` | Private link, valid 7 days, that opens the ResumeNext cover letter editor with the letter loaded, plus the same review. Stores the letter for the link. |

## Skill

`skills/resumenext-cover-letter/SKILL.md` tells the agent when to use the tools and in which order.

## Example prompts

- "Score my cover letter for a Marketing Manager role at Northline."
- "Show me example cover letters for a nurse."
- "Open this cover letter in the ResumeNext editor."

## Pricing

The plugin and its tools are free and need no account. Editing the letter in ResumeNext and saving it as PDF, DOCX or TXT is free; on the free plan the file carries a ResumeNext watermark, which ResumeNext Pro removes ($1.95 for 3 days, then $14.95 a month until you cancel, https://resumenext.io/pricing).

## Data and privacy

Read-only tools process the text the agent sends and store nothing. A tool that creates a link stores the document you asked to open, for 7 days; opening the link saves it in your ResumeNext account or in a temporary account created for it. The plugin has no hooks or local scripts, calls no AI model, and receives only the text passed to a tool.

## Docs

- Documentation: https://resumenext.io/mcp#cover-letter
- Privacy policy: https://resumenext.io/privacy
- Terms of service: https://resumenext.io/terms
- Support: support@resumenext.io

ResumeNext is not affiliated with Cursor, Anysphere or LinkedIn.

## License

MIT
