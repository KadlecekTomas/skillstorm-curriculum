# Success Metrics

## Princip

Metriky musí řídit rozhodnutí. Vanity metrics nesmí zakrýt, že školy neplatí, nedokončují workflow nebo nevěří výsledku.

## North Star Metric

**Počet dokončených, lidsky schválených kurikulárních projektů, které škole prokazatelně ušetřily významný čas.**

Samotný počet uploadů ani AI návrhů není hodnotou.

## Obchodní metriky

### Discovery

- počet relevantních rozhovorů,
- podíl respondentů s konkrétním projektem a termínem,
- podíl s identifikovaným vlastníkem,
- počet žádostí o nabídku,
- počet placených pilotů,
- konverze nabídka → objednávka,
- skutečná realizovaná cena.

### Pilot

- hrubý příjem z pilotu,
- interní čas na pilot,
- externí náklady na zpracování,
- contribution margin,
- doba od objednávky k výsledku,
- podíl pilotů dokončených v dohodnutém rozsahu.

### Retence

- podíl škol, které pokračují po auditu,
- důvod pokračování,
- ochota přejít na opakovanou platbu,
- doporučení konkrétní další škole.

## Produktové metriky

### Aktivace

Uživatel je aktivovaný, když:

1. vytvořil projekt,
2. nahrál validní dokument,
3. potvrdil první část struktury,
4. udělal první rozhodnutí o vazbě.

Měříme:

- čas do aktivace,
- podíl pozvaných uživatelů, kteří se aktivují,
- místo nejčastějšího odchodu.

### Dokončení workflow

- podíl projektů s dokončenou strukturou,
- podíl projektů s vyřešenými blokujícími nálezy,
- podíl projektů s exportem,
- čas v každém kroku,
- počet návratů kvůli chybě systému.

### Kvalita návrhů

- acceptance rate,
- edit rate,
- rejection rate,
- počet závažně chybných návrhů,
- precision na validačním setu,
- podíl položek předaných specialistovi,
- podíl návrhů bez dostatečného zdroje.

Acceptance rate sama o sobě může být zavádějící. Musí se kombinovat s auditem kvality a závažností chyb.

### UX

- čas do pochopení prvního kroku,
- task completion rate,
- počet žádostí o pomoc,
- počet nevratných chyb,
- počet obrazovek bez dalšího jasného kroku,
- SUS nebo jiná jednoduchá standardizovaná zpětná vazba až při větším vzorku,
- kvalitativní výrok: „dokázal/a bych to příště udělat sám/sama“.

## Hodnotové metriky

Před a po pilotu se odhaduje:

- počet hodin práce školy,
- počet lidí zapojených do koordinace,
- počet ručně kontrolovaných položek,
- počet nalezených problémů, které současný postup neodhalil,
- čas do použitelného výstupu.

Úspora času musí být doložena popisem baseline, ne pouze dojmem po prezentaci.

## Bezpečnostní metriky

- cross-tenant incidenty: cíl 0,
- neoprávněné přístupy: cíl 0,
- dokumenty v logách nebo analytice: cíl 0,
- kritické neopravené zranitelnosti před pilotem: cíl 0,
- úspěšnost obnovovacího testu,
- čas revokace přístupu,
- počet support přístupů bez důvodu: cíl 0.

## AI safety metriky

- návrhy vydané jako schválené bez člověka: cíl 0,
- návrhy bez source reference: cíl 0,
- schema validation failure rate,
- prompt-injection test pass rate,
- počet změn modelu bez evaluace: cíl 0,
- počet nebezpečně sebevědomých chybných závěrů.

## Počáteční rozhodovací prahy

Tyto hodnoty jsou **DECISION** pro validační fázi:

- 15–20 relevantních rozhovorů,
- alespoň 3 placené piloty pro pokračování do pilotního MVP,
- cílově 5 placených pilotů pro silný signál,
- významná úspora: pracovní hypotéza alespoň 20 hodin na školu,
- přijaté nebo lehce upravené návrhy: pracovní hypotéza alespoň 80 % u podporovaného scope,
- závažné chybné návrhy: tak nízko, aby neohrožovaly důvěru; přesný práh vznikne z pilotních dat,
- pokračování po auditu: více než polovina pilotních škol jako silný SaaS signál.

Prahy se nesmí upravit zpětně pouze proto, aby projekt vypadal úspěšně.

## Kill criteria

Zvažujeme stop nebo zásadní pivot, když:

- po 20 kvalitních rozhovorech nevzniknou alespoň 3 placené piloty,
- většina škol chce pouze bezplatný nástroj,
- úspora je malá oproti nákladům,
- kvalita návrhů vyžaduje téměř úplnou ruční práci,
- školy výstupu nevěří ani při zdrojovosti a lidské kontrole,
- jednorázový audit nevytváří důvod k pokračování a služba nemá zdravou marži,
- bezpečné zpracování je ekonomicky neudržitelné.

## Reporting cadence

- discovery: týdenní evidence signálů,
- pilot: vyhodnocení po každé škole,
- produkt: týdenní operativní metriky,
- rozhodovací gate: písemné `GO / ADJUST / STOP` s důkazy.
