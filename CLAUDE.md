# Version Coupling

The `mcp.json` in this repo pins to a specific tag of `webframp/swamp-mcp-server` via the GitHub raw URL. When updating the MCP server version:

1. Tag and push the new version in `webframp/swamp-mcp-server`
2. Update the tag in `mcp.json` here to match
3. Commit with message: `Bump swamp-mcp-server to vX.Y.Z`

The URL pattern is:
```
https://raw.githubusercontent.com/webframp/swamp-mcp-server/v{VERSION}/src/main.ts
```

Current pinned version: **v0.1.0**

Never update `mcp.json` to reference a tag that doesn't exist yet.
