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

The people tools (`people-search` and `people-enrich`) return professional information about named people: name, job title, employer, work history, education, skills, general location, and links to public professional and social profiles. `people-enrich` can also return a work email address. The brand and company tools can return a company's public contact details.

- **Sources:** publicly available sources, such as websites, public profiles, and news, and licensed third-party data providers.
- **Legal basis:** Context.dev's legitimate interests, and its customers' legitimate interests, in providing and using business information. Customers may not use the data for decisions about a person's eligibility for credit, employment, insurance, or housing.
- **Removal:** anyone can ask to see, correct, or delete their information, or to stop being included, by emailing [privacy@context.dev](mailto:privacy@context.dev) with their name and the profile URLs or email addresses the request relates to.

Details are in section 3 of the [Context.dev privacy policy](https://www.context.dev/privacy).

## Data and privacy

The plugin connects to one service, the Context.dev MCP server at `https://mcp.context.dev`, and installs nothing on your machine. When Claude calls a Context.dev tool, the request you ask for, such as a URL, search query, schema, or file, is sent to Context.dev to fetch, process, and return the result, and is billed to your Context.dev account. Sign-in uses Context.dev OAuth, so no API key is stored in Claude.

Context.dev keeps request logs to operate, secure, bill for, and improve the service, which can include training the models it uses. Requests made with zero data retention (`zdr`) are processed without keeping their content. The [privacy policy](https://www.context.dev/privacy) covers collection, use, and retention in full.

## Troubleshooting

- **Sign-in fails or tools are missing:** in Claude Code, open `/mcp` and reconnect `context`; in Claude, disconnect and reconnect the connector.
- **`USAGE_EXCEEDED` or `RATE_LIMITED`:** ask Claude to run `get-usage` to see your credit balance, next refill, and request limits.
- **A request failed:** ask Claude to run `list-logs` with errors only, then `get-log` with the request ID for the full error.

## Links

- [Context.dev documentation](https://docs.context.dev)
- [Context.dev API reference](https://docs.context.dev/llms.txt)
- [Privacy policy](https://www.context.dev/privacy)
- Support: [support@context.dev](mailto:support@context.dev)
- Security reports: [hello@context.dev](mailto:hello@context.dev) with the subject "Context MCP security report"

## License

MIT — see [LICENSE](LICENSE).
