# Notion Workflows

Core workflows that power the CLI commands.

## Workflow: capture
- Parse input into a short title and details
- Create Task with Status = Backlog

## Workflow: process
- Query Tasks where Status = Backlog
- For each task, classify and link Project/Area
- If it belongs to a new Project or Resource, create it and link back

## Workflow: plan-day
- Pull due/overdue tasks and priority items
- Select 3-7 tasks for Today
- Record Today list in a Resources note if desired

## Workflow: plan-week
- Review Projects and upcoming dates
- Establish 1-3 outcomes per area
- Capture risks and dependencies

## Workflow: checkout
- Mark completed tasks
- Roll over incomplete items
- Capture blockers and notes
