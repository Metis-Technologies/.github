---
name: ship
description: Crea branch + commit + push + PR seguendo le convenzioni Metis (ticket Linear per BF/BFM, ticketless per agent-engine/website). Usa quando l'utente dice "fai commit e pr", "shippa", "apri la PR", "manda in review".
---

# ship — shipping conforme alle convenzioni Metis

Riconosci il repo corrente e applica la convenzione giusta.

## beautyflow (team Linear `BF`) e beautyflow-mobile (`BFM`)

Usa lo script del repo:

```sh
scripts/commit-and-pr.sh "<type>: <descrizione>"          # crea il ticket Linear
scripts/commit-and-pr.sh "<type>: <descrizione>" --ticket BF-42   # riusa un ticket
```

Effetto: ticket Linear → branch `feature|fix|chore/<KEY>-<N>` → commit `<KEY>-<N> <type>: …` → push → PR verso `develop`.

## metis-agent-engine e metis-website (no team Linear, piano Free)

Usa l'helper ticketless del repo (`scripts/ship.sh` per agent-engine; per metis-website segui la stessa logica a mano):

```sh
scripts/ship.sh "<type>: <descrizione>"
```

Effetto: branch `feature|fix|chore/<slug>` → commit Conventional → push → PR. **Niente ticket Linear** finché il workspace è su Free.

## Regole invarianti

- `type` ∈ `feat`, `fix`, `chore`, `docs`, `refactor`, `test` (+ `build`/`ci`/`perf`/`style` dove ammesso dal repo).
- **Mai** push diretto su `main`/`staging`/`develop`. **Mai** `--base staging` senza conferma esplicita dell'utente.
- Prima di shippare: lint/test/typecheck dell'app toccata **verdi**.
- Mai committare secret. Solo modifiche chirurgiche già concordate.
- Le naming/branch rule complete e il piano di migrazione Linear futura sono in `.github-private/profile/README.md`.
