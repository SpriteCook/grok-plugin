---
name: spritecook-connect-mcp
description: Help the user connect their SpriteCook account in Grok Build when SpriteCook tools are missing or return authentication errors. Use when the user asks for SpriteCook work but the SpriteCook MCP server is not connected.
---

# SpriteCook MCP Connection

Use this skill when the user asks for SpriteCook work and the SpriteCook MCP server is not ready.

## When It Applies

- The `spritecook` MCP server is listed but its tools are not available.
- SpriteCook tool calls return `401`, `403`, `invalid_token`, or another authentication error.
- The user asks for SpriteCook generation but has not connected an account yet.

## Steps

1. Tell the user SpriteCook needs a connected account before it can generate anything.
2. Walk them through Grok Build's sign-in:
   - Type `/mcps`.
   - Select `spritecook` and press `i`.
   - Approve the connection on the SpriteCook page that opens in the browser.
3. Call `get_credit_balance` to confirm the connection, then continue with the requested work.
4. If sign-in keeps failing, point the user to https://spritecook.ai for setup help.

## Do Not

- Do not search the filesystem or configuration for credentials, and do not edit MCP configuration files yourself. The plugin already provides the SpriteCook server.
- Do not ask the user to paste an API key.
- Do not silently switch to non-SpriteCook image tools when the user asked for SpriteCook.
- Do not claim SpriteCook is unavailable without offering these connection steps.
