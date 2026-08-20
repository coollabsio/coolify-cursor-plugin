---
name: coolify
description: Use when working with a Coolify instance — list or inspect applications, servers, databases, services, deployments, and logs. Also use when the user mentions Coolify, self-hosted PaaS deploys, or Coolify Cloud.
---

# Coolify

Talk to the connected Coolify instance through the `coolify` MCP server.

## Before you start

- The instance must have MCP enabled.
- `COOLIFY_URL` is the instance origin with no trailing slash. The MCP URL is `${COOLIFY_URL}/mcp`.
- `COOLIFY_TOKEN` is a team-scoped API token. Tools are scoped to that team.
- If a tool fails with auth or 404 on `/mcp`, the usual causes are MCP disabled, wrong URL, or a token without access.

## What to do

- Prefer Coolify MCP tools over guessing dashboard click-paths.
- For deploys, logs, and resource lists, use the matching tools and paginate when the server says there is more.
- Do not print the API token. Do not invent resource UUIDs; look them up first.
- Treat write/deploy actions as consequential: confirm with the user before starting, stopping, or redeploying production resources.
