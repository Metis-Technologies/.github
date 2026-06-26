---
name: api-sec-review
description: Review di sicurezza white-box dell'API NestJS (OWASP API Top 10) con focus multi-tenant. Usa quando l'utente chiede un audit di sicurezza, prima di una release, o tocca auth/guard/controller sensibili.
---

# api-sec-review — OWASP API security pass

Per `beautyflow/apps/server` e `metis-agent-engine/apps/server` (NestJS + Fastify + Prisma).

## Checklist (OWASP API Top 10, adattata)

1. **BOLA/BFLA** (la #1 storica): ogni accesso ai dati filtrato per `tenantId`; nessun endpoint che fida l'ID risorsa dal client senza cross-check tenant. Nei servizi `tenantId` è il primo argomento; nei controller arriva da `req.user.tenantId`.
2. **Auth**: JWT con **algoritmo pinnato** (no `alg:none`/confusion), scadenza, cookie httpOnly dove applicabile, rate-limit sugli endpoint auth.
3. **Mass assignment / input**: `ValidationPipe` con `whitelist` + `forbidNonWhitelisted` globale; DTO tipizzati; sanitizzazione.
4. **Error/info leak**: messaggi di validazione dettagliati **disabilitati in produzione**; niente stack trace; Swagger non esposto in prod.
5. **Secrets**: solo via `CredentialsService` (AES-256-GCM in agent-engine); mai loggati, mai restituiti dalle API, mai esposti al modello LLM.
6. **Rate limit / headers**: ThrottlerGuard globale, Helmet, CORS ristretto all'origine dashboard.

## Metodo

White-box: leggi guard, pipe globali, controller sensibili (POS, prenotazioni, credenziali). Confronta con l'audit esistente (`docs/SECURITY_AUDIT_*.md`) per non riaprire cose già chiuse. Output: findings con severità (H/M/L), file:riga, fix. Apri ticket nel progetto `Production Hardening` (label `security`).
