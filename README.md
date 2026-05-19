# proco-mcp

**Proco MCP Server — on-chain capital markets infrastructure as a Model Context Protocol server.** Capital accounts, settlement conditions, treasury controls, and programmable USDC flows — accessible to any MCP-compatible system in minutes.

→ [procohq.com](https://procohq.com)

---

## Status

`Pre-release.` API stable. Production rollout tracked alongside the [Proco SDK](https://github.com/procohq/proco-sdk).

---

## What it exposes

When connected, the MCP server exposes on-chain capital markets infrastructure as callable tools:

- `wallet_create` · `wallet_get` · `wallet_balance`
- - `payment_create` · `payment_status`
  - - `policy_set` · `policy_get` (`pay_when`, `pay_if`, `sweep_when`)
    - - `treasury_get` · `treasury_rebalance`
     
      - Each tool returns structured JSON; every action is non-custodial and signed by the principal's own wallet across Hyperliquid, Base, and Solana.
     
      - ## Quickstart
     
      - ```bash
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

        ## Example: Treasury sweep at end of session

        A trading desk closes Hyperliquid positions at end of day. The MCP tool sweeps unused margin back to the Base treasury:

        ```json
        {
          "tool": "treasury_rebalance",
          "from": "hyperliquid-margin",
          "to": "base-treasury",
          "amount": "500000",
          "currency": "USDC"
        }
        ```

        Settlement: ~12 seconds. Non-custodial. No intermediary.

        ## Links

        - [Proco SDK](https://github.com/procohq/proco-sdk) — TypeScript client used under the hood
        - - [Proco Agent Skill](https://github.com/procohq/proco-agent-skill) — the same tools as a LangChain/CrewAI/AutoGen skill
          - - [Docs](https://procohq.com/docs)
           
            - ## License
           
            - MIT
