# metis-workflow — skill condivise Claude Code

Plugin con le skill ricorrenti del workflow Metis, riusabili in tutti i repo
dell'org (`beautyflow`, `beautyflow-mobile`, `metis-website`, `metis-agent-engine`).

## Installazione

Da Claude Code (una volta per macchina):

```
/plugin marketplace add Metis-Technologies/.github
/plugin install metis-workflow@metis
```

Le skill diventano disponibili come slash-command (`/ship`, `/linear-issue`, …)
e vengono anche suggerite dal modello quando il contesto le richiede.

## Skill incluse

| Skill | A cosa serve |
|---|---|
| `ship` | Branch + commit + push + PR secondo le convenzioni (ticket Linear per BF/BFM, ticketless per agent-engine/website). |
| `linear-issue` | Crea issue Linear ben formato (team BF/BFM) con label e progetto corretti. |
| `seo-audit` | Audit SEO/GEO/AEO (metadata, structured data, sitemap, robots, hreflang). |
| `struct-audit` | Salute strutturale: god-file, helper duplicati, codice condiviso non estratto. |
| `api-sec-review` | Pass di sicurezza OWASP API sull'API NestJS, focus multi-tenant. |
| `sync-notion` | Porta roadmap/changelog/decisioni su Notion "Metis HQ". |
| `linear-triage` | Triage ricorrente degli issue (label, progetto, priorità, stale). |
| `weekly-digest` | Update settimanale async (Linear Done + PR mergiate) per Notion/Discord. |

## Routine ricorrenti (Cowork)

`linear-triage` e `weekly-digest` sono pensate per girare **schedulate**. Due opzioni:

1. **Sessione Claude Code schedulata** (claude.ai/code): pianifica una sessione
   ricorrente che invoca `/linear-triage` (giornaliera) e `/weekly-digest`
   (venerdì). Nessun secret aggiuntivo: l'auth è lato Anthropic Console.
2. **GitHub Action** con `anthropics/claude-code-action`: richiede il secret
   `ANTHROPIC_API_KEY` a livello org (oggi **non** impostato — vedi
   `.github-private/profile/README.md`). Abilitare solo quando si vuole
   l'esecuzione headless in CI.

> Nota: non è stata aggiunta una Action schedulata "morta" che fallirebbe senza
> il secret. Si attiva consapevolmente quando decidete la cadenza.
