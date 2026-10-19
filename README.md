# ResumeNext plugins for Cursor

Resume, cover letter and job application tools for Cursor agents, one plugin per use case. Each plugin bundles a skill and a remote ResumeNext MCP server. No account or sign-in is needed to use the tools.

| Plugin | What you get | MCP server |
|---|---|---|
| [`resumenext-ats-resume-checker`](./resumenext-ats-resume-checker) | Get your resume's ATS score out of 100, the issues to fix first, and a link that opens it in the ResumeNext resume builder. | `https://resumenext.io/api/grok/resume/mcp` |
| [`resumenext-job-match`](./resumenext-job-match) | Compare your resume with a job post: matched and missing keywords, coverage, a job-tailored ATS score, and an editable copy with the job attached. | `https://resumenext.io/api/grok/job-match/mcp` |
| [`resumenext-cover-letter`](./resumenext-cover-letter) | Score your cover letter out of 100 against a fixed checklist, read example letters for your role, and open the final letter in the ResumeNext cover letter editor. | `https://resumenext.io/api/grok/cover-letter/mcp` |
| [`resumenext-resignation-letter`](./resumenext-resignation-letter) | Get a resignation letter in a standard, formal or grateful style from your company and last day, ready to edit and save as PDF, DOCX or TXT in ResumeNext. | `https://resumenext.io/api/grok/resignation-letter/mcp` |
| [`resumenext-linkedin-resume`](./resumenext-linkedin-resume) | Score your LinkedIn profile out of 100 for the role you want, see what to fix first, and turn it into a resume that opens in the ResumeNext editor. | `https://resumenext.io/api/grok/linkedin/mcp` |
| [`resumenext-resume-examples`](./resumenext-resume-examples) | Find resume examples for your role and the right resume template for your profile, each opening in the ResumeNext editor as a starting point. | `https://resumenext.io/api/grok/resume-examples/mcp` |
| [`resumenext-resume-bullet-points`](./resumenext-resume-bullet-points) | Check resume bullet points line by line for action verbs, numbers, first person and phrases to delete, and get action verbs by type of work. | `https://resumenext.io/api/grok/bullet-points/mcp` |
| [`resumenext-resume-skills`](./resumenext-resume-skills) | Get the skills recruiters expect for your role and see which ones your resume lists and shows in your work, lists only, shows only, or misses. | `https://resumenext.io/api/grok/resume-skills/mcp` |

## Install

Open **Cursor Settings → Plugins**, search for **ResumeNext** and install the plugins you need, or run `/add-plugin <plugin-name>` in chat.

## Test locally

Copy a plugin folder (not a symlink) to `~/.cursor/plugins/local/<plugin-name>`, then restart Cursor or run **Developer: Reload Window**, and check the skill and MCP server under **Customize**.

## Pricing

The plugin and its tools are free and need no account. Building and editing a resume in ResumeNext is free. Downloading the finished resume as PDF or Word needs ResumeNext Pro: $1 for 3 days, then $29.95 a month until you cancel (https://resumenext.io/pricing).

## Data and privacy

Read-only tools process the text the agent sends and store nothing. A tool that creates a link stores the document you asked to open, for 7 days; opening the link saves it in your ResumeNext account or in a temporary account created for it. The plugin has no hooks or local scripts, calls no AI model, and receives only the text passed to a tool.

Privacy policy: https://resumenext.io/privacy · Terms: https://resumenext.io/terms · Support: support@resumenext.io

## License

MIT, see [LICENSE](./LICENSE).
