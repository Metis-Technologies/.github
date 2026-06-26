---
name: seo-audit
description: Audit SEO/GEO/AEO di una pagina o app (metadata, structured data, sitemap, robots, hreflang). Usa quando l'utente chiede un audit SEO, "perché non indicizza", o lavora su pagine money della webapp/sito.
---

# seo-audit — audit SEO / GEO / AEO

Riproduce l'audit usato negli issue BF-46/47/48. Lavora sia su URL live sia sul sorgente Next.js.

## Cosa verificare

1. **Crawlability**: `robots.txt` (200, `Sitemap:` presente), `sitemap.xml` (200, `application/xml`, URL validi), redirect/locale (`/` → `/it/`), status code.
2. **Metadata per pagina**: `generateMetadata` presente sulle pagine money (`business/[slug]`, `city/[slug]`, landing); `<title>`/description specifici (non quelli generici del layout); canonical; `hreflang` per le lingue.
3. **Open Graph / Twitter**: `og:title/description/image`, `twitter:card`.
4. **Structured data (GEO/AEO)**: JSON-LD `LocalBusiness`/`BeautySalon` sulle schede business, `BreadcrumbList`, `Organization`/`WebSite` sul sito. Validare la sintassi.
5. **Performance/CWV** se rilevante (LCP, immagini `next/image` AVIF/WebP).

## Output

- Tabella punteggi **SEO / GEO / AEO** su /10 + totale /30.
- Lista fix prioritizzata, ognuno azionabile (file da toccare).
- Se l'utente vuole, apri gli issue con la skill `linear-issue` (team BF) o GitHub Issues (metis-website).

Non toccare gli identificatori legacy `stylelist`/`wueba.it` (URL/worker/DB in produzione).
