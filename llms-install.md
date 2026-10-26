# Install Scento Perfume API (MCP server) in Cline

Scento Perfume API is a free, read-only remote MCP server with 1,400+ perfumes, 140+ houses and 400+ raw materials. No API key, no account, nothing to clone or build.

Add this to `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "scento-perfume-api": {
      "url": "https://www.scento.com/mcp",
      "type": "streamableHttp",
      "disabled": false
    }
  }
}
```

Prefer a local stdio proxy? Use `npx -y scento-perfume-api` instead:

```json
{
  "mcpServers": {
    "scento-perfume-api": {
      "command": "npx",
      "args": ["-y", "scento-perfume-api"],
      "disabled": false
    }
  }
}
```

Once connected, ask for a perfume's notes, similar scents, a side-by-side comparison, or a raw material portrait. Docs: https://www.scento.com/developers
