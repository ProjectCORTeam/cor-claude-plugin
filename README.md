# COR

COR connects Claude to your COR account. The plugin uses the remote server at https://mcp.projectcor.com/mcp. You sign in with OAuth to your COR account. Claude can read and write projects, tasks, messages, and time logs. Your COR role and permissions decide what Claude can see and change.

Manage your COR work from a conversation with Claude. Claude can look up projects and tasks, report on a project's health and hours, plan your week, comment on tasks, and log time, all through your own COR account.

## Connect your COR account

The plugin connects Claude to COR's remote MCP server at `https://mcp.projectcor.com/mcp`. You sign in with OAuth to your COR account, and the plugin itself holds no password or token. You need an active COR account at [cor.works](https://cor.works).

- In claude.ai and Cowork, add COR from the directory, then connect it from the plugin's Connectors tab and sign in to COR.
- On Team and Enterprise plans, an Owner adds the connector for the organization first. Each member then connects with their own COR account.
- In Claude Code, the plugin loads through your claude.ai account. Run `/mcp` to sign in to the `cor` server.

## Ask Claude

Ask in plain words. Claude picks the matching skill from its description. For example:

- "Log my hours from today's commits." Claude drafts a timesheet from your git history and logs hours only after you approve the draft.
- "How is project Acme Rebrand doing?" Claude reports health, hours against the estimate, overdue and stalled tasks, and upcoming leave. It changes nothing.
- "Triage my pending tasks for this week." Claude sorts your tasks by deadline and status and suggests what to start, who to follow up with, and what can wait.

In Claude Code, each skill also runs as a slash command, such as `/cor:triage-pending-tasks`. To see every skill, ask Claude which skills it has from plugins.

## What Claude can do in COR

Through the COR MCP server, Claude can read and write your COR projects, tasks, task messages, and time logs. It can also read clients, team members, and leave. Every action runs as you, and the server allows only what your COR role and permissions allow.

The plugin's skills show each change and wait for your yes before they log hours, post a task message, or update a task. A posted message can't be unsent, and an @mention notifies that person. Logged hours start as pending. The plugin can't approve, edit, or delete hours.

## Data

The plugin's files are Markdown, JSON, plain text, and one SVG logo. The only network destination is the COR MCP server.

- When you ask for COR work, Claude sends the requests it needs, and the data in them, to `https://mcp.projectcor.com/mcp`.
- To draft hours, Claude runs `git log` in your repository in Claude Code, or reads a log you paste in chat. Claude sends COR only the rows you approve, each with a task, a date, a duration, and an optional description.
- [COR's privacy policy](https://live.projectcor.com/legal/privacy-policy) explains how the COR MCP server stores your sign-in session and which services process usage data.

## Support

Email help@projectcor.com. The [COR MCP server documentation](https://developers.projectcor.com/ai-tools/mcp-server) lists the server's tools. Use of COR follows the [COR Terms of Service](https://live.projectcor.com/legal/terms-of-service).

## License

The license is MIT. See [LICENSE](LICENSE).
