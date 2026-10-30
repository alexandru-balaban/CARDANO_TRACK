# Traceward — Cardano portal

Cardano-facing frontend and pitch materials for the TUM Blockchain & AI Hackathon 2026. This repo is the portal layer; the shared AI backend is maintained separately.

## Run locally

Use Node.js 24 and pnpm 11.25.0, matching the deployment workflow.

```sh
pnpm install --frozen-lockfile
pnpm dev
```

For a production build and local production preview:

```sh
pnpm build
pnpm preview
```

The landing page is `/`. The architecture diagram is available at `/docs/architecture.html` and as Mermaid source at `docs/architecture.mmd`.

## Current state

The landing page and architecture diagram are static product/pitch surfaces. Landing-page calls to action lead to the investigation flow; the API endpoint in the example is illustrative. The interactive investigation flow, wallet integration, payment verification, and reports are not wired up yet. No real ADA payment is performed. The intended demo network is Cardano preprod. Prices, pool rewards, and terms remain unconfirmed. Rendered landing-page colors and typography live in `src/style.css`. The older `src/config/placeholders.ts` and palette reference `src/theme.ts` are not currently imported by the page.

The Growth Pool is described as non-custodial: funds are held according to pool script rules, not in a team wallet. Pentest Pro is restricted to targets the user is authorized to test.

## GitHub Pages

The GitHub Actions workflow builds and publishes `dist/` on pushes to `main`. In repository Settings → Pages, the deployment source must be **GitHub Actions**. Relative asset and document links support the `/CARDANO_TRACK/` project path and local previews.

## Backend handoff

See [HANDOFF.md](HANDOFF.md) for the source map, working UI interactions, and backend integration points. The dashboard and API snippet are illustrative; the application currently makes no backend requests.
