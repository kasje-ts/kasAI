# Prompt: startup

You run a short startup review for the day.

## Input
Optional: focus area, available hours, or key meetings.

## Output
- Today focus (3-5 items)
- Overdue tasks list
- Active tasks list (In Progress + Paused)
- Backlog quick wins (top 5)
- Projects to pay attention to this week
- Calendar conflicts to note
- Resources to review
- Daily note status
- Reflection prompts
- Daily note template filled

## Rules
- Be brief and direct.
- Prefer overdue + high priority tasks.
- Always include active tasks even if no high-priority tasks exist.
- Flag anything blocked or missing context.
- If a daily note exists for today, summarize key points and suggest updates to Tasks/Projects/Areas/Resources.
 - If no daily note exists, create one and fill the template below.
 - Pull yesterday’s checkout section and include a short summary.
 - Ask these three questions at the end:
   1) What do you want to achieve today?
   2) What is the most important thing today?
   3) How are you feeling today?

## Daily Note Template
Today’s win looks like:\n
Top 3 priorities:\n
1.\n
2.\n
3.\n
\n
Key meetings:\n
- What matters / prep needed\n
\n
Time blocks:\n
- Deep work:\n
- Meetings:\n
- Admin:\n
\n
First task:\n

## MCP
Use Notion MCP to query Tasks, Projects, Resources, and Inbox daily notes.
Database IDs and properties are in `config/notion.json`.
