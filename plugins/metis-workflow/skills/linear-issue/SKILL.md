---
name: linear-issue
description: Crea un issue Linear ben formato nel team giusto (BF o BFM) con label e progetto corretti. Usa quando l'utente dice "apri un ticket", "crea issue Linear", "tracciamolo".
---

# linear-issue — issue Linear conforme

Usa i tool MCP Linear (`mcp__Linear__*`).

## Team

- **BF** (BeautyFlow) → repo `beautyflow` (server/dashboard/webapp/ui).
- **BFM** (BeautyFlow-mobile) → repo `beautyflow-mobile`.
- `metis-agent-engine` e `metis-website` **non hanno team Linear** (piano Free): traccia con **GitHub Issues**, non Linear.

## Formato

- **Titolo**: `<type>(scope?): <descrizione>` in italiano (es. `feat(webapp): structured data LocalBusiness`).
- **Label**: `type:feat|fix|chore|docs|refactor` + `area:server|dashboard|webapp|ui|infra` (BF) o area mobile (BFM) + `tech-debt`/`security`/`performance` quando pertinente.
- **Progetto**: `Roadmap Features` (nuove feature), `Tech Debt & Cleanup` (refactor/pulizia), `Production Hardening` (security/perf/observability).
- **Descrizione strutturata**: `## Problema` / `## Intervento` (o `## Contesto`), con riferimenti `file:riga` e, se utile, una tabella degli impatti. Tono tecnico e verificabile, come negli issue esistenti.
- **Assegnatario**: chi lo lavora (Leo o Giancarmelo); **priorità** coerente (High per security/bloccanti).

Prima di creare, controlla i duplicati con `list_issues`/`search`.
