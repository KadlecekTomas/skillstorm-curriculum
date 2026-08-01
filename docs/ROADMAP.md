# Roadmap

## Princip

Roadmapa není seznam funkcí. Je to sled rozhodovacích bran. Další fáze se neotevře pouze proto, že předchozí práce byla naprogramována.

## Fáze 0 — Product foundation

### Výstupy

- produktová doktrína,
- problémové hypotézy,
- nabídka pilotu,
- MVP scope,
- UX pravidla,
- doménový model,
- bezpečnostní baseline,
- rozhodovací metriky.

### Gate

- dokumentace je interně konzistentní,
- hlavní workflow je jednoznačné,
- scope neobsahuje žákovská data ani SIS funkce,
- tým umí jednou větou popsat prodávaný výsledek.

## Fáze 1 — Problem discovery

### Cíl

Ověřit problém a nákupní realitu dříve, než vznikne rozsáhlý produkt.

### Práce

- 15–20 rozhovorů,
- mapování současného postupu,
- evidence času a workaroundů,
- identifikace vlastníka a schvalovatele,
- ověření reakce na cenu,
- získání bezpečných syntetických nebo schválených vzorků.

### Gate

Pokračujeme, pokud:

- alespoň polovina relevantních škol řeší konkrétní projekt s vlastníkem,
- opakují se stejné nákladné kroky,
- existuje realistický nákupní proces,
- alespoň tři školy projeví závazný zájem o placený pilot.

## Fáze 2 — Concierge prototype

### Cíl

Dodat hodnotu částečně ručně a zjistit, co skutečně automatizovat.

### Práce

- bezpečný příjem dokumentu,
- interní extrakční skripty nebo nástroje,
- ručně kontrolované mapování,
- jednoduchý review prototyp,
- ručně vytvořený export,
- měření času na každém kroku.

### Gate

- alespoň 3 placené piloty,
- výstup je pro školu použitelný,
- ruční služba ukazuje opakovatelný proces,
- škola získá významnou úsporu,
- tým rozumí nejčastějším typům chyb.

## Fáze 3 — Pilot MVP

### Cíl

Automatizovat nejnákladnější opakující se části a umožnit uživateli vlastní kontrolu.

### Epic pořadí

1. foundation monorepo, CI a environments,
2. organization/auth/tenant isolation,
3. project workflow,
4. secure document upload,
5. extraction pipeline,
6. structure review,
7. framework version import,
8. mapping suggestions,
9. human decisions and findings,
10. exports and audit,
11. observability, backups and pilot operations,
12. Playwright critical journey.

### Gate

- uživatel dokončí průchod bez vývojáře,
- cross-tenant testy procházejí,
- AI návrhy mají zdroje a schválení,
- export odpovídá rozhodnutím,
- obnova ze zálohy je otestovaná,
- alespoň 5 placených pilotů nebo ekvivalentně silný důkaz.

## Fáze 4 — Repeatability

### Cíl

Snížit interní práci na jeden pilot a dokázat opakovatelné nasazení.

### Práce

- onboarding bez ručního zásahu vývojáře,
- standardizované importní profily,
- lepší fronta nejasností,
- šablony exportů,
- provozní dashboard bez obsahu dokumentů,
- billing a smluvní standard,
- support runbook.

### Gate

- klesá interní čas na projekt,
- kvalita neklesá,
- školy dokončují workflow,
- existuje pokračující použití po prvním auditu,
- produkt má pozitivní contribution margin při realistické ceně.

## Fáze 5 — Curriculum workspace

Otevírá se pouze tehdy, když školy chtějí pokračující práci.

Možné schopnosti:

- změnové řízení,
- schvalovací workflow,
- dopadová analýza,
- dlouhodobé verze ŠVP,
- odpovědnosti předmětových týmů,
- aktualizace při nové verzi rámce.

## Fáze 6 — Evidence layer

Pouze po ověření workspace:

- vazby na materiály a plány,
- evidence realizace kurikula,
- importy z dalších systémů,
- analytika na úrovni kurikula.

Tato fáze nesmí automaticky sklouznout k hodnocení jednotlivých žáků.

## Fáze 7 — Internationalization

Podmínky:

- český product-market fit,
- obecný framework engine,
- partner nebo jasný vstupní kanál v cílové zemi,
- právní a terminologická analýza,
- lokální validační dataset.

Nejprve jeden další trh, nikoliv „celá Evropa“.

## Zakázané paralelní proudy před Gate 3

- mobilní aplikace,
- student portal,
- parent portal,
- gamifikace,
- marketplace,
- plný LMS,
- docházka a známky,
- více zemí,
- rozsáhlé integrace.

## Release zásady

Každá fáze má:

- ownera,
- měřitelný výsledek,
- akceptační kritéria,
- bezpečnostní review,
- UX test,
- rozhodnutí `GO / ADJUST / STOP`.

„Ještě jeden sprint“ není náhradou za rozhodnutí.
