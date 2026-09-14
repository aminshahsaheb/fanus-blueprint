# Fānus Blueprint

> Visual engineering and observability interface for the Fānus ecosystem.

Fānus Blueprint is the visual / explanatory surface for the Fānus system. It presents architecture, state transitions, API concepts, ledger integrity, migration flows, ritual interaction, and runtime-oriented observability in a single immersive interface.

## Role in the ecosystem

```
Fanus-Living-Seal
      │
      └── canonical core / source of truth
                │
                ├── fanus-presence
                │      └── presence + verification runtime
                │
                ├── fanus-app
                │      └── application experience
                │
                └── fanus-blueprint
                       └── visual engineering / Blueprint surface
```

This repository is intentionally independent from `fanus-presence`. The Blueprint must not become a second implementation of the canonical core.

## Source policy

The current `index.html` is the original Fanus 1 Blueprint source carried into Git as a standalone static site. The first migration preserves its visual language and runtime behavior rather than silently redesigning or rewriting it.

Before converting the page into a component framework, audit and classify every simulated, mocked, external, and real runtime behavior.

## Deployment

This project is designed for Netlify as a static site:

- Production entrypoint: `index.html`
- Publish directory: repository root
- Build command: none
- Netlify configuration: `netlify.toml`

Recommended production flow:

```
GitHub main
    ↓
Netlify
    ↓
fanus1.netlify.app
```

Keep the Netlify site for `fanus-presence` separate. Do not point both sites at the same repository unless the deployment architecture is intentionally changed.

## External runtime dependencies

The Blueprint currently loads selected browser dependencies from CDNs, including Vazirmatn, Three.js, GSAP / ScrollTrigger, and Chart.js. Runtime/API demonstrations in the page must be treated according to their actual implementation; visual simulation is not proof of backend execution.

## Engineering rules

1. Preserve the established visual identity unless a deliberate redesign is approved.
2. Keep canonical core logic out of this repository.
3. Never present mocked or simulated telemetry as verified production telemetry.
4. Keep deployment configuration explicit and minimal.
5. Prefer small, reviewable commits.
6. Test desktop and mobile behavior after visual changes.

## Current state

- [x] Original Fanus 1 source imported
- [x] Independent repository established
- [x] Netlify static deployment configuration added
- [x] Production response headers added
- [ ] Runtime/mock/external dependency audit
- [ ] Full responsive QA
- [ ] Accessibility audit
- [ ] Production endpoint verification
- [ ] Final visual regression pass
