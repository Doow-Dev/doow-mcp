# Doow MCP

Connect AI clients to Doow's organization, spend, and operations workflows through the Model Context Protocol (MCP).

Doow MCP is a hosted, OAuth-protected remote MCP server. This repository is a hosted integration and documentation package, not a runnable local MCP server, and it does not expose the private Doow API source code. Access requires a Doow account and organization authorization through OAuth.

## Connect

- **MCP endpoint:** `https://mcp.doow.co/mcp`
- **Transport:** Streamable HTTP
- **OAuth issuer:** `https://mcp.doow.co`
- **Scopes:** `mcp:read`, `mcp:write`

Use an MCP client that supports remote Streamable HTTP servers and OAuth authorization-code flow with public-client PKCE (S256). Doow MCP uses bearer authorization and returns an `mcp-session-id` for session-aware requests.

OAuth endpoints:

- **Authorization:** `https://mcp.doow.co/oauth/authorize`
- **Token:** `https://mcp.doow.co/oauth/token`
- **Client registration:** `https://mcp.doow.co/oauth/register`
- **Revocation:** `https://mcp.doow.co/oauth/revoke`

OAuth metadata is available at:

- [`/.well-known/oauth-authorization-server`](https://mcp.doow.co/.well-known/oauth-authorization-server)
- [`/.well-known/oauth-protected-resource`](https://mcp.doow.co/.well-known/oauth-protected-resource)

## Capabilities

The server exposes organization-scoped tools for Doow workflows, including:

- Organization, team, contract, and license operations
- Cards, expenses, dashboards, insights, and reporting
- Integrations and connected app workflows
- Search and read/query operations

The current production catalog contains 85 tools: 44 read/query tools and 41 write/mutation tools. Sensitive write operations can require explicit confirmation or elicitation.

## Security

Access is authorized for the connected organization. Doow MCP supports separate read and write scopes, rate limits, session lifecycle controls, and audit metadata. Requests without bearer authorization are rejected.

Do not put Doow credentials in client configuration files or issue credentials to untrusted applications.

## Health

- [Health check](https://mcp.doow.co/mcp/health)
- [Readiness check](https://mcp.doow.co/mcp/ready)

## Support

For support, email [support@doow.co](mailto:support@doow.co).

## License

This repository contains integration documentation and metadata for the hosted Doow MCP service. The hosted service is provided by Doow and is not licensed for redistribution as a local server.
