# Resume Examples & Templates - ResumeNext

Find resume examples for your role and the right resume template for your profile, each opening in the ResumeNext editor as a starting point. No sign-in.

Ask for a role and the agent gets up to three resume examples with headline, summary, experience bullets and skills, each with a link to its page and a link that opens it in the ResumeNext editor as a starting point. It can also list the resume templates, marked ATS-safe or visual, narrowed to an audience: professional, executive, tech, creative, student or healthcare.

Scores and letters come from fixed rules and templates on ResumeNext's servers: the same input always gives the same result.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Resume Examples & Templates - ResumeNext**.
3. Click **Install**. No sign-in is needed.

Or run `/add-plugin resumenext-resume-examples` in chat.

## MCP

```json
{
  "mcpServers": {
    "resumenext-resume-examples": {
      "type": "http",
      "url": "https://resumenext.io/api/grok/resume-examples/mcp"
    }
  }
}
```

The plugin connects to the ResumeNext MCP server at `https://resumenext.io/api/grok/resume-examples/mcp` (Streamable HTTP). Auth: none. The tools work without an account; opening a link creates a temporary ResumeNext account for the document, so the work is still there when you come back.

## Tools

| Tool | What it does |
|---|---|
| `find_resume_examples` | Up to three examples for a role, with links to the example page and to the editor. Without a match, the list of roles covered. Read-only. |
| `list_resume_templates` | Resume templates with layout type (ATS-safe or visual), description, who it suits and a link that opens a new resume in it. Read-only. |

## Skill

`skills/resumenext-resume-examples/SKILL.md` tells the agent when to use the tools and in which order.

## Example prompts

- "Show me resume examples for a software engineer."
- "Which resume template fits a student?"
- "I need an ATS-safe resume template for healthcare."

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1.95 for 3 days, then $14.95 a month until you cancel (https://resumenext.io/pricing).

## Data and privacy

Read-only tools process the text the agent sends and store nothing. A tool that creates a link stores the document you asked to open, for 7 days; opening the link saves it in your ResumeNext account or in a temporary account created for it. The plugin has no hooks or local scripts, calls no AI model, and receives only the text passed to a tool.

## Docs

- Documentation: https://resumenext.io/mcp#resume-examples
- Privacy policy: https://resumenext.io/privacy
- Terms of service: https://resumenext.io/terms
- Support: support@resumenext.io

ResumeNext is not affiliated with Cursor, Anysphere or LinkedIn.

## License

MIT
