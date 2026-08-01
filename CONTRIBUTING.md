# Contributing to SkillStorm Curriculum

## Základní pravidlo

Každá změna musí zlepšit hlavní kurikulární workflow, snížit zásadní riziko nebo vytvořit ověřitelný obchodní důkaz. Technická zajímavost sama o sobě nestačí.

## Git workflow

- `main` — stabilní a zkontrolovaná verze
- feature větev — `feat/<kratky-nazev>`
- fix větev — `fix/<kratky-nazev>`
- dokumentace — `docs/<kratky-nazev>`
- bezpečnostní oprava — `security/<kratky-nazev>`

Změny se standardně dostávají do `main` přes pull request.

## Commit messages

Používej Conventional Commits:

- `feat:` nová uživatelská schopnost
- `fix:` oprava chyby
- `docs:` dokumentace
- `test:` testy
- `refactor:` změna struktury bez změny chování
- `security:` bezpečnostní hardening nebo oprava
- `chore:` údržba

Commit má být logický a reverzibilní. Necommituj rozpracované náhodné směsi změn.

## Před zahájením funkce

Musí existovat:

- uživatelský problém,
- cílová persona,
- očekávaný výsledek,
- vazba na `MVP-SCOPE.md` nebo schválené rozhodnutí,
- akceptační kritéria,
- bezpečnostní a datový dopad,
- plán testu.

Pokud funkce rozšiřuje scope, nejdřív se aktualizuje `DECISION-LOG.md` a relevantní produktová dokumentace.

## Pull request

PR má obsahovat:

- proč změna vzniká,
- co se mění,
- co se výslovně nemění,
- screenshoty nebo video u UI,
- testy a jejich výsledek,
- migrace a rollback, pokud existují,
- bezpečnostní dopad,
- známá omezení,
- navazující práci.

## Definition of Done

Změna není hotová, dokud:

- splňuje akceptační kritéria,
- TypeScript prochází bez obcházení typů,
- testy procházejí,
- autorizace je ověřena na serveru,
- cross-tenant scénář je otestován u tenantových dat,
- chybové stavy mají srozumitelnou nápravu,
- UI funguje klávesnicí,
- citlivá data nejsou v logách,
- auditní událost existuje tam, kde je nutná,
- dokumentace odpovídá realitě,
- nejsou ponechány trvalé TODO bez vlastníka.

## TypeScript

- žádný nový JavaScript,
- nepoužívat `any` bez zdůvodněné výjimky,
- validovat runtime vstupy,
- sdílené typy nesmí nahrazovat API kontrakt,
- doménové enumy a stavy mají jasné přechody,
- nullable hodnoty musí mít doménový význam.

## Frontend

- komponenty PascalCase,
- funkce a proměnné camelCase,
- server je autorita pro oprávnění,
- jedna hlavní akce na obrazovku,
- žádný význam pouze barvou,
- loading, empty, error a success stav jsou povinné,
- formuláře zachovají data při chybě,
- technické chyby se nepředávají uživateli.

## Backend

Každý modul odděluje:

- controller / transport,
- use case nebo service,
- doménová pravidla,
- persistence,
- DTO a validaci.

Controllery nesmí obsahovat hlavní doménovou logiku. Repository metoda pro tenantová data musí vyžadovat organization scope.

## Databáze a Prisma

- jedna centrální schema definice v database package,
- každá změna má migraci,
- migrace je zkontrolovaná před commitem,
- destructive změna má plán dat a rollback,
- indexy odpovídají reálným query patternům,
- referenční rámce a schválení se nepřepisují bez verze,
- seed používá pouze syntetická data.

Po změně schématu:

```sh
pnpm prisma migrate dev --name <popis_zmeny>
pnpm prisma generate
```

Přesný workspace příkaz se upraví po inicializaci monorepa.

## Testovací minimum

### Každá doménová změna

- unit test invariantů,
- negativní scénář,
- autorizace podle role a tenantu.

### Každý endpoint

- validní vstup,
- nevalidní vstup,
- chybějící oprávnění,
- cizí organizace,
- neexistující entita.

### Každý kritický UI flow

- loading,
- prázdný stav,
- chyba s nápravou,
- úspěch,
- obnovení stránky,
- klávesnice.

### E2E release gate

Hlavní cesta od vytvoření projektu po export musí procházet v reálném browseru nad reálným API a databází.

## AI změny

Změna promptu, modelu nebo preprocessing pipeline vyžaduje:

- verzi,
- eval proti schválenému datasetu,
- porovnání s předchozí verzí,
- kontrolu schema validation,
- kontrolu zdrojovosti,
- nákladový dopad,
- rollback.

Výstup modelu nikdy nepřechází přímo do schválených doménových dat.

## Bezpečnostní review

Povinné u změn týkajících se:

- autentizace,
- autorizace,
- uploadu a downloadu,
- object storage,
- AI providerů,
- exportů,
- audit logu,
- retence a smazání,
- secrets,
- cross-tenant query.

## Dokumentace

Při změně produktu uprav odpovídající dokument:

- scope → `MVP-SCOPE.md`
- UX → `UX-UI-PRINCIPLES.md` nebo `PRIMARY-USER-FLOW.md`
- doména → `DOMAIN-MODEL.md`
- architektura → `ARCHITECTURE.md`
- bezpečnost → `SECURITY-PRIVACY.md`
- AI → `AI-GOVERNANCE.md`
- obchod → `BUSINESS-MODEL.md`
- rozhodnutí → `DECISION-LOG.md`

Kód a dokumentace se nesmí dlouhodobě rozcházet.

## Zakázané praktiky

- secrets v repozitáři,
- reálné školní dokumenty v fixtures,
- force push do sdílené větve bez dohody,
- bypass CI kvůli termínu,
- autorizace pouze ve frontendu,
- skryté automatické schválení AI návrhu,
- zakomentované bloky starého kódu,
- „TODO navždy“,
- scope creep bez rozhodnutí.
