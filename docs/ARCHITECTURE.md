# Architecture

## Architektonický cíl

Postavit bezpečný, auditovatelný a snadno měnitelný modulární monolit, který zvládne placené piloty bez předčasné distribuované složitosti.

## Doporučený stack

- **Monorepo:** pnpm workspaces
- **Web:** Next.js, React, TypeScript, Tailwind CSS
- **API:** NestJS, TypeScript
- **Databáze:** PostgreSQL
- **ORM:** Prisma
- **Objektové úložiště:** S3-compatible storage v EU regionu
- **Fronta:** jednoduchá job queue pro zpracování dokumentů
- **Observability:** strukturované logy, error tracking, metriky
- **Testy:** unit, integration a Playwright pro hlavní workflow
- **Lokální provoz:** Docker Compose

Konkrétní poskytovatelé jsou otevřené rozhodnutí. Výběr musí respektovat bezpečnost, cenu pilotu, datovou lokalitu a jednoduchost provozu.

## Struktura repozitáře

```text
apps/
  web/
  api/
  worker/
packages/
  database/
  curriculum-domain/
  ui/
  config/
  testing/
docs/
samples/
  synthetic/
```

`worker` může v prvním kroku běžet ve stejném deploymentu, pokud je rozhraní oddělené a dlouhé úlohy neblokují HTTP request.

## Moduly backendu

```text
auth
organizations
memberships
projects
documents
extraction
frameworks
mappings
findings
comments
exports
audit
ai-orchestration
operations
```

Každý modul obsahuje controller, service/use cases, DTO, persistence adapter a testy. Doménová pravidla nesmí být rozptýlena pouze v controllerech.

## Hranice systému

### Web

- prezentace a interakce,
- žádná bezpečnostní autorita,
- optimistické UI pouze s jasným potvrzením serveru,
- žádné tajné klíče,
- citlivý obsah neposílat do klientských analytických služeb.

### API

- autentizace a autorizace,
- validace vstupů,
- doménová pravidla,
- řízení stavů projektu,
- auditní události,
- generování podepsaných upload/download odkazů.

### Worker

- extrakce textu,
- segmentace struktury,
- AI/rule processing,
- tvorba exportů,
- opakovatelné a idempotentní joby,
- timeouty a retry policy.

### Databáze

- zdroj pravdy pro strukturovaná data,
- tenant scoping,
- transakce pro důležitá rozhodnutí,
- append-only historie schválení,
- soft-delete pouze tam, kde dává doménový smysl.

### Object storage

- originální dokumenty,
- odvozené artefakty,
- exporty,
- šifrování,
- krátkodobé podepsané odkazy,
- lifecycle a řízené smazání.

## Multitenancy

Pro MVP shared database + shared schema s povinným `organizationId`.

Pravidla:

- tenant context vzniká na serveru z autentizovaného membershipu,
- klient nesmí být autoritou pro `organizationId`,
- všechny repository metody vyžadují tenant scope,
- testy musí dokazovat nemožnost cross-tenant čtení a zápisu,
- interní support access je explicitní, časově omezený a auditovaný.

Pozdější RLS je možné doplnit jako druhou obrannou vrstvu. Nesmí nahrazovat aplikační autorizaci.

## Document pipeline

```text
UPLOAD_REQUESTED
→ UPLOADED
→ VALIDATING
→ EXTRACTING
→ SEGMENTING
→ CLASSIFYING
→ READY_FOR_REVIEW
```

Při chybě:

```text
FAILED_RETRYABLE | FAILED_NEEDS_USER | FAILED_FINAL
```

Každý krok je idempotentní a ukládá:

- vstupní verzi,
- status,
- čas,
- chybu v interním formátu,
- bezpečnou uživatelskou zprávu,
- použité nástroje/modely.

## AI orchestrace

AI není volána přímo z controlleru.

Vrstva orchestrace řeší:

- verzi promptu,
- výběr modelu,
- redakci vstupu,
- strukturovaný výstup,
- validaci schématu,
- retry,
- náklady,
- audit,
- fallback na ruční zpracování.

Výstup modelu je vždy nedůvěryhodný vstup, který musí projít validací.

## API principy

- REST je pro MVP dostatečný,
- OpenAPI generované z DTO,
- explicitní stavy a idempotency key u dlouhých operací,
- pagination u seznamů,
- problem-details styl pro chyby,
- žádné generické endpointy typu `/execute`.

## Verzování

Verzovat:

- framework data,
- source documents,
- extraction pipeline,
- prompt templates,
- AI model run,
- export snapshots,
- významné doménové kontrakty.

Starý export musí být dohledatelný vůči tehdejší verzi dat.

## Testovací strategie

### Unit

- doménové invariants,
- stavové přechody,
- scoring a status mapping,
- permission resolution.

### Integration

- Prisma + PostgreSQL,
- tenant isolation,
- upload metadata,
- job idempotence,
- audit append.

### Contract

- struktura AI výstupu,
- framework importer,
- export schema.

### E2E

Kritický Playwright scénář:

1. přihlášení koordinátora,
2. vytvoření projektu,
3. upload syntetického dokumentu,
4. kontrola struktury,
5. přijetí a odmítnutí vazby,
6. vyřešení nálezu,
7. export.

## Deployment

Pro pilot preferujeme co nejmenší počet provozních částí:

- web/API,
- worker,
- managed PostgreSQL,
- object storage.

Preview prostředí nesmí používat produkční dokumenty. Produkční migrace musí být forward-compatible a mít plán obnovy.

## Zakázaná předčasná složitost

Bez doložené potřeby nevzniknou:

- mikroservisy,
- Kubernetes,
- event sourcing celého systému,
- vlastní identity provider,
- vlastní vector database jako výchozí volba,
- plugin marketplace,
- multi-region deployment,
- native mobile backend.
