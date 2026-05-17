# proco-mcp

**Proco MCP Server — on-chain capital markets infrastructure as a Model Context Protocol server.** Capital accounts, settlement conditions, treasury controls, and programmable USDC flows — accessible to any MCP-compatible system in minutes.

→ [procohq.com](https://procohq.com)

---

## Status

`Pre-release.` Scaffolding only. Implementation tracked in [`procohq/proco-sdk`](https://github.com/procohq/proco-sdk) and the parent Proco programme.

---

## What it exposes

When connected, the MCP server exposes on-chain capital markets infrastructure as callable tools:

- `wallet_create` · `wallet_get` · `wallet_balance`
- `payment_create` · `payment_status`
- `policy_set` · `policy_get` (`pay_when`, `pay_if`, `sweep_when`)
- `treasury_get` · `treasury_rebalance`

Each tool returns structured JSON; every action is non-custodial and signed by the principal's own wallet across Hyperliquid, Base, and Solana.

---

## Quickstart

```bash
npm install -g @proco/mcp
```

Add to your MCP client config:

```json
{
  "mcpServers": {
    "proco": {
      "command": "proco-mcp",
      "env": {
        "PROCO_API_KEY": "sk_..."
      }
    }
  }
}
```

Get an API key at [procohq.com/sign-in](https://procohq.com/sign-in) — free sandbox, no credit card.

---

## Links

- [Proco SDK](https://github.com/procohq/proco-sdk) — TypeScript client used under the hood
- [Proco Agent Skill](https://github.com/procohq/proco-agent-skill) — the same tools as a LangChain/CrewAI/AutoGen skill
- [Examples](https://github.com/procohq/examples) — runnable integration templates
- [Docs](https://procohq.com/docs)

---

## License

MIT
