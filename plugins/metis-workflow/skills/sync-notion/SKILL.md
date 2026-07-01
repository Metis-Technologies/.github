---
name: sync-notion
description: Sincronizza roadmap/changelog/decisioni dai repo e da Linear verso il workspace Notion "Metis HQ". Usa quando l'utente dice "aggiorna Notion", "porta la roadmap su Notion", "logga la decisione".
---

# sync-notion — sincronizzazione verso Notion HQ

Usa i tool MCP Notion (`mcp__Notion__*`). Workspace: **Metis HQ**.

## Mappature

- **Roadmap**: Linear progetti `Roadmap Features` (BF + BFM) → pagina Notion *Roadmap & Implementazioni Future*. Riporta lo stato, non duplicare i dettagli tecnici.
- **Changelog / release**: PR mergiate su `develop`→`staging`→`production` (o `main`) → sezione release note della pagina prodotto.
- **Decision log**: ogni decisione strategica/architetturale → pagina *Decision log* (crearla se manca: context → opzioni → scelta → conseguenze). È un TODO esplicito nella checklist tooling.
- **Incident log**: outage/escalation/bug critico → pagina *Incident log*.

## Regole

- Non spostare/riscrivere pagine esistenti senza chiedere; **append** o aggiorna sezioni mirate.
- Scrivi in italiano, conciso, con link agli issue Linear/PR.
- Non copiare segreti o dati cliente in Notion.
- Le pagine business plan/financial sono sensibili: non modificarle salvo richiesta esplicita.
