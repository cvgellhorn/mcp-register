---
name: mcp-register
description: Use when listing Spacecamps (spacecamps.com.au) on free directories, or when publishing the mcp-register repo to MCP and agent registries. Skip AlternativeTo. Draft listings only from the public product facts in this repo.
license: MIT
metadata:
  author: cvgellhorn
  version: "1.0"
---

# Spacecamps directory registration

Spacecamps is the product. The public source is https://spacecamps.com.au. This repository is the MCP server and the launch desk for the 50 free directory rows.

## Do this first

1. Call `get_product` and use only those facts.
2. Call `next_directory` with the slugs already submitted.
3. Call `draft_listing` for that slug and paste it. Do not add claims that are not in the draft.
4. AlternativeTo is already submitted. If a tool returns it, skip the form.

## Waves

- Waves 1, 3, 4 and 5 list Spacecamps the booking product. The URL is https://spacecamps.com.au.
- Wave 2 lists this repository, https://github.com/cvgellhorn/mcp-register. Add the GitHub topic `gemini-cli-extension`.
- Wave 5 submits the marketing homepage, not the dashboard.

## Leave out

- Prices other than Small at A$59 per month including tax, Medium at A$129 per month including tax, and Enterprise with no public amount.
- Customers, review scores, or integrations that are not in `get_product`.
- Anything from the private spacecamps source repository: Stripe price identifiers, webhook secrets, sandbox keys, database URLs.
- Hype. Write plain sentences.

## Publish the MCP server

The manifest files are `server.json`, `glama.json`, `.cursor-plugin/plugin.json`, `mcp.json`, `.claude-plugin/plugin.json`, `.mcp.json`, `gemini-extension.json` and `SKILL.md`.

`server.json` description is 100 characters or fewer.

After the npm package `@cvgellhorn/mcp-register` is published:

```bash
brew install mcp-publisher && mcp-publisher login && mcp-publisher publish
```

Stop if a directory asks for payment or for an account that is not already signed in.
