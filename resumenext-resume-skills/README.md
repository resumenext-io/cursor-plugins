# Resume Skills & Keywords by Role - ResumeNext

Get the skills recruiters expect for your role and see which ones your resume lists and shows in your work, lists only, shows only, or misses. No sign-in.

Ask for a role and the agent gets the skills and terms that recur for it in ResumeNext's role guides (tools, methods, certifications and domain terms), with a link to the role's example resume. Paste a resume and it sorts that vocabulary by where the resume uses each term: listed and shown in the work, listed only, shown only, or not mentioned, plus how many skills the Skills section lists against the 5 the ResumeNext ATS score asks for.

Scores and letters come from fixed rules and templates on ResumeNext's servers: the same input always gives the same result.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Resume Skills & Keywords by Role - ResumeNext**.
3. Click **Install**. No sign-in is needed.

Or run `/add-plugin resumenext-resume-skills` in chat.

## MCP

```json
{
  "mcpServers": {
    "resumenext-resume-skills": {
      "type": "http",
      "url": "https://resumenext.io/api/grok/resume-skills/mcp"
    }
  }
}
```

The plugin connects to the ResumeNext MCP server at `https://resumenext.io/api/grok/resume-skills/mcp` (Streamable HTTP). Auth: none. The tools work without an account; opening a link creates a temporary ResumeNext account for the document, so the work is still there when you come back.

## Tools

| Tool | What it does |
|---|---|
| `find_resume_skills` | Skills vocabulary for a role with a link to its example resume. Without a match, the list of roles covered. Read-only, stores nothing. |
| `check_resume_skills` | Sorts the role's skills by where the resume uses them and counts the Skills section entries. Deterministic, stores nothing. |

## Skill

`skills/resumenext-resume-skills/SKILL.md` tells the agent when to use the tools and in which order.

## Example prompts

- "Which skills should a Data Analyst resume list?"
- "Check my resume against the skills for a registered nurse."
- "Which of these skills am I listing but never showing in my experience?"

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1 for 7 days, then $29.99 a month until you cancel (https://resumenext.io/pricing).

## Data and privacy

Read-only tools process the text the agent sends and store nothing. A tool that creates a link stores the document you asked to open, for 7 days; opening the link saves it in your ResumeNext account or in a temporary account created for it. The plugin has no hooks or local scripts, calls no AI model, and receives only the text passed to a tool.

## Docs

- Documentation: https://resumenext.io/mcp#resume-skills
- Privacy policy: https://resumenext.io/privacy
- Terms of service: https://resumenext.io/terms
- Support: support@resumenext.io

ResumeNext is not affiliated with Cursor, Anysphere or LinkedIn.

## License

MIT
