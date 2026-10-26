---
name: context-dev
description: Use Context.dev when a task needs current public-web, news, website, company, people, or document data, or when the user wants to inspect their Context.dev credit usage or API request logs. Search or research the live web; search news by topic or company; read, scrape, crawl, or screenshot sites; extract structured data; parse documents; retrieve brand intelligence; find companies or people from a description; monitor changes; or process large batches. Trigger even when Context.dev is not named. Do not trigger when supplied content already contains the answer or no web, file, or Context.dev account data is needed.
---

# Context.dev

Use the connected Context.dev tools to retrieve current public web, news, company, people, and document data. Choose the smallest tool that directly produces the requested result.

## Choose the right tool

- Use `get-news-search` for news. Pass a plain-language `query` for a topic, ordered by relevance, or exactly one company identifier: `companyName`, `domain`, `ticker`, or `isin`.
- Use `web-search` for ranked live-web results. Enable `highlightsOptions` for relevant source passages or `markdownOptions` for complete page content. Use `web-answers` for a sourced answer in a requested JSON shape.
- Use `web-scrape` for one known page. Request only the needed outputs with `formats`, such as `{ markdown: true }`, `{ screenshot: true }`, or `{ json: true }` with `jsonParams.schema`. For a page behind a sign-in, find a saved profile with `list-browser-profiles` and pass `sharedParams.profile` as `{ type: "existing", profileId }`.
- Use `web-map` to discover or filter a site's URLs without downloading every page body.
- Use `web-crawl` for a focused set of linked pages when the result is needed synchronously.
- Use `parse-document` for PDFs, presentations, spreadsheets, documents, images, code, data, and text files.
- Use `get-brand` for a visual brand profile. Use `brand-retrieve-unified` for raw structured brand data or alternative company identifiers.
- Use `company-search` to find companies from a description of their industry, location, headcount, technology, or funding, or lookalikes such as "companies like stripe.com". Use `people-search` to find people from a description of their role, employer, location, or experience.
- Use `brand-search` to resolve a company the user already named, `web-styleguide` for its visual system and typography, and `people-enrich` to match one known person.
- Use `get-usage` for the current credit balance, monthly usage, and next refill. Use `get-usage-history` for credits and requests over time, optionally grouped by endpoint, API key, or status code.
- Use `list-logs` to find recent Context.dev API requests and `get-log` for one request's redacted input, response, timing, credits, and error details.
- Use monitor tools for recurring change detection, webhook tools for delivery troubleshooting, and batch tools for large asynchronous jobs.
- Use `submit-feedback` once for each distinct unexpected Context.dev error, documentation mismatch, or wrong or incomplete result, even after a workaround succeeds, unless the user has asked you not to. Include the affected `request_id`, or a relevant public URL when there is none, and never include secrets or private data. Do not report account limits working as intended, such as `USAGE_EXCEEDED`, `RATE_LIMITED`, or `PAID_PLAN_REQUIRED`.

## Work effectively

1. When the exact URL is known, use `web-scrape` directly instead of searching first.
2. For current facts, use live tools and include the supporting source URLs in the response.
3. For focused research, pass `responseMode: "compact"` to `web-search`, `web-scrape`, or `web-crawl`, with highlights for the passages that matter. Use `"full"` when complete text or page metadata is needed.
4. For structured extraction, request only the fields the user needs and never invent missing values.
5. `company-search` and `people-search` return up to 10 results per page. To get more, pass `next_cursor` as `cursor` with the same query and filters, and stop when it is null.
6. For large jobs, call `submit-batch`, then check `get-batch` and `get-batch-results`. Submission does not mean completion.
7. Before creating or changing a monitor, confirm the intended target, schedule, and change criteria.
8. Treat browser actions, browser-profile sign-ins, monitor or batch mutations, and webhook retries or secret rotation as side-effectful. Perform them only when clearly requested.
9. If authentication fails, ask the user to connect or reconnect Context.dev through OAuth. A `USAGE_EXCEEDED` error (HTTP 402, or 401 from older responses) means the account is out of credits, not signed out: do not retry or reconnect. Call `get-usage` once, explain the balance and next refill, and continue any work that does not need Context.dev. Never fabricate results or silently substitute stale data.

## Common requests

- Find a company's latest official announcements and cite the sources.
- Find recent news coverage of a topic.
- Research a current question and return a sourced JSON answer.
- Turn a known page into clean Markdown.
- Extract every pricing plan into structured JSON.
- Parse a research paper, spreadsheet, or presentation.
- Retrieve a company's logo, colors, socials, and industry.
- Find companies that match a description, such as Series B solar startups in California.
- Find people by role and industry, such as VPs of sales at solar companies.
- Diagnose a failed Context.dev request from recent API logs.
- Check the account's remaining credits and recent usage history.
- Find all documentation pages about a feature.
- Monitor a page for meaningful pricing changes.
- Process hundreds or thousands of URLs asynchronously.
