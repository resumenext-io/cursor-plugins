# Resignation Letter Generator - ResumeNext

Get a resignation letter in a standard, formal or grateful style from your company and last day, ready to edit and save as PDF, DOCX or TXT in ResumeNext. No sign-in.

Give the company and your last day and the agent gets a complete resignation letter in one of three styles: standard (professional and neutral), formal (short, on the record, notice-period wording) or grateful (warm and personal). The letter comes with a link that opens it in ResumeNext, ready to edit and save as PDF, DOCX or TXT.

Scores and letters come from fixed rules and templates on ResumeNext's servers: the same input always gives the same result.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Resignation Letter Generator - ResumeNext**.
3. Click **Install**. No sign-in is needed.

Or run `/add-plugin resumenext-resignation-letter` in chat.

## MCP

```json
{
  "mcpServers": {
    "resumenext-resignation-letter": {
      "type": "http",
      "url": "https://resumenext.io/api/grok/resignation-letter/mcp"
    }
  }
}
```

The plugin connects to the ResumeNext MCP server at `https://resumenext.io/api/grok/resignation-letter/mcp` (Streamable HTTP). Auth: none. The tools work without an account; opening a link creates a temporary ResumeNext account for the document, so the work is still there when you come back.

## Tools

| Tool | What it does |
|---|---|
| `write_resignation_letter` | Complete letter text in the chosen style and a link that opens it in ResumeNext to edit and save. Template-based and deterministic, stores nothing. |

## Skill

`skills/resumenext-resignation-letter/SKILL.md` tells the agent when to use the tools and in which order.

## Example prompts

- "Write my resignation letter: company Northline, last day November 14, grateful style."
- "I need a formal resignation letter for HR, my last day is March 14, 2026."
- "Draft a short resignation letter to my manager Dana."

## Pricing

The plugin and its tools are free and need no account. Editing the letter in ResumeNext and saving it as PDF, DOCX or TXT is free; on the free plan the file carries a ResumeNext watermark, which ResumeNext Pro removes ($1.95 for 3 days, then $14.95 a month until you cancel, https://resumenext.io/pricing).

## Data and privacy

Read-only tools process the text the agent sends and store nothing. A tool that creates a link stores the document you asked to open, for 7 days; opening the link saves it in your ResumeNext account or in a temporary account created for it. The plugin has no hooks or local scripts, calls no AI model, and receives only the text passed to a tool.

## Docs

- Documentation: https://resumenext.io/mcp#resignation-letter
- Privacy policy: https://resumenext.io/privacy
- Terms of service: https://resumenext.io/terms
- Support: support@resumenext.io

ResumeNext is not affiliated with Cursor, Anysphere or LinkedIn.

## License

MIT
