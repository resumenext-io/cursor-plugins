# Job Match & Resume Keyword Scanner - ResumeNext

Compare your resume with a job post: matched and missing keywords, coverage, a job-tailored ATS score, and an editable copy with the job attached. No sign-in.

Paste a resume and a job posting and the agent gets the posting's keywords that appear in the resume and the ones that are missing, how often each occurs on both sides, the coverage percentage and an ATS score for that job. Then it can open a copy of the resume in the ResumeNext editor with the job attached as its target, so the editor keeps scoring it against that posting.

Scores and letters come from fixed rules and templates on ResumeNext's servers: the same input always gives the same result.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Job Match & Resume Keyword Scanner - ResumeNext**.
3. Click **Install**. No sign-in is needed.

Or run `/add-plugin resumenext-job-match` in chat.

## MCP

```json
{
  "mcpServers": {
    "resumenext-job-match": {
      "type": "http",
      "url": "https://resumenext.io/api/grok/job-match/mcp"
    }
  }
}
```

The plugin connects to the ResumeNext MCP server at `https://resumenext.io/api/grok/job-match/mcp` (Streamable HTTP). Auth: none. The tools work without an account; opening a link creates a temporary ResumeNext account for the document, so the work is still there when you come back.

## Tools

| Tool | What it does |
|---|---|
| `match_resume_to_job` | Matched and missing keywords, counts on both sides, coverage percentage and a deterministic job-tailored ATS score with the issues to fix first. Read-only, stores nothing. |
| `prepare_tailored_resume` | Private link, valid 7 days, that opens the ResumeNext editor with the resume loaded and the job attached as its target. Stores the resume and the posting for the link. |

## Skill

`skills/resumenext-job-match/SKILL.md` tells the agent when to use the tools and in which order.

## Example prompts

- "Match my resume to this job and list the keywords I'm missing."
- "How well does my resume fit this Data Analyst posting?"
- "Open my resume tailored to this job in ResumeNext."

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1 for 3 days, then $29.95 a month until you cancel (https://resumenext.io/pricing).

## Data and privacy

Read-only tools process the text the agent sends and store nothing. A tool that creates a link stores the document you asked to open, for 7 days; opening the link saves it in your ResumeNext account or in a temporary account created for it. The plugin has no hooks or local scripts, calls no AI model, and receives only the text passed to a tool.

## Docs

- Documentation: https://resumenext.io/mcp#job-match
- Privacy policy: https://resumenext.io/privacy
- Terms of service: https://resumenext.io/terms
- Support: support@resumenext.io

ResumeNext is not affiliated with Cursor, Anysphere or LinkedIn.

## License

MIT
