# SkillStorm Curriculum

> **Kontrolovatelný převod školního kurikula vůči závaznému vzdělávacímu rámci — bez dalšího školního informačního systému, bez dat žáků a bez zbytečné administrativy.**

SkillStorm Curriculum je úzce zaměřený produkt pro vedení škol a koordinátory ŠVP. Pomáhá převést existující školní vzdělávací program do strukturované mapy, porovnat jej s referenčním rámcem, označit nepokryté oblasti, duplicity a nejasnosti a připravit podklady pro lidské rozhodnutí.

Produkt **nenahrazuje odborný úsudek školy**. Automatizace navrhuje, člověk schvaluje a systém uchovává dohledatelnou historii rozhodnutí.

## Jediný počáteční workflow

```text
Nahrát ŠVP
  → rozpoznat strukturu dokumentu
  → potvrdit předměty a ročníky
  → navrhnout vazby na referenční rámec
  → ukázat mezery, duplicity a nejistoty
  → provést lidskou kontrolu
  → exportovat pracovní podklady
```

Dokud tento průchod nebude prokazatelně užitečný a placený, projekt nebude rozšiřován o LMS, žákovské účty, rodičovské účty, známkování, docházku, gamifikaci, chat ani mobilní aplikaci.

## Produktový slib

Uživatel musí bez školení pochopit:

1. kde právě je,
2. co má udělat,
3. proč to má udělat,
4. co se stane po kliknutí,
5. zda je jeho práce bezpečně uložená,
6. co ještě zbývá dokončit.

**Systém nese složitost. Uživatel ji nesmí nést za něj.**

## Stav projektu

Projekt je v etapě **product discovery + pilot definition**. Dokumentace rozlišuje:

- **doložené skutečnosti**,
- **pracovní hypotézy**,
- **rozhodnutí týmu**,
- **otevřené otázky k ověření**.

Za potvrzení obchodní hypotézy se nepovažuje pochvala, registrace ani bezplatné testování. Rozhodující signál je placený pilot a měřitelná úspora práce.

## Dokumentace

Začni v [`docs/INDEX.md`](docs/INDEX.md).

Klíčové dokumenty:

- [`docs/PRODUCT-DOCTRINE.md`](docs/PRODUCT-DOCTRINE.md) — neměnné produktové principy
- [`docs/PRODUCT-VISION.md`](docs/PRODUCT-VISION.md) — dlouhodobý směr a vstupní produkt
- [`docs/PILOT-OFFER.md`](docs/PILOT-OFFER.md) — nabídka prvního placeného pilotu
- [`docs/MVP-SCOPE.md`](docs/MVP-SCOPE.md) — co první verze smí a nesmí obsahovat
- [`docs/UX-UI-PRINCIPLES.md`](docs/UX-UI-PRINCIPLES.md) — zero-training UX pravidla
- [`docs/PRIMARY-USER-FLOW.md`](docs/PRIMARY-USER-FLOW.md) — detailní hlavní průchod
- [`docs/DOMAIN-MODEL.md`](docs/DOMAIN-MODEL.md) — doménové entity a jejich vztahy
- [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) — technická architektura
- [`docs/ROADMAP.md`](docs/ROADMAP.md) — pořadí práce a rozhodovací brány

## Pracovní zásady

- TypeScript bez JavaScriptu.
- Next.js pro web, NestJS pro API, PostgreSQL + Prisma pro data.
- Jedna změna = jedna jasná větev a logický commit.
- Vývoj začíná až po definování očekávaného uživatelského výsledku.
- Každá automatická analýza musí mít zdroj, míru jistoty a možnost lidské opravy.
- Žádná funkce nevstoupí do MVP pouze proto, že je technicky zajímavá.

## Měřítko úspěchu

Prvním cílem není „hotová platforma“. Prvním cílem je prokázat, že relevantní školy:

- mají naléhavý problém,
- rozumějí výstupu bez dlouhého vysvětlování,
- zaplatí za pilot,
- získají měřitelnou úsporu práce,
- důvěřují výsledku díky lidské kontrole a dohledatelnosti,
- mají důvod pokračovat i po prvotním převodu dokumentu.

## Licence a citlivost

Repozitář zatím neobsahuje licenci. Dokud nebude stanovena obchodní a licenční strategie, nepovažuje se obsah za open source.

Do repozitáře se nikdy necommitují skutečné dokumenty škol, osobní údaje, přístupové údaje ani produkční exporty.
