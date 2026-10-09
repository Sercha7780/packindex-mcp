# PackIndex MCP Server

Live packaging material and input prices, quote checks, contract price adjustments, pack costing and supplier RFQs — using your own OPN plan.

PackIndex is a hosted (remote) MCP server by the Open Packaging Network. There is nothing to install: connect your MCP client to the server URL and sign in with your OPN account when a tool needs it.

| | |
|---|---|
| **Server URL** | `https://opnplatform.com/api/mcp` |
| **Transport** | Streamable HTTP |
| **Auth** | OAuth 2.1 (dynamic client registration and CIMD). Public price tools work without sign-in. |
| **MCP Registry** | `com.opnplatform/packindex` |
| **Docs** | https://opnplatform.com/mcp |

## What it does

PackIndex brings live packaging price benchmarks into the conversation — from inputs such as crude oil, naphtha, natural gas, power, aluminium and recovered paper, through raw materials such as PP, HDPE, PET and pulp, and semi-finished grades such as kraftliner, boxboard and BOPP film, to finished packs like corrugated boxes and bottles. Every index has a value for today, in USD and your currency.

- **Price check** — today's value of any index, with its recent change
- **Quote check** — is a supplier's price fair against the benchmark and its 12-month range?
- **Contract adjustment** — recalculate an index-linked contract price from its base date
- **Regional comparison** — one material across Europe, the US, China and the Middle East
- **12-week outlook** and **price-move explanations**
- **Carbon** — kg CO₂e per unit or per tonne (PEF Circular Footprint Formula)
- **Design Studio** — turn a brief into a packaging spec and cost it
- **PACKIQ** — specialist packaging agents (quote analysis, EPR fees, recyclability)
- **Trade Exchange** — find suppliers and, when you ask, send an RFQ

## Connect

**Claude** — Settings → Connectors → search "PackIndex", or *Add custom connector* with the server URL.

**Claude Code**
```bash
claude mcp add --transport http packindex https://opnplatform.com/api/mcp
```

**ChatGPT** — Apps → search "PackIndex", or add the server URL as a custom connector in developer mode.

**VS Code / Cursor / other MCP clients** — add a remote server:
```json
{
  "mcpServers": {
    "packindex": {
      "type": "http",
      "url": "https://opnplatform.com/api/mcp"
    }
  }
}
```

**Microsoft Copilot Studio** — Tools → Add a tool → Model Context Protocol → server URL, OAuth 2.0 with dynamic discovery.

## Tools (26)

| Tool | What it does |
|---|---|
| `search_indices` | Search PackIndex codes |
| `get_live_index` | Get one index value |
| `get_prices` | Get several index values |
| `get_all_indices` | List index values (paginated) |
| `get_index_history` | Get index history |
| `get_index_forecast` | Get index forecast (12 weeks) |
| `get_carbon_index` | Get Green Index carbon score |
| `get_market_movers` | Biggest risers and fallers |
| `explain_price_move` | Explain a price move |
| `check_quote` | Check a supplier quote |
| `price_adjustment` | Index-linked price adjustment |
| `compare_regions` | Compare a material across regions |
| `estimate_packaging_price` | Estimate a corrugated box price |
| `packindex_query` | Ask PackIndex in plain words |
| `draft_packaging_spec` | Design Studio: brief to spec |
| `cost_packaging_spec` | Design Studio: cost a spec |
| `compare_packaging_options` | Design Studio: compare options |
| `list_my_projects` | Design Studio: my projects |
| `update_project` | Design Studio: update a project |
| `list_packiq_agents` | List PACKIQ agents |
| `run_packiq_agent` | Run a PACKIQ agent |
| `get_agent_chain` | Next PACKIQ agent |
| `find_suppliers` | Exchange: find suppliers |
| `search_exchange_listings` | Search Exchange listings |
| `post_rfq` | Exchange: send an RFQ (asks before sending) |
| `get_my_rfqs` | Exchange: my RFQs |

## Example prompts

- "What is the polypropylene price today on PackIndex?"
- "My supplier quotes €1,450 per tonne for PP homopolymer. Is that fair?"
- "Our PP contract was €1,300/t in March, 60% linked to PP. What should we pay now?"
- "What should I pay for 10,000 B-flute boxes 400×300×200 mm in Canada?"
- "Who can make my carton in Canada? Send them an RFQ for 20,000 units."

## Plans

Everything follows your OPN plan exactly as in the web app: price data is free with 12-week delayed values (live on Essential and above; regional comparisons and outlooks on Professional), Design Studio uses Suite runs, PACKIQ uses credits and RFQs count toward your Exchange plan. Values are indicative benchmarks, not quotes or advice — cite them as PackIndex.

## Links

- Documentation: https://opnplatform.com/mcp
- Privacy: https://opnplatform.com/legal/privacy
- Terms: https://opnplatform.com/legal/terms
- Support: support@opnplatform.com · https://opnplatform.com/legal/contact

---

PackIndex is operated by Polimex Trade Inc. (Open Packaging Network), Richmond Hill, ON, Canada. This repository holds the public listing and connection details for the hosted server; the server itself is not open source.
