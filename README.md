# Context.dev for Claude

The official [Context.dev](https://context.dev) plugin for Claude. Search and research the live web, scrape and crawl sites, extract structured data, parse documents, retrieve brand and people intelligence, inspect API request logs, monitor website changes, and run large asynchronous batches.

## Install

Install **Context.dev** from Claude's plugin directory, then authenticate when Claude opens the Context.dev OAuth flow. No API key needs to be copied into Claude.

For local development:

```bash
git clone https://github.com/context-dot-dev/claude-plugin.git
claude plugin validate --strict ./claude-plugin
claude --plugin-dir ./claude-plugin
```

In Claude Code, open `/mcp`, approve the `context` server, and complete the Context.dev OAuth flow in your browser. Then run one of the prompts below. Claude should call a `context` MCP tool and return a sourced result. Loading the plugin with `--plugin-dir` keeps the test isolated to that session.

## Try it

Ask Claude:

```text
Use Context.dev to find Stripe's latest official product announcements. Include the most relevant passage and source URL for each result.
```

```text
Use Context.dev to extract every pricing plan from https://www.context.dev/pricing as structured JSON.
```

```text
Use Context.dev to retrieve the brand profile for linear.app, including its logo, colors, fonts, and social profiles.
```

## Included

- The production Context.dev MCP server with 40 direct, typed tools at `https://mcp.context.dev/mcp`
- OAuth authentication through Context.dev
- Guidance that routes each request to the smallest suitable Context.dev tool
- Search, sourced answers, news, scraping, crawling, extraction, parsing, brand, people, screenshot, request-log, monitor, webhook, feedback, and batch workflows

## Links

- [Context.dev documentation](https://docs.context.dev)
- [Context.dev API reference](https://docs.context.dev/llms.txt)
- [Support](mailto:support@context.dev)

## License

MIT — see [LICENSE](LICENSE).
