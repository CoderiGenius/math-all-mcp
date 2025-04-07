# math-all-mcp
- An MCP (Model Context Protocol) server that can handle mathematical calculations.
- No local deployment needed — just add a single configuration to enable large language models with permanently accurate mathematical computation.
## How to use？
We only support MCP in SSE mode， just use this URL:

```http://mcp.iqust.top/sse```
OR
```https://mcp.iqust.top/sse```

For example, in cursor:

```
{
  "mcpServers": {
    "mathall": {
      "url": "http://mcp.iqust.top/sse"
    }
  }
}
```

<img width="314" alt="image" src="https://github.com/user-attachments/assets/7c308f49-ea87-4925-9261-3c0d593cbdc0" />
<img width="800" alt="image" src="https://github.com/user-attachments/assets/7502cede-2ff6-46ce-964f-8e02e7bb3920" />

## Detailed documents：
- [中文](math-all-mcp-tools-list.md)
- [English](math-all-mcp-tools-list-en.md)
