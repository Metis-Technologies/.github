---
name: struct-audit
description: Analisi strutturale del codebase — god-file, helper duplicati, codice condiviso non estratto, cicli. Usa quando l'utente chiede tech-debt scan, "dove sono i file grossi", o un audit di struttura.
---

# struct-audit — salute strutturale del codice

Riproduce l'analisi usata in BF-31/36 (dedup) e nei tracker tech-debt.

## Cosa misurare

1. **God-file**: file più grandi per LOC, **escludendo** generati/l10n (`*.g.dart`, `*.freezed.dart`, `messages/`, `*.gen.ts`, build). Soglia di attenzione: file che concentrano complessità sproporzionata.
2. **Helper duplicati**: funzioni/blocchi byte-identici ripetuti (es. `buildOrderBy`, mapping). Candidati a estrazione.
3. **Codice condiviso non estratto**: in beautyflow, file con path identico tra `apps/dashboard/src` e `apps/webapp/src` (target: `packages/`). In agent-engine, duplicazioni server↔dashboard.
4. **Confini architetturali**: violazioni (`core/` che importa da `features/` nel mobile; controller non sottili nel server).
5. **Codice morto**: export/tipi inutilizzati (`knip` per i TS, `flutter analyze` per Dart) — ma **gated su CI verde**, mai cancellazioni cieche.

## Output

Lista prioritizzata di interventi **a fette piccole** (mai mega-PR), pronti da aprire come ticket nel progetto `Tech Debt & Cleanup` con la skill `linear-issue`. Per ogni voce: file, problema, intervento proposto, rischio.
