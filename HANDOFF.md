# Traceward — frontend handoff

Traceward is the working product name for the Cardano track. This repository contains the React/Vite frontend; the shared AI backend is maintained separately.

## Run locally

Use Node.js 24 and pnpm 11.25.0, matching the GitHub Pages workflow.

```sh
pnpm install --frozen-lockfile
pnpm dev
```

Vite prints the local URL. For a production build and preview:

```sh
pnpm build
pnpm preview
```

## Implemented

- Responsive landing page with centered hero, an illustrative workspace, service cards, agent API example, Growth Pool explanation, and Cardano payment framing.
- Three working preview tabs: investigation, payment approval, and evidence report.
- Mobile navigation, expandable FAQs, and a copy button for the illustrative API example.
- Readable secondary text and aligned service-card actions.
- Architecture page and downloadable SVG, with Mermaid source.

## Source map

| File | Purpose |
| --- | --- |
| `src/main.tsx` | Landing page, `DemoDashboard`, preview state, FAQ content, illustrative API example |
| `src/style.css` | Rendered styles, colors, typography, and responsive layout |
| `src/theme.ts` | Palette reference; currently not imported by the page |
| `src/config/placeholders.ts` | Earlier commercial placeholders; currently not imported by the page |
| `docs/architecture.html` | Standalone architecture page |
| `docs/architecture.svg` | Downloadable architecture diagram |
| `docs/architecture.mmd` | Conceptual architecture in Mermaid |
| `vite.config.ts` | React plugin and relative asset base |
| `.github/workflows/pages.yml` | Production build and GitHub Pages deployment |

## Backend integration status

The workspace, request `TW-0248`, status labels, payment binding, and evidence content are illustrative UI data. The preview tab state is local React state. No API calls are executed by the application.

The `apiExample` string in `src/main.tsx` shows a proposed request with `tier`, `incident`, and `budgetAda`. `INVESTIGATION_API`, `apiKey`, and `YOUR_BUDGET` are example identifiers, not configured values. This snippet is not an agreed or implemented backend contract.

There is no `/app` route, API client, authentication flow, connected wallet, payment verification, validator integration, or report persistence yet. Landing-page buttons navigate to page sections. The architecture describes the proposed system, not deployed services.

### Integration points to agree

1. Backend routes and request/response schemas for quotes, investigation submission, job status, evidence reports, and audit history.
2. Authentication and the distinction between operator wallet approval and agent access.
3. Confirmation and request-binding proof required before the backend dispatches an investigation once.
4. Quote expiry, budget enforcement, error states, and report delivery.

The intended demo network is Cardano preprod. Pentest Pro requires authorised targets and explicit scope. Growth Pool credits, reward rules, and prices are not confirmed.

## Deployment

`main` automatically builds and deploys to GitHub Pages. Only generated `dist/` output is deployed; the build also copies the architecture files to `dist/docs/`. Relative links support the `/CARDANO_TRACK/` repository path.

GitHub Pages serves the static frontend. The shared backend needs its own hosting, API URL, and appropriate browser access configuration. Vite exposes `VITE_` environment values to the browser, so those values must be public configuration.

## Visual direction

The landing page follows the Sirius reference's centered composition, charcoal type, blue actions, pastel UI tiles, and pale section backgrounds. The current primary blue is `#2C49D8`. Landing-page colors are applied in `src/style.css`.
