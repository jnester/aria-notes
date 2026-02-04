# Fix Linear MCP Auth

## Correct Command
```bash
npx -y mcp-remote https://mcp.linear.app/sse
```

**NOT:**
```bash
npx -y mcp-remote https://mcp.linear.app/mcp
```

## With Custom Port
```bash
npx -y mcp-remote https://mcp.linear.app/sse 9999
```

## Note
Cache may need to be cleared first (ask agent to help locate and clear).

## Cross-Platform Auth
Authenticating on the Windows side also authenticates the Linux MCP server. Copy the auth from Windows to Linux if Linux isn't picking up the authentication.
