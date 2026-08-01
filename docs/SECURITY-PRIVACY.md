# Security & Privacy

## Bezpečnostní cíl

SkillStorm Curriculum pracuje s interními dokumenty školy. I když první verze nevyžaduje data žáků, dokumenty mohou obsahovat neveřejné informace. Bezpečnost je proto součást produktu, nikoliv pozdější doplněk.

Tento dokument je technická a produktová baseline. Nenahrazuje právní posouzení.

## Datová minimalizace

MVP nesmí vyžadovat:

- seznamy žáků,
- známky,
- docházku,
- zdravotní údaje,
- údaje rodičů,
- individuální vzdělávací výsledky.

Při nahrání systém upozorní, že uživatel nemá nahrávat osobní údaje, které nejsou pro audit nutné.

## Klasifikace dat

### Public

- veřejná produktová dokumentace,
- veřejné referenční rámce, pokud jejich použití dovolují podmínky.

### Internal

- provozní konfigurace bez tajemství,
- anonymizované metriky,
- interní metodiky.

### Confidential

- školní kurikulární dokumenty,
- mapování a komentáře,
- exporty,
- kontaktní údaje uživatelů.

### Restricted

- přístupové tokeny,
- hesla a recovery secrets,
- produkční encryption keys,
- případné osobní nebo zvláštní kategorie údajů nalezené ve vstupu.

## Tenant isolation

- každá doménová operace je scoped na organizaci,
- ID zaslané klientem nikdy nestačí k autorizaci,
- kontroluje se membership, role a oprávnění k projektu,
- existují negativní integrační testy cross-tenant přístupu,
- cache keys obsahují tenant scope,
- exporty a storage paths jsou oddělené.

## Autentizace

MVP:

- bezpečné hashování hesel pomocí moderního algoritmu,
- krátkodobé access tokeny nebo bezpečné serverové sessions,
- rotace refresh tokenů,
- revokace aktivních sessions,
- rate limiting a ochrana přihlášení,
- povinné ověření e-mailu,
- možnost vynutit MFA pro vlastníky a interní support.

SSO je pozdější schopnost, pokud jej vyžadují pilotní školy.

## Autorizace

Deny by default.

Role samy nestačí pro citlivé akce. Ověřuje se také:

- organizace,
- projekt,
- stav projektu,
- vlastnictví nebo přiřazení,
- typ operace.

Příklady:

- `VIEWER` nesmí měnit rozhodnutí,
- `REVIEWER` smí rozhodovat pouze v přiřazeném scope, pokud je omezen,
- `COORDINATOR` spravuje projekt, ale nemusí spravovat organizaci,
- support přístup vyžaduje důvod a audit.

## Dokumenty a úložiště

- upload přes krátkodobý podepsaný odkaz,
- kontrola MIME typu i skutečného formátu,
- limit velikosti,
- antivirová nebo malware kontrola,
- dokumenty nejsou veřejné,
- download odkazy mají krátkou platnost,
- šifrování při přenosu a v úložišti,
- náhodné storage keys bez původního názvu v cestě,
- původní dokument se neupravuje.

## Retence a smazání

Před pilotem se smluvně stanoví:

- délka uložení,
- kdo může požádat o smazání,
- zda se uchovává export,
- jak fungují zálohy,
- kdy jsou data definitivně odstraněna.

Smazání projektu musí řešit databázi, object storage, indexy, cache a odvozené artefakty. „Soft delete“ není samo o sobě splněním požadavku na výmaz.

## Logování

Logy nesmí obsahovat:

- hesla,
- access/refresh tokeny,
- celé dokumenty,
- celé AI prompty s citlivým obsahem,
- podepsané URL,
- zbytečné osobní údaje.

Logy mají obsahovat correlation ID, bezpečné entity ID, typ operace, stav a čas.

## Auditní stopa

Auditují se minimálně:

- přihlášení a citlivé změny účtu,
- vytvoření a archivace projektu,
- nahrání, stažení a smazání dokumentu,
- změna rolí,
- schválení, odmítnutí a oprava vazby,
- vyřešení nálezu,
- vytvoření exportu,
- interní support access.

Audit je chráněn před běžnou editací a má definovanou retenci.

## AI a třetí strany

Před odesláním obsahu třetí straně musí být známo:

- které části dokumentu odcházejí,
- kde se data zpracují,
- zda se používají k trénování,
- jak dlouho se uchovávají,
- kdo je subprocesor,
- jak je možné zpracování vypnout nebo nahradit.

Citlivost vstupu se minimalizuje segmentací. Celý dokument se neposílá modelu, pokud není technicky a smluvně odůvodněno.

## Zálohy a obnova

- automatické zálohy databáze,
- verzování nebo odpovídající ochrana objektů,
- pravidelný test obnovy,
- definované RPO/RTO před produkčním pilotem,
- oddělená oprávnění pro mazání produkčních dat a záloh.

Záloha, která nebyla otestována obnovou, není spolehlivá záloha.

## Secure development baseline

- secrets pouze v secret manageru nebo bezpečném prostředí,
- `.env` nikdy v Gitu,
- dependency scanning,
- code review u autorizace a migrací,
- parametrizované dotazy přes ORM,
- validace DTO,
- CSP a bezpečné cookies,
- ochrana proti CSRF podle zvoleného auth modelu,
- pravidelné aktualizace závislostí,
- produkční debug endpointy vypnuté.

## Incident response minimum

Před prvním placeným pilotem musí existovat:

- kontakt pro hlášení incidentu,
- postup omezení přístupu,
- možnost revokovat sessions a klíče,
- evidence dotčených projektů,
- proces komunikace se školou,
- post-incident review.

## Release gate

Produkční pilot nesmí začít bez:

- ověřené tenant isolation,
- bezpečného uploadu a downloadu,
- zálohy a testu obnovy,
- auditování citlivých akcí,
- definované retence,
- prověření dodavatelů AI a infrastruktury,
- základního threat modelu hlavního workflow.
