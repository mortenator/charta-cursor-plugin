# Charta — Chart Generator for Cursor

> Generate presentation-quality charts from your AI agent. Waterfall, Mekko, bar, line, pie, and 9 more — returns SVG or PNG instantly.

## Install

**Option 1: Cursor Marketplace** *(coming soon)*
Search "Charta" in the Cursor plugin panel.

**Option 2: Manual (add to your Cursor MCP config)**

Open `.cursor/mcp.json` in your project root (or `~/Library/Application Support/Cursor/mcp.json` globally) and add:

```json
{
  "mcpServers": {
    "charta": {
      "command": "npx",
      "args": ["-y", "@charta/mcp"]
    }
  }
}
```

No install, no API key required for local SVG generation. Zero config.

## What it does

Once installed, your Cursor agent can generate charts on demand:

> *"Create a waterfall chart showing our ARR bridge from Q4 to Q1"*

```
generate_chart({
  type: "waterfall",
  data: [
    { label: "Q4 ARR",    value: 4200, isTotal: true },
    { label: "New Biz",   value: 980 },
    { label: "Expansion", value: 540 },
    { label: "Churn",     value: -310 },
    { label: "Q1 ARR",    value: 5410, isTotal: true }
  ]
})
// → returns { svg: "...", chartId: "chart_abc123" }
```

## MCP Tools

| Tool | What it does |
|------|-------------|
| `generate_chart` | Generate a chart — returns SVG + chartId |
| `list_chart_types` | All supported types with data shapes |
| `get_chart_schema` | JSON schema for a specific chart type |
| `save_chart` | Save chart to disk as SVG or PNG |
| `describe_chart` | Recommend the best chart type for your data |

## Supported chart types

waterfall · bar · grouped-bar · stacked-bar · line · area · pie · donut · scatter · bubble · gantt · mekko · radar · heatmap

## Links

- Website: https://getcharta.ai
- Developers: https://getcharta.ai/developers
- npm: https://www.npmjs.com/package/@charta/mcp
- GitHub (MCP): https://github.com/mortenator/charta-mcp

## License

MIT
