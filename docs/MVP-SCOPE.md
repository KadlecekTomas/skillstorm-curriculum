# MVP Scope

## Cíl MVP

MVP musí umožnit jedné škole dokončit jediný end-to-end proces:

> nahrát dokument → potvrdit rozpoznanou strukturu → zkontrolovat navržené vazby → vyřešit mezery a nejistoty → exportovat výsledek

MVP není veřejná samoobslužná platforma pro libovolný počet škol. Je to nástroj pro řízené placené piloty.

## Povinné schopnosti

### 1. Organizace a přístup

- vytvoření školní organizace administrátorem,
- pozvání omezeného počtu pracovníků,
- role `OWNER`, `COORDINATOR`, `REVIEWER`, `VIEWER`,
- oddělení dat mezi organizacemi,
- přehled aktivních uživatelů.

### 2. Projekt kurikulárního auditu

- vytvoření projektu,
- název a popis,
- vybraný referenční rámec a jeho verze,
- stav projektu,
- vlastník a termín,
- jednoduchý checklist průchodu.

### 3. Dokumenty

- nahrání PDF nebo DOCX,
- zobrazení stavu zpracování,
- srozumitelná chyba při nepodporovaném nebo nečitelném souboru,
- zachování původního dokumentu,
- řízené odstranění dokumentu,
- záznam verze a času nahrání.

### 4. Rozpoznaná struktura

- kapitoly a podkapitoly,
- předměty nebo vzdělávací oblasti,
- ročníky či období,
- očekávané výstupy a související text,
- možnost ruční opravy názvu, typu a zařazení,
- označení nerozpoznané části.

### 5. Referenční rámec

- import jedné podporované struktury rámce,
- verze rámce,
- hierarchie oblastí a požadavků,
- dohledatelný zdroj každého požadavku,
- ochrana proti tiché změně publikované verze.

### 6. Návrhy mapování

- vazba mezi prvkem ŠVP a prvkem rámce,
- stav `NAVRŽENO`, `PŘIJATO`, `ODMÍTNUTO`, `UPRAVENO`,
- míra jistoty,
- vysvětlení návrhu,
- zobrazení relevantního kontextu z obou stran,
- lidské potvrzení.

### 7. Nálezy

- možné nepokrytí,
- možná duplicita,
- nejasná vazba,
- rozpor ve struktuře,
- chybějící rozhodnutí,
- priorita a stav řešení,
- komentář a odpovědná osoba.

### 8. Přehled stavu

- jasný počet hotových a zbývajících položek,
- oddělení blokujících problémů od doporučení,
- návrat přesně na další nevyřešenou položku,
- automatické ukládání,
- viditelný stav posledního uložení.

### 9. Export

- export mapy vazeb,
- export otevřených nálezů,
- export rozhodnutí a komentářů,
- strojově čitelný CSV/XLSX a čitelný PDF až podle pilotní potřeby,
- označení verze dat a času exportu.

### 10. Audit a provoz

- kdo vytvořil, změnil nebo schválil rozhodnutí,
- čas změny,
- předchozí a nová hodnota u důležitých změn,
- základní provozní logy,
- zálohy a obnova.

## Explicitně mimo MVP

- žákovské a rodičovské účty,
- testy, známkování a docházka,
- LMS a knihovna výukových materiálů,
- gamifikace, XP a avatary,
- chat, notifikace do mobilní aplikace a sociální feed,
- tržiště,
- automatické přepsání celého ŠVP,
- veřejné hodnocení škol,
- více národních rámců současně,
- plnohodnotný editor kancelářských dokumentů,
- synchronizace se SIS,
- generická AI přípravna pro učitele,
- analytika žákovských výsledků.

## UX limit

Pro hlavní průchod platí:

- maximálně jeden primární úkol na obrazovku,
- maximálně jeden dominantní primární button,
- žádná obrazovka bez jasného dalšího kroku,
- žádná povinná znalost odborných názvů systému,
- chyba vždy obsahuje způsob nápravy,
- destruktivní akce jsou vratné nebo potvrzené.

## Technický limit

MVP smí začít jako modulární monolit. Mikroservisy, event streaming a komplexní pluginový systém nejsou povolené bez prokázané potřeby.

## Definition of Done pro MVP

MVP je hotové pouze tehdy, když:

- reálný pilotní uživatel dokončí workflow bez vedení vývojáře,
- uživatel dokáže opravit chybné rozpoznání,
- žádný AI návrh se nevydává za schválený,
- export odpovídá schváleným datům,
- auditní záznam je dohledatelný,
- data jedné školy nejsou dostupná jiné škole,
- tým dokáže bezpečně obnovit projekt ze zálohy,
- jsou změřeny hlavní metriky průchodu.
