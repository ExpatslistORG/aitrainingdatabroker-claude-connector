# Aitrainingdatabroker.com for Claude

Aitrainingdatabroker.com is available as a connector in Claude. Ask Claude about selling, licensing or buying company data for AI training and it answers from the Aitrainingdatabroker.com blog, with a link to the full article on every result. This repo documents the connector. The live, always current version of these docs is at https://aitrainingdatabroker.com/docs/claude/.

## About Aitrainingdatabroker.com

AI Training Data Broker is an independent broker for company data deals with AI labs. Companies with 20 or more people sell or license their operational data (support tickets, team chat, CRM, SOPs, code, accounting) to AI labs for training, with third-party de-identification and counsel-reviewed contracts; labs and model teams source licensed, de-identified workflow data. Its blog answers the questions both sides ask. Visit it at https://aitrainingdatabroker.com.

## What is a Claude connector?

A connector lets Claude use an outside service while it answers you. This one is a Model Context Protocol (MCP) server hosted by Aitrainingdatabroker.com. It needs no account and no API key, and every tool is read-only.

## Add it to Claude

1. In Claude, open Settings, then Connectors.
2. Choose Add custom connector.
3. Paste the endpoint below and choose no authentication if asked.

```
POST https://aitrainingdatabroker.com/api/mcp/claude
Content-Type: application/json
```

Any MCP client that speaks Streamable HTTP works the same way. The included `.mcp.json` is an example config for clients that read one.

## Tools

| Tool | What it does |
|---|---|
| `latest_posts` | The newest articles, optionally only for sellers or only for buyers, with a one-line summary and a link. |
| `search_posts` | Articles matching a topic, such as pricing, legality, exclusivity or RL data. |
| `get_post` | One article: date, who it is for, the opening 120 words, the questions its FAQ answers and a link to read the rest. |
| `search / fetch` | The standard connector pair, the same content in the shape deep research expects. |

## Example prompts

- How much do AI labs pay for company data?
- Is it legal to sell my company data to an AI lab?
- What is RL data, and why do labs ask for it?
- Show me the latest AI Training Data Broker articles for buyers.

## What the connector returns

- Published blog articles only: titles, dates, summaries, openings and links.
- Never anything from the partner portal: no deals, intakes, requests or contact details.
- It cannot sign anyone up, send a request or change anything.
- Articles are the broker's guidance for sellers and buyers, not legal or tax advice.
- Links carry `utm_source=claude` so analytics can tell visits from Claude apart from other visits. The tag identifies the connector, not you.

## Data and privacy

We receive the name of the tool called and its parameters: a search phrase, an audience or an article slug. We receive no Claude account details, no name, no email address and no conversation history. We keep standard server logs and nothing else about connector use. The full policy is at https://aitrainingdatabroker.com/privacy/ and the terms are at https://aitrainingdatabroker.com/terms/.

## Limits

- At most 10 results per call, newest first or best match first.
- Calls are rate limited per address. Please do not use the connector to copy the blog in bulk.

## Support

Questions, bug reports or removal requests: use the contact page (https://aitrainingdatabroker.com/contact/).

## More from Aitrainingdatabroker.com

- Website: https://aitrainingdatabroker.com
- Blog: https://aitrainingdatabroker.com/blog/
- Developer docs for Claude: https://aitrainingdatabroker.com/docs/claude/
- Developer docs for ChatGPT: https://aitrainingdatabroker.com/docs/chatgpt/
- ChatGPT plugin: https://github.com/ExpatsListORG/aitrainingdatabroker-chatgpt-plugin
- Claude skill: https://github.com/ExpatsListORG/aitrainingdatabroker.com
