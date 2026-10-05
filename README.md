# Cryptominium MCP server

What a crypto position would really sell for: measured exit costs, the monthly
Exit-Friction Index, and address and transaction lookups. Read-only.

```
https://cryptominium.com/mcp
```

Streamable HTTP. No account, no key, no cost.

This repository holds the connection files only: the listing for the official
MCP Registry, a Gemini CLI extension, a Cursor plugin and the logo. The server
itself runs at the address above and is not published here.

## What it does

Every day, Cryptominium measures what a $100,000 sell of each tracked token
actually returns against its quoted price, on Base, Ethereum and BNB Chain and
on exchange order books. Every answer carries its measurement date and a link
to the page it came from.

| Tool | What it answers |
|---|---|
| `exit_cost` | What selling a token really returns, measured, with the date |
| `exit_index` | The monthly Exit-Friction Index: the median share of value lost selling $100,000, across every measured token |
| `coin_profile` | CM Profile: what is known about a coin, what is measured, and what is not known |
| `powermap` | PowerMap: which company or group holds which of nine powers over a coin (freeze, pause, mint, redeem, custody, govern, validate, pay out, bridge) |
| `identify_address` | What a public address or ENS name is: wallet or contract, which chains, which token |
| `explain_transaction` | What an EVM transaction did: what moved, the fee, approvals granted or revoked |
| `what_is` | What a crypto word means, in plain English, with sources |
| `search` | Cryptominium search: what a query is, and the matching coins and pages |

No trading, no wallet connection, and nothing a caller sends is stored.
Measurements, not advice: Cryptominium does not recommend buying, selling or
holding anything.

## Try asking

- "What would I really get selling $100,000 of YFI?"
- "What was the exit-friction index last month?"
- "What is this address: vitalik.eth"
- "Who can freeze USDC?"

## Connect

**Claude** (claude.ai or Claude Desktop): Settings → Connectors → Add custom
connector, URL `https://cryptominium.com/mcp`.

**Claude Code:**

```bash
claude mcp add --transport http cryptominium https://cryptominium.com/mcp
```

**Gemini CLI:**

```bash
gemini extensions install https://github.com/wanchwolfred-arch/cryptominium-mcp
```

**Cursor:** install the Cryptominium plugin from the Cursor Marketplace, or add
to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "cryptominium": { "url": "https://cryptominium.com/mcp" }
  }
}
```

**VS Code:** Command Palette → "MCP: Add Server" → HTTP →
`https://cryptominium.com/mcp`.

Any other client that speaks streamable HTTP can use the URL directly.

## Citing

Quote the figure with its date and the link the tool returns, for example:
"Selling $100,000 of AERO on Base costs 0.4% — measured 4 Oct 2026 by
Cryptominium. https://cryptominium.com/exit/base/aerodrome-finance"

## Links

- Developers and the free API: https://cryptominium.com/developers
- Methodology: https://cryptominium.com/methodology
- Privacy: https://cryptominium.com/privacy#mcp
- Official MCP Registry name: `com.cryptominium/cryptominium`
- Support: hello@cryptominium.com

## Licence

The files in this repository are MIT licensed (see `LICENSE`). The
measurements the server returns are covered by the terms on
https://cryptominium.com/data, not by this licence.
