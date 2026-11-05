# mcp-register

Launch desk and MCP server for [Spacecamps](https://spacecamps.com.au), booking software for independent caravan and holiday parks in Australia and New Zealand.

The desk walks the 50 free dofollow directories. AlternativeTo is already submitted. Wave 2 publishes this repository to MCP and agent registries. Product copy is taken from the public site. Prices on the page are the public ones: Small is A$59 per month including tax, Medium is A$129 per month including tax, and Enterprise has no public monthly amount.

The directory order follows [Ilias Ism's launch playbook](https://il.ly/growth/directories).

## Run the desk

```bash
npm install
npm run dev
```

Open http://localhost:3847. Ticks are stored in this browser.

## Run the MCP server

```bash
npm run build:mcp
node dist/stdio.js
```

Claude Code, Cursor and Gemini CLI start that file from `.mcp.json`, `mcp.json` and `gemini-extension.json`.

The dev server also exposes the same tools at `/mcp` over Streamable HTTP.

## Registry files

| File | What reads it |
| --- | --- |
| `server.json` | Official MCP Registry. Description is 100 characters or fewer. |
| `glama.json` | Glama maintainer claim |
| `.cursor-plugin/plugin.json` and `mcp.json` | Cursor Marketplace and cursor.directory |
| `.claude-plugin/plugin.json` and `.mcp.json` | Claude Code and Cowork |
| `gemini-extension.json` | Gemini CLI gallery, after the repo topic `gemini-cli-extension` |
| `SKILL.md` | ClawHub, skills.sh, MCP Market, awesome-claude-skills |

Publishing to the Official MCP Registry needs an npm release of `@cvgellhorn/mcp-register` first (`package.json` `mcpName` is `io.github.cvgellhorn/mcp-register`), then:

```bash
brew install mcp-publisher && mcp-publisher login && mcp-publisher publish
```

`npm run test` checks the 50 rows, the public prices, and a live stdio session.
Add the GitHub topic `gemini-cli-extension` on this repository so the Gemini CLI gallery can index it.
