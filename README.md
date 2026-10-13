# SpriteCook for Grok Build

SpriteCook generates game art from Grok Build: sprites, characters, tilesets, UI kits, and short animations, in pixel art or detailed HD styles. This plugin adds the hosted SpriteCook MCP server plus workflow skills that show the agent how to keep a set of assets consistent and ready for your engine.

## What's Included

- `.mcp.json`: the hosted SpriteCook MCP server (`https://mcp.spritecook.ai/mcp/oauth`), which you sign in to with your SpriteCook account
- `skills/`: workflow skills for sprites, tilesets, UI kits, animation, uploads, presets, edge cleanup, and Godot export, plus a Grok-specific skill that walks you through signing in
- `.grok-plugin/plugin.json`: the plugin manifest

## Install

```bash
grok plugin install https://github.com/SpriteCook/grok-plugin
```

## Connect Your Account

1. In Grok Build, type `/mcps`.
2. Select `spritecook` and press `i` to sign in.
3. Approve the connection on the SpriteCook page that opens in your browser.

You only do this once. Grok Build stores and refreshes the sign-in itself, so you never paste an API key.

You need a SpriteCook account. Every account gets free credits each month, and paid plans add more.

## Try It

Ask the agent:

- "Generate a tiny pixel art knight, idle pose."
- "Build a top-down grass tileset."
- "Design a UI kit for a fantasy inventory screen."
- "Animate this sprite into a short idle loop."

Results are saved to your SpriteCook library, so you can download or reuse them later.

## Network Endpoints and Credentials

- `https://mcp.spritecook.ai/mcp/oauth`: the SpriteCook MCP server. All tools run here.
- `https://api.spritecook.ai`: SpriteCook sign-in (OAuth 2.1 with PKCE), plus upload links for images you choose to import.
- Asset downloads come from the signed links the tools return.

The plugin has no hooks or scripts that run on install, reads no local credentials or environment variables, and asks for no API keys. Sign-in uses OAuth, handled by Grok Build.

## Privacy and Terms

SpriteCook uses your prompts, and any images you choose to upload, to generate your assets. Read the [privacy policy](https://spritecook.ai/privacy) and [terms of service](https://spritecook.ai/terms).

## Skill Source of Truth

Bundled workflow skills come from [SpriteCook/skills](https://github.com/SpriteCook/skills). Update that repository first, then sync its committed skills into `skills/`. [skills-source.json](skills-source.json) records the exact bundled source revision. `skills/spritecook-connect-mcp` is specific to Grok Build and lives only in this repository.

## License

MIT. See [LICENSE](LICENSE).
