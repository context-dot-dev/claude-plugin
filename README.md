# Context.dev for Claude

The official [Context.dev](https://context.dev) plugin for Claude. Search and research the live web, scrape and crawl sites, extract structured data, parse documents, find companies and people, retrieve brand intelligence, inspect account usage and API request logs, monitor website changes, and run large asynchronous batches.

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

- The production Context.dev MCP server with 51 tools at `https://mcp.context.dev/mcp?profile=claude`
- OAuth authentication through Context.dev
- Guidance that routes each request to the smallest suitable Context.dev tool
- Search, sourced answers, news, scraping, crawling, extraction, parsing, brand, company, people, screenshot, usage, request-log, monitor, webhook, feedback, and batch workflows

## People data

The people tools (`people-search` and `people-enrich`) return professional information about named people, such as name, job title, employer, work history, education, general location, and links to public professional and social profiles.

- **Sources:** publicly available sources, such as websites, public profiles, and news, and licensed third-party data providers.
- **Legal basis:** Context.dev's legitimate interests, and its customers' legitimate interests, in providing and using business information. Customers may not use the data for decisions about a person's eligibility for credit, employment, insurance, or housing.
- **Removal:** anyone can ask to see, correct, or delete their information, or to stop being included, by emailing [privacy@context.dev](mailto:privacy@context.dev) with their name and the profile URLs or email addresses the request relates to.

Details are in section 3 of the [Context.dev privacy policy](https://www.context.dev/privacy).

## Links

- [Context.dev documentation](https://docs.context.dev)
- [Context.dev API reference](https://docs.context.dev/llms.txt)
- [Support](mailto:support@context.dev)

## License

MIT — see [LICENSE](LICENSE).
