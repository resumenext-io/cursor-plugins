# Resume Bullet Point Checker & Action Verbs - ResumeNext

Check resume bullet points line by line for action verbs, numbers, first person and phrases to delete, and get action verbs by type of work. No sign-in.

Paste resume bullet points and the agent gets a check of every line: the opening word and whether it is an action verb, gerund openings and phrases to delete (Responsible for, Worked on, Helped with...), whether the line carries a number, first person, word count and what to change, plus the lines to rewrite first. It can also bring up action verbs for a type of work.

Scores and letters come from fixed rules and templates on ResumeNext's servers: the same input always gives the same result.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Resume Bullet Point Checker & Action Verbs - ResumeNext**.
3. Click **Install**. No sign-in is needed.

Or run `/add-plugin resumenext-resume-bullet-points` in chat.

## MCP

```json
{
  "mcpServers": {
    "resumenext-resume-bullet-points": {
      "type": "http",
      "url": "https://resumenext.io/api/grok/bullet-points/mcp"
    }
  }
}
```

The plugin connects to the ResumeNext MCP server at `https://resumenext.io/api/grok/bullet-points/mcp` (Streamable HTTP). Auth: none. The tools work without an account; opening a link creates a temporary ResumeNext account for the document, so the work is still there when you come back.

## Tools

| Tool | What it does |
|---|---|
| `check_resume_bullets` | Per-line check against ResumeNext's action verb guide and ATS line checks, totals, and the lines to rewrite first. Deterministic, stores nothing. |
| `find_action_verbs` | Action verbs for a type of work (leadership, building, process-improvement, analysis, finance, communication, sales, teaching, care), phrases to delete and rules for picking a verb. Read-only. |

## Skill

`skills/resumenext-resume-bullet-points/SKILL.md` tells the agent when to use the tools and in which order.

## Example prompts

- "Check these resume bullets and tell me which to rewrite first."
- "Give me action verbs for leadership."
- "Make these bullet points stronger without inventing numbers."

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1 for 7 days, then $29.99 a month until you cancel (https://resumenext.io/pricing).

## Data and privacy

Read-only tools process the text the agent sends and store nothing. A tool that creates a link stores the document you asked to open, for 7 days; opening the link saves it in your ResumeNext account or in a temporary account created for it. The plugin has no hooks or local scripts, calls no AI model, and receives only the text passed to a tool.

## Docs

- Documentation: https://resumenext.io/mcp#bullet-points
- Privacy policy: https://resumenext.io/privacy
- Terms of service: https://resumenext.io/terms
- Support: support@resumenext.io

ResumeNext is not affiliated with Cursor, Anysphere or LinkedIn.

## License

MIT
