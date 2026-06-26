---
name: weekly-digest
description: Genera l'update settimanale (PR mergiate + issue Done + commit) raggruppato per repo/area, da postare su Notion/Discord. Usa quando l'utente dice "fai il riepilogo della settimana", "update del venerdì", o la esegui da una sessione schedulata.
---

# weekly-digest — update settimanale async

Sostituisce il "Loom del venerdì" con un report scritto, a costo zero.

## Raccolta (ultimi 7 giorni)

- **Linear**: issue passati a `Done` nei team BF + BFM (`list_issues` con `state` Done, `updatedAt: -P7D`).
- **GitHub**: PR mergiate e commit rilevanti su `beautyflow`, `beautyflow-mobile`, `metis-website`, `metis-agent-engine` (tool MCP GitHub).

## Formato output

Markdown conciso, in italiano, raggruppato per **prodotto/repo** e poi per **area** (feature / fix / tech-debt / security / infra). Per ogni voce: una riga + link. In testa: 3-5 **highlight** della settimana. In coda: **in corso** (issue `In Progress`) e **prossimi** (Todo ad alta priorità).

## Destinazione

- Append in una pagina Notion *Weekly updates* (creala se manca) via skill `sync-notion`.
- Se richiesto, posta su Discord (canale dev).

Niente metriche inventate: se un dato non c'è, ometti la sezione.
