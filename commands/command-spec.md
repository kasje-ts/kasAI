# CLI Command Spec (Codex)

Minimal CLI command set for Codex in Cursor.
Commands are prompts executed with the Notion MCP server.

## Conventions
- `kasai <command> [args]`
- CLI input is natural language.
- DB IDs and properties are in `config/notion.json`.

## Commands
See `commands/cli-templates.md` for CLI templates and examples.
### capture
Create a new Task with minimal required fields.

Input:
- Freeform text
- Optional hints like `due`, `priority`, `project`, `area`

Behavior:
- Create Task in Tasks DB
- Default `Status = Inbox` (if available)
- Store raw text in `Description` if unclear

### process
Process inbox tasks and attach structure.

Behavior:
- Query Tasks where `Status = Inbox`
- For each, classify and update fields
- Link to Project/Area when possible
- Convert to Project/Resource when needed

### plan-day
Create a Today list and daily plan.

Behavior:
- Pull due/overdue + priority tasks
- Select 3-7 focus tasks
- Optionally write a daily plan doc in Resources

### plan-week
Review upcoming week.

Behavior:
- Review active Projects
- Set weekly outcomes
- Identify risks, dependencies, and key milestones

### checkout
End-of-day closeout.

Behavior:
- Mark completed tasks
- Roll over unfinished items
- Capture blockers
- Set reminders for tomorrow

### review-project
Refresh a Project.

Behavior:
- Check Progress/Status
- Ensure next actions exist
- Update notes in Resources

## Notes
- CLI is prompt-driven in Cursor/Codex.
- Commands will evolve.
