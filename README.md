# Uxia MCP

<img src="assets/uxia-logo.svg" alt="Uxia" width="64" />

Connect your AI assistant to [Uxia](https://uxia.app) for AI user research. This repository contains the Cursor plugin configuration and connection instructions for Uxia's hosted MCP service.

**Remote endpoint:** `https://platform.uxia.app/api/mcp-v2/mcp`

**Transport:** Streamable HTTP

**Authentication:** OAuth with PKCE

## Requirements

You need a Uxia account with access to a workspace and a client that supports remote MCP and OAuth. Your account's permissions, subscription and credits apply. Actions such as generating testers or launching research may consume credits. Review launch costs before approving a launch.

## Connect in Cursor

Add the following entry to your existing `.cursor/mcp.json` in a project, or to `~/.cursor/mcp.json` for your user. Merge it with any existing servers:

```json
{
  "mcpServers": {
    "uxia": {
      "url": "https://platform.uxia.app/api/mcp-v2/mcp"
    }
  }
}
```

Open Cursor's MCP settings and connect Uxia. Complete the browser sign-in and authorization flow, then return to Cursor. The package also includes `.cursor-plugin/plugin.json` and `mcp.json` for Cursor plugin distribution. Marketplace availability depends on Cursor's review; this repository does not indicate an approved listing.

## Connect in Claude and other clients

In Claude's connector settings, add a custom remote connector using the endpoint above and complete authorization. Custom connector availability depends on your Claude plan and your organization's settings. Other OAuth-capable MCP clients can use the same URL.

Choose the **remote connector/server** option in directories that distinguish it from downloadable server software. No local server, npm package, API-key entry or separate deployment is needed.

## Authorization and data

Sign in on `platform.uxia.app` and review the requested permissions before allowing access. The connection is associated with the Uxia workspace selected during authorization. To use a different workspace, select it in Uxia and authorize a new connection.

Your client manages its OAuth credentials. Never add access tokens, refresh tokens, API keys or passwords to this repository or `mcp.json`. Following an authentication migration, disconnect and reconnect if an existing connection no longer works. Disconnect through the client when finished; contact support if you need help revoking access.

The hosted service handles authentication and enforces permissions. Tool requests and the research data returned by them pass between your chosen AI client and Uxia. Review both providers' data policies before connecting.

## Capabilities

- Discover and manage workspace audiences and AI testers.
- Create and edit research drafts, including tasks, surveys and supported test blocks.
- Preview participants, readiness and costs before an explicitly approved launch.
- Read test progress, findings and available screenshot evidence.

The connected server provides the current tool names and schemas. Tool additions are delivered by the hosted service and do not require changes to this repository.

Try: “List my Uxia audiences,” “Help me draft a website usability test,” or “Show the progress of this Uxia test.” Ask for a preview before any launch that spends credits.

## Help and documentation

- [Product](https://uxia.app)
- [MCP documentation](https://platform.uxia.app/docs/integrations/mcp) (Uxia sign-in may be required)
- [Privacy policy](https://www.uxia.app/privacy-policy)
- [Terms](https://www.uxia.app/terms-conditions)
- Support: [hello@uxia.app](mailto:hello@uxia.app)

For connection trouble, check the endpoint, sign in to the intended workspace, reconnect, and confirm your client supports OAuth. Send support the client name and a sanitized error message. Do not include credentials or private research data in public issues.

## License

This repository's files are provided under the [MIT license](LICENSE). Use of the hosted Uxia service remains subject to Uxia's terms.
