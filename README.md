# kasAI

Minimal Codex CLI command set for Notion (PARA). Uses the Notion MCP server.

## What This Repo Is For
- Define Codex slash commands.
- Store Notion database config.
- Keep prompt workflows in version control.

## Notion Databases
IDs and properties are in `config/notion.json`.

- Tasks: `2e09b6c7-1158-811f-92c2-000b4f6a3164`
- Projects: `2e09b6c7-1158-81da-93c4-000beb315d43`
- Areas: `2e09b6c7-1158-8196-81f8-000b121fc4f3`
- Resources: `2e09b6c7-1158-81ee-bb15-000b2002040f`
- Inbox (Daily Notes): `2e19b6c7-1158-8092-b572-000b4846107d`

## Status Values
- Tasks: Backlog, In Progress, Paused, Completed, Delegated
- Projects: Inbox, Planned, In Progress, Completed
- Resources: Inbox, To Review, Reviewed
- Inbox: Not Started, In Progress, Processed

## Commands
All commands are Codex prompts mapped to Notion MCP calls.

- `startup`: Create or update today’s daily note. Show active tasks, overdue, and top backlog. Ask reflection questions.
- `capture`: Add a task to Backlog from quick input.
- `process`: Structure Backlog tasks and link Projects/Areas.
- `plan-day`: Build a focused list of 3–7 tasks.
- `plan-week`: Review Projects and set weekly outcomes.
- `checkout`: Mark completed tasks and append reflection to today’s daily note.
- `daily-review`: End‑of‑day review note in Inbox.
- `weekly-synthesis`: Weekly synthesis note in Inbox.
- `inbox-processor`: Process Backlog tasks and Resources Inbox/To Review.
- `recall`: Search Tasks/Projects/Resources.
- `edit`: Update items by name and fields.
- `review-project`: Refresh project status and next actions.
- `thinking-partner`: Ask questions first, track insights, surface connections.

## Key Files
- `config/notion.json`: Database IDs, properties, status values.
- `prompts/`: Full prompt definitions.
- `commands/`: CLI templates and examples.
- `templates/`: Daily and weekly plan templates.
- `SETUP.md`: Minimal setup steps.

## Usage
- Codex CLI slash commands live in `~/.codex/prompts/`.
- Start the day with `/startup`.
- End the day with `/checkout` and `/daily-review`.
- Weekly clean up with `/weekly-synthesis` and `/inbox-processor`.
