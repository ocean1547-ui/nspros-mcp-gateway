# NS Pros MCP Gateway

**174,966 MCP servers. One endpoint.**

**Every MCP server and public data source in the world — in one place, at
the lowest price.**

The NS Pros MCP Gateway fronts the public MCP registries behind a single managed
endpoint. Instead of hunting through registries and wiring up servers one at a
time, you connect your MCP client to one address, search the whole catalog from
inside your client, and call tools through the same connection. The gateway is
hosted around the clock, the catalog is re-gathered daily, and connected
servers are health-checked daily.

- **Endpoint:** `https://mcp.nspros.ca/mcp` (Streamable HTTP)
- **Overview & pricing:** https://nspros.ca/mcp
- **Status:** public pilot — free for everyone until **February 28, 2027**

## Connect

Add the gateway to any MCP client that supports remote (Streamable HTTP) servers:

```json
{
  "mcpServers": {
    "nspros": {
      "url": "https://mcp.nspros.ca/mcp"
    }
  }
}
```

Client-specific files are in [`examples/`](examples/) (Claude Code / Claude
Desktop, Cursor, VS Code).

## What works today

**No key needed**

| Tool | What it does |
|---|---|
| `catalog_search` | Search the full catalog — 174,966 servers gathered from the public registries, deduplicated and refreshed daily. Filter by pack. |
| `catalog_stats` | Live catalog counts: packs, license-checked and remote-ready totals, and the servers currently proxied. |

**With a gateway key** (header `X-API-Key`, or `Authorization: Bearer <key>`)

1,854 tools are live through the gateway (measured 2026-11-20): 69 upstream
servers are proxied, namespaced as `<server>__<tool>`, alongside the NS Pros
Data API and the catalog tools. The proxied set grows as more upstream servers
pass verification.

Gateway keys are free during the launch period. Create an account at
https://nspros.ca and email hello@nspros.ca to get one.

## Packs

The catalog is grouped into 10 packs by the job you are doing:

| Pack | Servers |
|---|---:|
| Finance & Payments API | 14,311 |
| Data & Knowledge API | 14,018 |
| AI Agents | 12,710 |
| Coding & Development | 9,040 |
| Infrastructure & DevOps | 7,366 |
| Databases | 6,705 |
| Web & Browser Automation | 5,381 |
| Developer Utilities | 1,495 |
| IoT & Devices | 461 |
| Everything Else | 57,025 |

Of the 174,966 servers in the catalog, 25,297 are license-checked for
commercial use — those are the ones we recommend and proxy first. Counts as of
November 18, 2026; the catalog is re-gathered daily.

## BYOK — your keys, your accounts

MCP is an open protocol, so connecting to a server costs nothing by itself. What
the subscription pays for is the gateway work: one managed endpoint, hosting
slots for servers that need them, and daily health checks that notice when a
server goes down. Tool usage is never billed by us — it runs on your own keys
and lands on your own provider accounts, at the provider's prices. No per-call
markup, on any plan.

## Pricing (USD)

| Plan | Price | What you get |
|---|---|---|
| Free | $0 | Full catalog search, 1 pack, 10 remote connections, your own keys |
| Builder | $9/mo | All 10 packs, unlimited connections, 3 hosting slots |
| Pro | $24/mo | 10 hosting slots, health checks and outage alerts, team sharing |
| Studio | from $49/mo | Embed the gateway in your own product; manage end-user connections |

Launch promo: every plan is free until February 28, 2027 — no card needed.
Paid plans start March 1, 2027.

For comparison: Glama's gateway plans run $9 / $26 / $80 a month and Composio
Pro is $29 a month, and per-call marketplaces charge for every call (APIbase:
$0.0005–$29.99 per call). These tiers are set at or below comparable plans,
and tool usage always runs on your own accounts with no per-call markup.

## About this repository

This repo holds the public docs, connection examples and registry metadata for
the gateway. The gateway itself runs on NS Pros infrastructure and is not open
source. Catalog data comes from the public MCP registries, including Glama,
Smithery, the official MCP Registry and PulseMCP; server names and descriptions
belong to their respective authors, and each server keeps its own license terms.

Run by [NS Pros](https://nspros.ca) in Halifax, Nova Scotia.
Questions: hello@nspros.ca
