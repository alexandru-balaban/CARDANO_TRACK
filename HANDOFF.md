# PavLex / IncidentGuard — Cardano track handoff

## What is implemented

- A responsive Cardano landing page at `/`.
- Product positioning for IncidentGuard: per-request security investigations for human operators and AI agents.
- Four-step journey: quote, wallet approval, payment/request binding, evidence report.
- Guardrail Agent and Pentest Pro tier descriptions. Pentest Pro is framed for authorised testing only.
- Agent API example with budget enforcement copy.
- Growth Pool copy that clearly states the pool is non-custodial and script-held.
- Cardano eUTxO and CIP-30 framing.
- PavLex-branded footer.
- Architecture artifacts:
  - `docs/architecture.html`
  - `docs/architecture.svg`
  - `docs/architecture.mmd`

## Run it

The machine needs Node.js. Then run:

```sh
pnpm install
pnpm dev
```

Open the local URL printed by Vite, usually `http://127.0.0.1:5173/`.

## Project decisions

- Current visual identity: Cardano blue `#0033AD`, defined in `src/theme.ts`.
- Prices, pool rewards, and terms are intentional placeholders in `src/config/placeholders.ts`.
- No real wallet, API, ADA payment, validator, or backend integration exists yet. Landing-page calls to action point to the investigation flow. The interactive `/app` portal is future work.
- The current local dev server was started through Codex's bundled Node runtime because system Node was unavailable. On a normal computer, standard Node LTS is enough.

## Suggested next work

1. Build the clickable `/app` portal and mocked investigation flow.
2. Add wallet connection through CIP-30 after choosing Mesh SDK or Lucid Evolution.
3. Connect quotes, payments, report generation, and audit history to the shared backend.
4. Fill confirmed prices and Growth Pool terms in `src/config/placeholders.ts`.
