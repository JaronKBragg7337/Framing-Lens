# Framing Lens — v3 (final, with corrections)

Version: v3  
Created: 2026-01-08  
Author: Jaron K. Bragg  
License: CC0 1.0 Universal (Public Domain)

## Overview

Framing Lens is a mobile-first perspective / framing exercise system that converts ambiguous prompts into structured, descriptive response patterns. This repository contains a default implementation and documentation for a session-first MVP: prompt sets, interpretation rules, modular outputs, and policy-driven sharing. Defaults are intended to be adaptable — environments and teams are encouraged to remix prompts, outputs, and policies to fit their context.

This file summarizes the v3 release and points to canonical docs included in this repository.

## What's included (top-level)

- README.md — project overview and quick notes
- LICENSE — CC0 1.0 (public domain)
- docs/ — canonical documentation and artifacts:
  - docs/PROMPT_SET_v3.md — canonical prompt set (v3)
  - docs/OUTPUT_MODULES.md — modular result types and examples
  - docs/WIREFLOW.md — screens and session-first user flow
  - docs/ROUTES_API.md — pages and API endpoints for the MVP
  - docs/DATA_MODEL.md — planned data model and tables
  - docs/POLICY_MODEL.md — session and environment policy model
  - docs/SCORING_ENGINE.md — rules-based scoring / signal engine
  - docs/ROADMAP.md — roadmap and optional extension tracks

## Quick summary (what this repo delivers)

- Session-first flow (Landing → Session setup → Prompts → Results)
- Versioned prompt sets (v3 included)
- Rules-based, interpretable scoring engine (dimension indicators, pattern descriptions)
- Modular output assembly (core modules + optional modules)
- Policy model for sharing, identity, and retention that environments can configure

## Prompt Set v3 (high level)

- Designed as a short, mobile-friendly exercise to surface how people respond to ambiguity.
- Each prompt requires structured answers in the exact format specified in `docs/PROMPT_SET_v3.md`:
  1. Choice
  2. Reason (1–2 sentences)
  3. First step (1 sentence)
  4. Risk / blind spot (1 sentence)
  5. Optional rewrite (1 sentence)
- Responses feed a rules-based scoring engine that produces normalized indicators and observational language.

Read the full prompt set here: [docs/PROMPT_SET_v3.md](./docs/PROMPT_SET_v3.md)

## Policy & Privacy

Policy is configurable per session. Key session policy fields:
- share_mode: "private" | "link_view" | "public" | "collaborative"
- identity_mode: "anonymous" | "named_optional" | "named_required"
- export_mode: "off" | "on"
- retention_mode: "indefinite" | "days:N" | "environment_default"

See the full policy model for preferred tone and copy rules: [docs/POLICY_MODEL.md](./docs/POLICY_MODEL.md)

## Data model & API

Planned database tables and API endpoints are documented in:
- [docs/DATA_MODEL.md](./docs/DATA_MODEL.md)
- [docs/ROUTES_API.md](./docs/ROUTES_API.md)

API endpoints (MVP):
- POST /api/session
- POST /api/response
- POST /api/session/complete
- GET /api/session/[id]/results
- GET /api/share/[token]
- GET /api/public/[slug]

## Scoring & Outputs

- The scoring engine is rules-based and interpretable (see [docs/SCORING_ENGINE.md](./docs/SCORING_ENGINE.md)).
- Core outputs: dimension indicators and pattern description.
- Optional modules: context-specific suggestions, relational mapping, development paths, raw export, etc.
- Outputs are assembled per-session according to chosen modules and policy.

## Roadmap (summary)

Core MVP is included. Extension tracks and features to consider:
- Cohort collection & aggregate views
- Workspaces & team dashboards
- Prompt remixing and versioning
- Publishing / collaborative modes
- Integrations, temporal analysis, localization

See the full roadmap: [docs/ROADMAP.md](./docs/ROADMAP.md)

## How to use (developer quick start)

1. Clone the repo.
2. Review docs to adapt prompts, outputs, and policy to your environment.
3. Implement the Next.js app (App Router) with the session-first flow; endpoints are specified in `docs/ROUTES_API.md`.
4. Store session and response data in Postgres (Supabase/Neon recommended).
5. Use the rules in `docs/SCORING_ENGINE.md` to generate indicators and assemble modules described in `docs/OUTPUT_MODULES.md`.

(Commands and a full local dev quick start can be added to README when the app code exists.)

## Contribution & Remixing

This project is public domain (CC0). Use, fork, and remix however you like. If you collaborate or contribute back, helpful things to include:
- Clear changelog entries for prompt edits and new modules
- Tests or examples demonstrating interpretation rules
- Example exports or sample sessions for QA

## Changelog — v3 (high level)

- Canonicalized prompt set (v3) and required answer format
- Consolidated docs for policy, routes, data model, scoring, and outputs
- Clarified modular output approach and pairing strategies
- Added explicit session policy fields and copy rules
- License set to CC0

## Notes / Author

Created by Jaron K. Bragg. This default implementation is intentionally adaptable — environments and teams should feel empowered to change prompts, scoring rules, output modules, and policy to fit their context and goals.

License: CC0 1.0 Universal — public domain dedication. Use it however you want. See LICENSE file.
