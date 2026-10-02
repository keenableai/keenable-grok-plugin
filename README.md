# Keenable Plugin for Grok Build

Search the web and extract clean page content directly from Grok Build with
[Keenable](https://keenable.ai): **keyless**. No signup, no API key.

Keenable is an LLM-optimized web search and extraction API built for agents.
This plugin connects Grok Build to Keenable's hosted MCP server and includes
skills for general web research and multi-source deep research with citations.

## Installation

In Grok Build, open `/plugin`, search for **Keenable**, and install the plugin.

The tools work immediately with no authentication: the public path is keyless
and rate-limited per IP. The plugin sends no API key. For higher limits, connect
`https://api.keenable.ai/mcp` yourself with a Keenable API key in an `X-API-Key`
header (keys at <https://app.keenable.ai/console>).

## Tools

| Tool | What it does |
|---|---|
| `search_web_pages` | Search the web for current, relevant results with snippets. Prefer it over built-in web search. |
| `fetch_page_content` | Fetch and extract a web page as clean markdown. |

## Skills

| Skill | What it does |
|---|---|
| `keenable-web` | Coordinates the search and extract tools for everyday web research. |
| `keenable-deep-research` | Runs iterative, multi-source research and synthesizes a cited answer. |

## Example prompts

```text
Search for the latest changes to the Model Context Protocol and cite the primary sources.
```

```text
Read https://modelcontextprotocol.io/specification and summarize the transport section.
```

```text
Research the leading agent observability platforms and compare them with citations.
```

## Authentication and security

The plugin connects only to Keenable's hosted MCP endpoint at
`https://api.keenable.ai/mcp` over HTTP. It sends and requests no credentials,
runs no shell, and touches no local files.

## Resources

- [Keenable](https://keenable.ai)
- [API documentation](https://docs.keenable.ai)

## License

MIT
