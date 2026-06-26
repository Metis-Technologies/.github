---
name: linear-triage
description: Routine di triage degli issue Linear (label, progetto, priorità, stale). Pensata per un giro ricorrente giornaliero. Usa quando l'utente dice "fai triage", "sistema i ticket nuovi", o la esegui da una sessione schedulata.
---

# linear-triage — triage ricorrente Linear

Usa i tool MCP Linear. Copri i team **BF** e **BFM**.

## Passi

1. **Nuovi/aggiornati** nelle ultime 24h (`list_issues` con `updatedAt: -P1D`).
2. Per ognuno senza metadati completi:
   - assegna `type:*` e `area:*` dal titolo/descrizione;
   - assegna **progetto** (`Roadmap Features` / `Tech Debt & Cleanup` / `Production Hardening`);
   - imposta **priorità** (High per security/bloccanti, altrimenti coerente col contenuto);
   - se manca l'assegnatario e l'autore lo sta lavorando, assegnalo all'autore.
3. **Stale**: issue `In Progress` fermi da > 7 giorni → segnala (non chiudere).
4. **Duplicati sospetti**: segnala, non unire automaticamente.

## Output

Digest sintetico: quanti triagati, cosa è stato cambiato, lista stale, eventuali dubbi da decidere a mano. Se l'utente vuole, posta il digest su Discord. **Non** inventare cambi non supportati dal contenuto dell'issue: nel dubbio, lascia e segnala.
