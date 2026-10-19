# LinkedIn Profile Review & Resume Converter - ResumeNext

Score your LinkedIn profile out of 100 for the role you want, see what to fix first, and turn it into a resume that opens in the ResumeNext editor. No sign-in.

Paste the text of a LinkedIn profile, or the text of LinkedIn's Save to PDF export, and the agent gets a reproducible score out of 100 with findings for headline, About, experience, keywords and completeness, the strengths and the priorities to fix. It can then turn the profile into a resume that opens in the ResumeNext editor, ready to format with a template and export. The plugin does not connect to LinkedIn: it only reads the text you paste.

Scores and letters come from fixed rules and templates on ResumeNext's servers: the same input always gives the same result.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **LinkedIn Profile Review & Resume Converter - ResumeNext**.
3. Click **Install**. No sign-in is needed.

Or run `/add-plugin resumenext-linkedin-resume` in chat.

## MCP

```json
{
  "mcpServers": {
    "resumenext-linkedin-resume": {
      "type": "http",
      "url": "https://resumenext.io/api/grok/linkedin/mcp"
    }
  }
}
```

The plugin connects to the ResumeNext MCP server at `https://resumenext.io/api/grok/linkedin/mcp` (Streamable HTTP). Auth: none. The tools work without an account; opening a link creates a temporary ResumeNext account for the document, so the work is still there when you come back.

## Tools

| Tool | What it does |
|---|---|
| `review_linkedin_profile` | Deterministic score out of 100, findings by section, strengths and priorities to fix. Read-only, stores nothing. |
| `convert_linkedin_to_resume` | Turns the profile into a resume and returns a private link, valid 7 days, that opens it in the ResumeNext editor, plus its ATS analysis. Stores the profile text for the link. |

## Skill

`skills/resumenext-linkedin-resume/SKILL.md` tells the agent when to use the tools and in which order.

## Example prompts

- "Review my LinkedIn profile for a Marketing Manager role."
- "What should I fix first on my LinkedIn profile?"
- "Turn my LinkedIn profile into a resume."

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1.95 for 3 days, then $14.95 a month until you cancel (https://resumenext.io/pricing).

## Data and privacy

Read-only tools process the text the agent sends and store nothing. A tool that creates a link stores the document you asked to open, for 7 days; opening the link saves it in your ResumeNext account or in a temporary account created for it. The plugin has no hooks or local scripts, calls no AI model, and receives only the text passed to a tool.

## Docs

- Documentation: https://resumenext.io/mcp#linkedin
- Privacy policy: https://resumenext.io/privacy
- Terms of service: https://resumenext.io/terms
- Support: support@resumenext.io

ResumeNext is not affiliated with Cursor, Anysphere or LinkedIn.

## License

MIT
