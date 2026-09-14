# Fānus Blueprint — Architecture

## Boundary

Fānus Blueprint is a **presentation and observability surface**. It is not the canonical implementation of the Fānus engine.

```
                    ┌─────────────────────────┐
                    │   Fanus-Living-Seal     │
                    │   canonical core        │
                    └────────────┬────────────┘
                                 │
             ┌───────────────────┼───────────────────┐
             │                   │                   │
             ▼                   ▼                   ▼
     fanus-presence         fanus-app        fanus-blueprint
     presence/runtime      application      visual/observability
             │                   │                   │
             └───────────────────┴───────────────────┘
                                 │
                                 ▼
                         fanus1.netlify.app
```

## Runtime layers

1. **Presentation** — semantic HTML, CSS, responsive layout and motion.
2. **Browser interaction** — Three.js, GSAP, Chart.js and local Web Crypto interactions.
3. **External integrations** — GitHub REST reads and the configured Fanus demo API.
4. **Demonstration state** — client-side mock/demo flows that must remain visibly classified as simulated.

## Source of truth

The repository contains one production entrypoint:

`index.html`

The file is intentionally standalone at this stage. Framework migration is a later engineering decision, not part of the initial preservation migration.

## Integrity rules

- Do not move canonical engine logic into this repository.
- Do not describe simulated telemetry as production telemetry.
- Do not embed secrets in browser code.
- Keep external endpoints explicit.
- Preserve the visual language unless a redesign is intentional.
- Treat every external dependency as replaceable infrastructure.

## Deployment

Netlify serves the repository root directly. There is no build step.

```
main → Netlify → fanus1.netlify.app
```
