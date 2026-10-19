# ATS Resume Checker & Resume Builder - ResumeNext

Get your resume's ATS score out of 100, the issues to fix first, and a link that opens it in the ResumeNext resume builder. No sign-in.

Paste a resume and the agent gets a reproducible ATS score out of 100, a letter grade, the score by area and the issues to fix first, computed by fixed rules rather than guessed. Improve the resume in the chat, score it again, then open the final version in the ResumeNext editor: it arrives already loaded, ready to format with an ATS-safe template and export.

Scores and letters come from fixed rules and templates on ResumeNext's servers: the same input always gives the same result.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **ATS Resume Checker & Resume Builder - ResumeNext**.
3. Click **Install**. No sign-in is needed.

Or run `/add-plugin resumenext-ats-resume-checker` in chat.

## MCP

```json
{
  "mcpServers": {
    "resumenext-ats-resume-checker": {
      "type": "http",
      "url": "https://resumenext.io/api/grok/resume/mcp"
    }
  }
}
```

The plugin connects to the ResumeNext MCP server at `https://resumenext.io/api/grok/resume/mcp` (Streamable HTTP). Auth: none. The tools work without an account; opening a link creates a temporary ResumeNext account for the document, so the work is still there when you come back.

## Tools

| Tool | What it does |
|---|---|
| `analyze_resume` | Deterministic ATS score out of 100, grade, score by area and issues to fix first; keyword coverage when a job description is given. Read-only, stores nothing. |
| `prepare_resume_editor` | Private link, valid 7 days, that opens the ResumeNext editor with the resume loaded, plus the same ATS analysis. Stores the resume for the link. |

## Skill

`skills/resumenext-ats-resume-checker/SKILL.md` tells the agent when to use the tools and in which order.

## Example prompts

- "Check my resume for ATS problems and tell me what to fix first."
- "Score this resume for a Marketing Manager role."
- "My resume is ready: open it in the ResumeNext editor."

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1 for 3 days, then $29.95 a month until you cancel (https://resumenext.io/pricing).

## Data and privacy

Read-only tools process the text the agent sends and store nothing. A tool that creates a link stores the document you asked to open, for 7 days; opening the link saves it in your ResumeNext account or in a temporary account created for it. The plugin has no hooks or local scripts, calls no AI model, and receives only the text passed to a tool.

## Docs

- Documentation: https://resumenext.io/mcp#resume
- Privacy policy: https://resumenext.io/privacy
- Terms of service: https://resumenext.io/terms
- Support: support@resumenext.io

ResumeNext is not affiliated with Cursor, Anysphere or LinkedIn.

## License

MIT
