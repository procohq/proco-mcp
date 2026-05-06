# proco-mcp

**Proco MCP Server — financial tools for AI agents.**

Wallets, payments, policies, and treasury exposed as a Model Context Protocol server. Drop into Claude Code, Codex, or any MCP-compatible framework and your agent can transact on-chain in five minutes.

→ [procohq.com](https://procohq.com)

---

## Status

`Pre-release.` Scaffolding only. Implementation tracked in [`procohq/proco-sdk`](https://github.com/procohq/proco-sdk) and the parent Proco programme.

---

## What it gives an agent

When connected, the MCP server exposes financial tools the agent can call directly:

- `wallet_create` · `wallet_get` · `wallet_balance`
- `payment_create` · `payment_status`
- `policy_set` · `policy_get` (`pay_when`, `pay_if`, `sweep_when`)
- `treasury_get` · `treasury_rebalance`

Each tool returns structured JSON; every action is non-custodial and signed by the agent's own wallet.

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

