# DigiClick MCP plugins

Plugins and marketplace entries for **DigiClick Telephony** — a phone number
and a voice for your agent. Calls in and out, texts, voicemail, transfer and
hold, numbers, your own cloned voice. Plain MCP over HTTPS:
`https://app.digiclick.com/api/mcp`.

- Product: https://app.digiclick.com/mcp
- Developer docs: https://app.digiclick.com/mcp/docs
- Get a key: https://app.digiclick.com/mcp/console

## Grok Bot

Add this repository as a marketplace (Settings → Plugins → add marketplace):

```
https://github.com/DigiClickCorp/mcp-plugins
```

Install `digiclick-telephony` and set `DIGICLICK_API_KEY` to a key from the
console. The plugin ships the MCP server config and a skill that explains the
call loop to the agent.

## Any MCP client

```json
{ "mcpServers": { "telephony": {
  "url": "https://app.digiclick.com/api/mcp",
  "headers": { "Authorization": "Bearer dk_live_..." } } } }
```

Support: support@digiclick.com · Privacy: https://app.digiclick.com/mcp/privacy · Terms: https://app.digiclick.com/mcp/terms
