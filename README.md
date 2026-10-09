# Polish Company Financials MCP Server

Read multi-year financial statements filed with the Polish KRS, rank companies in their industry and region, and compare them with sector benchmarks.

Remote MCP server (Streamable HTTP), read-only, hosted by [Compabase](https://compabase.com/companies).

```
https://compabase.com/api/mcp/financials
```

## Tools

| Tool | What it does |
|---|---|
| `search_companies / count_companies` | Filter companies by revenue, profit, assets, EBITDA, PKD and region. |
| `get_financials` | Full financial statements by fiscal year. |
| `get_company_rankings` | Revenue rank in industry, region and country. |
| `get_financial_stats` | Sector and regional benchmarks. |
| `get_company / get_company_secured_liabilities` | Headline figures and secured liabilities. |

## Example prompts

- Show revenue and net profit of Orlen for the last three years.
- List the 10 largest software companies in Gdańsk by revenue.
- How does this company's margin compare with its industry?

## Authentication

Sign in with your Compabase account (OAuth) in clients that support it, or send an MCP key: create one at https://compabase.com/integrations?tab=mcp and pass it as `Authorization: Bearer mcpk_…` or append `?apiKey=mcpk_…` to the URL. Queries count toward your Compabase plan.

## Setup

**Claude (claude.ai, Desktop):** Settings → Connectors → Add custom connector → paste the URL above (add `?apiKey=mcpk_…` if you use a key).

**Cursor / VS Code / Windsurf** (`mcp.json`):

```json
{
  "mcpServers": {
    "polish-company-financials": {
      "url": "https://compabase.com/api/mcp/financials",
      "headers": { "Authorization": "Bearer mcpk_YOUR_KEY" }
    }
  }
}
```

**ChatGPT:** Settings → Apps → Developer mode → Create → paste the URL.

## About

Part of the [Compabase](https://compabase.com/docs/mcp/) MCP family. Full Compabase MCP (all Polish company data tools): https://compabase.com/api/mcp.

Questions: contact@compabase.com

## Gemini CLI

```bash
gemini extensions install https://github.com/ContentWriterco/Polish-Company-Financials-MCP
```

Gemini CLI asks for your Compabase MCP key during installation (create one at https://compabase.com/integrations?tab=mcp).
