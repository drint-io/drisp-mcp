# Drisp MCP — 3D device mockups for app and website screenshots

[![AllMCPs Verified](https://allmcps.com/api/badge/drisp)](https://allmcps.com/mcp/drisp?verify=48c7354b-71af-48d3-be6f-d1abe111ac9e)

**Drisp** puts a screenshot of an app or a website on a device mockup and gives back a PNG. The devices are drawn in 3D with real glass and light by Drint's render engine: every iPhone from the 12 to the 18 Pro, iPads, a MacBook, Apple Watch, a Galaxy phone, a laptop and a monitor — about 100 devices.

This repository holds the setup files for the **hosted** Drisp MCP server. There is nothing to install or run:

```
https://drint.io/drisp/mcp
```

- Transport: Streamable HTTP
- Sign-in: optional. Without it, pictures are up to 1024 px with a light watermark grid, about 20 an hour per address. Ask for a clean picture (`clean: true`) or a size above 1024 and your app asks you to sign in to Drint (OAuth, nothing to paste): a [Drisp Pro](https://drint.io/drisp/pricing) account gets clean pictures up to 2048 px, 60 an hour.
- Website: [drint.io/drisp](https://drint.io/drisp)

## Tools

| Tool | What it does |
|---|---|
| `list_devices` | The devices Drisp can draw, each with the screenshot size in pixels that fills its screen exactly, and its page on drint.io |
| `device_mockup` | A screenshot (public https link, or base64 PNG / JPEG / WebP up to 10 MB) on one device, returned as a PNG link kept for an hour. Options: `size` (512, 1024; 1536 and 2048 with Drisp Pro), `clean` (Drisp Pro), `background` ("transparent" or a colour), `frame` colour |

## Connect

### Claude (claude.ai, Claude Desktop)

Settings → Connectors → **Add custom connector** → URL `https://drint.io/drisp/mcp`.

### Claude Code

```bash
claude mcp add --transport http drisp https://drint.io/drisp/mcp
```

Or install it as a plugin from this repository:

```
/plugin marketplace add drint-io/drisp-mcp
/plugin install drisp@drisp
```

### ChatGPT

Settings → Apps & Connectors → Advanced → Developer mode → **Create** → MCP server URL `https://drint.io/drisp/mcp`, no authentication.

### Cursor

Add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "drisp": { "url": "https://drint.io/drisp/mcp" }
  }
}
```

### VS Code (GitHub Copilot)

Command Palette → **MCP: Add Server** → HTTP → `https://drint.io/drisp/mcp`. Or add to `.vscode/mcp.json`:

```json
{
  "servers": {
    "drisp": { "type": "http", "url": "https://drint.io/drisp/mcp" }
  }
}
```

### Gemini CLI

```bash
gemini extensions install https://github.com/drint-io/drisp-mcp
```

### Codex CLI

Add to `~/.codex/config.toml`:

```toml
[mcp_servers.drisp]
url = "https://drint.io/drisp/mcp"
```

### Windsurf, Cline, Kiro, goose and other clients

Use any "remote / Streamable HTTP server" option with the URL `https://drint.io/drisp/mcp`. No headers and no key are needed.
## Try it

- "Put this screenshot of my app on an iPhone 17 Pro." (attach or link the screenshot)
- "Which screenshot size fills an iPad Air 13 screen exactly?"
- "Make a MacBook mockup of https://example.com/screenshot.png"

## Links

- Drisp: https://drint.io/drisp
- Support: support@drint.io
- Privacy Policy: https://drint.io/privacy (the picture link expires after an hour)
- Drint (packaging mockups and dielines) and Drict (label-law checks) have their own MCP servers: [drint-io/drint-mcp](https://github.com/drint-io/drint-mcp), [drint-io/drict-mcp](https://github.com/drint-io/drict-mcp)

## License

The files in this repository are MIT-licensed. The drint.io service follows the [Drint Terms](https://drint.io/terms).
