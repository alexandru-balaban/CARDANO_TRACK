# Traceward — Cardano portal

Cardano-facing frontend and pitch materials for the TUM Blockchain & AI Hackathon 2026. This repo is the portal layer; the shared AI backend is maintained separately.

## Run locally

Use Node.js 22.12+ and pnpm.

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

The landing page and architecture diagram are static product/pitch surfaces. Landing-page calls to action lead to the investigation flow; the API endpoint in the example is illustrative. The interactive investigation flow, wallet integration, payment verification, and reports are not wired up yet. No real ADA payment is performed. The intended demo network is Cardano preprod. Prices, pool rewards and terms are centralized in `src/config/placeholders.ts`. Brand colours are centralized in `src/theme.ts`.

The Growth Pool is described as non-custodial: funds are held according to pool script rules, not in a team wallet. Pentest Pro is restricted to targets the user is authorized to test.

## GitHub Pages

The GitHub Actions workflow builds and publishes `dist/` on pushes to `main`. In repository Settings → Pages, the deployment source must be **GitHub Actions**. Relative asset and document links support the `/CARDANO_TRACK/` project path and local previews.
