# SpriteCook for Grok Build

SpriteCook generates game art from Grok Build: sprites, characters, tilesets, UI kits, and short animations, in pixel art or detailed HD styles. This plugin adds the hosted SpriteCook MCP server plus workflow skills that show the agent how to keep a set of assets consistent and ready for your engine.

## What's Included

- `.mcp.json`: the hosted SpriteCook MCP server (`https://mcp.spritecook.ai/mcp/oauth`), which you sign in to with your SpriteCook account
- `skills/`: workflow skills for sprites, tilesets, UI kits, animation, uploads, presets, edge cleanup, and Godot export
- `.grok-plugin/plugin.json`: the plugin manifest

## Install

```bash
grok plugin install https://github.com/SpriteCook/grok-plugin
```

## Connect Your Account

The first time the agent calls a SpriteCook tool, Grok Build opens the SpriteCook sign-in in your browser. Approve the connection and you're set. Grok Build stores and refreshes the sign-in itself, so you never paste an API key.

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

Bundled workflow skills come from [SpriteCook/skills](https://github.com/SpriteCook/skills). Update that repository first, then sync its committed skills into `skills/`. [skills-source.json](skills-source.json) records the exact bundled source revision.

## License

MIT. See [LICENSE](LICENSE).
