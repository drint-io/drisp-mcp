# Installing the Drisp MCP server

Drisp is a hosted MCP server. There is nothing to clone, build or install, it needs no API key, and there is no sign-in.

1. Add this entry to the MCP settings file (for Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "drisp": {
      "type": "streamableHttp",
      "url": "https://drint.io/drisp/mcp"
    }
  }
}
```

2. Check that it works: call `list_devices`. It lists every device with the screenshot size that fills its screen exactly.

3. To make a mockup, call `device_mockup` with `device` (from `list_devices`) and the screenshot as `screenshot_url` (public https) or `screenshot_base64` (PNG, JPEG or WebP, up to 10 MB). It returns a PNG link.

Docs: https://drint.io/drisp
