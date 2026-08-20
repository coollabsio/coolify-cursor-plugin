# Coolify Cursor plugin

Official [Cursor](https://cursor.com) / Grok Bot plugin for [Coolify](https://coolify.io).

It connects to Coolify's built-in Streamable HTTP MCP server at `https://<your-instance>/mcp` so agents can inspect servers, apps, databases, services, deploys, and logs.

## Prerequisites

1. Coolify with MCP enabled (root token: `POST /api/v1/mcp/enable`, or the instance Settings toggle). Docs: [MCP](https://coolify.io/docs/integrations/mcp) and [next docs](https://next.coolify.io/docs/integrations/mcp).
2. A **team-scoped API token** from **Keys & Tokens → API tokens**.

## Install (after marketplace listing)

1. In Cursor: Customize / Marketplace → search **Coolify** → Add.
2. In Grok Bot: sidebar account → **Settings → Plugins** → search **Coolify** → Add.
3. Set:
   - `COOLIFY_URL` — instance URL, no trailing slash (`https://coolify.example.com` or `https://app.coolify.io`)
   - `COOLIFY_TOKEN` — the API token

Until it is listed, add the same MCP config locally (Cursor `mcp.json`):

```json
{
  "mcpServers": {
    "coolify": {
      "url": "https://YOUR-INSTANCE/mcp",
      "headers": {
        "Authorization": "Bearer YOUR-TOKEN"
      }
    }
  }
}
```

## Publish to the Cursor marketplace

This repo is the plugin. Submit it at [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish). Cursor reviews listings; after approval it appears in Cursor and in Grok Bot's plugin catalog.

## Layout

- `.cursor-plugin/plugin.json` — manifest and install variables
- `mcp.json` — remote Coolify MCP (`${COOLIFY_URL}/mcp`)
- `skills/coolify/SKILL.md` — when to use Coolify

No secrets belong in this repo. Users set `COOLIFY_URL` and `COOLIFY_TOKEN` at install time.
