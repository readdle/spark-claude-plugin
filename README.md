# Spark for Claude

Give Claude access to [Spark](https://sparkmailapp.com) - read, draft, triage, and act on your email, calendars, meetings, and contacts. The Spark plugin bundles the Spark MCP tools with the `use-spark` skill and a set of recipes and personas: step-by-step workflows such as `/spark:recipe-morning-standup` or `/spark:recipe-inbox-zero`.

What Claude can do:

- Search and browse your emails across all connected accounts
- Read full threads with bodies and attachments
- Read individual attachment contents directly (images, PDFs, text files)
- List folders and shared inboxes
- Look up contacts
- Check calendar events and find free time slots for scheduling
- Review meeting transcripts, summaries, and notes
- Show team info, members, and assignments
- Compose drafts - new messages, replies, forwards, with attachments
- Post team chat comments on shared threads
- Triage messages - archive, pin, snooze, move, label, mark as done, share with team, assign and delegate
- Reclassify smart categories (Priority, People, Notifications, Newsletters)
- Manage contacts - block/accept, change category, mark important/primary, toggle auto-summary

## Requirements

- [Spark Desktop](https://sparkmailapp.com) on macOS or Windows, signed in to at least one account.
- Spark CLI enabled: in Spark, go to **Settings → AI Agents → Spark CLI Setup** and follow the prompts.
- Per-account access levels - `read-only`, `triage` (everything in read-only plus drafts, comments, and email/contact actions), or `send` (everything in triage plus sending mail and calendar invitations) - configured in **Settings → AI Agents → Access**. Recipes and personas declare the level they need; running one against an account with insufficient access returns an error explaining how to upgrade.

## What the plugin runs

The plugin starts `spark mcp`, the MCP server built into the Spark CLI that Spark CLI Setup installs. Each tool call runs the matching `spark` command against your running Spark Desktop. The plugin ships no code of its own. Tool results are returned to Claude as part of your conversation; the plugin itself sends nothing anywhere else.

## Privacy Policy

The plugin is a local bridge between Claude and Spark Desktop on your computer - it does not collect or transmit data on its own, so use of it is governed by Spark's official privacy policy: [https://sparkmailapp.com/privacy](https://sparkmailapp.com/privacy).

## License

[MIT](LICENSE) © Spark Mail Limited
