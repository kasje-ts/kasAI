# CLI Command Templates (Codex)

These templates map CLI input to Notion MCP calls.
DB IDs and properties are in `config/notion.json`.

## General Format
- Input: `kasai <command> <freeform text> [--flags]`
- Output: short summary + MCP actions

## Common Flags
- `--due YYYY-MM-DD`
- `--priority <value>`
- `--project "Project Name"`
- `--area "Area Name"`
- `--url <url>`
- `--dry-run`

## capture
Create a task.

Example inputs:
- `kasai capture draft Q1 roadmap --project "Growth" --due 2026-01-15 --priority High`
- `kasai capture follow up with legal about vendor contract`

MCP actions:
1. Create a page in Tasks DB
2. Set:
   - Name (short title)
   - Description (full input text)
   - Status = Backlog
   - Optional fields from flags

Output:
- Task name + link

## process
Structure items in Backlog.

Example inputs:
- `kasai process`
- `kasai process --limit 10`

MCP actions:
1. Query Tasks where Status = Backlog
2. For each, update Project/Area, Priority, Due Date when clear
3. If not a task, convert to Project or Resource and link back

Output:
- Updated items + clarifications if needed

## plan-day
Build a daily plan.

Example inputs:
- `kasai plan-day`
- `kasai plan-day --hours 5 --focus "Hiring"`

MCP actions:
1. Query Tasks with due/overdue + high priority
2. Select 3-7 tasks (prefer In Progress, then Backlog)
3. Optionally create a Resource note using `templates/daily-plan.md`

Output:
- Today list + optional note link

## plan-week
Create weekly outcomes.

Example inputs:
- `kasai plan-week`
- `kasai plan-week --focus "Customer research"`

MCP actions:
1. Query Projects where Status in (Inbox, Planned, In Progress)
2. Identify top outcomes and milestones
3. Optionally create a Resource note using `templates/weekly-plan.md`

Output:
- Weekly outcomes + optional note link

## checkout
End-of-day closeout.

Example inputs:
- `kasai checkout "shipped onboarding copy" --blockers "waiting on design"`

MCP actions:
1. Mark completed tasks as Completed
2. Move remaining In Progress tasks to Paused or Backlog if needed
3. Capture blockers and wins in a Resource note

Output:
- Completed count + rolled-over items

## daily-review
End-of-day review note.

Example inputs:
- `kasai daily-review`

MCP actions:
1. Query Tasks completed today
2. Query Tasks edited today
3. Create or update a Resource note

Output:
- Accomplished + progress + insights + tomorrow focus

## review-project
Refresh a project.

Example inputs:
- `kasai review-project "Website Redesign"`

MCP actions:
1. Find project by Name
2. Update Progress, Status, and next actions
3. Link new tasks if required

Output:
- Status summary + next actions

## recall
Recall info across databases.

Example inputs:
- `kasai recall "vendor contract"`
- `kasai recall --project "Website Redesign" --type resources`

MCP actions:
1. Search Tasks/Projects/Resources for matching text
2. Return top matches with context

Output:
- Matches + links

## weekly-synthesis
Weekly synthesis note.

Example inputs:
- `kasai weekly-synthesis`

MCP actions:
1. Query Tasks, Projects, Resources edited this week
2. Create a Resource note

Output:
- Themes + insights + project progress + next week

## inbox-processor
Process Backlog tasks and Resource inbox.

Example inputs:
- `kasai inbox-processor`

MCP actions:
1. Query Tasks where Status = Backlog
2. Query Resources where Status in (Inbox, To Review)
3. Update links and statuses

Output:
- Actions to take

## thinking-partner
Exploration mode with questions first.

Example inputs:
- `kasai thinking-partner "How should I approach Q2 planning?"`

MCP actions:
1. Search Tasks, Projects, Resources for related context

Output:
- Questions + insights + connections

## startup
Daily startup review.

Example inputs:
- `kasai startup`
- `kasai startup --focus \"Growth\" --hours 5`

MCP actions:
1. Query overdue Tasks and high priority Tasks
2. Query Projects with Status in (Inbox, Planned, In Progress)
3. Query Resources with Status in (Inbox, To Review)
4. Query Inbox daily note for today and summarize key points
5. Summarize focus for today and risks

Output:
- Focus items + overdue + active + backlog + projects + resources + reflection prompts

## edit
Update existing items.

Example inputs:
- `kasai edit task "follow up with legal" --status "In Progress" --due 2026-01-20`
- `kasai edit project "Website Redesign" --progress 45 --status "In Progress"`

MCP actions:
1. Find item by name (disambiguate if needed)
2. Update specified fields

Output:
- Confirmation + updated fields
