# Setup

## Requirements
- Notion account
- Notion MCP server enabled
- Codex in Cursor
- Git CLI tools

## Notion MCP
1. Enable the Notion MCP server in your Codex settings.
2. Ensure Codex can access your Notion workspace.
3. Open a test prompt and ask Codex to list your Notion databases.

## Repo
- Config lives in `config/notion.json`.
- Prompts live in `prompts/`.
- Command templates live in `commands/`.

## First Run
1. Open this repo in Cursor.
2. Use a command like `kasai capture ...`.
3. Confirm it creates a task in Notion.

## Troubleshooting
- If a command fails, verify database IDs and property names in `config/notion.json`.
