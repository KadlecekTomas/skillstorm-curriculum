# Information Architecture

## Cíl

Navigace musí odpovídat práci uživatele, ne interním modulům systému. Primární uživatel se orientuje podle projektu a jeho stavu.

## Hlavní navigace

Pro MVP:

```text
Projekty
Škola a uživatelé
Nápověda
Profil
```

Položky jako `AI`, `Dokumenty`, `Mappings`, `Findings` nebo `Jobs` nejsou globální hlavní navigace. Patří do kontextu konkrétního projektu.

## Seznam projektů

Každá karta nebo řádek ukazuje:

- název projektu,
- referenční rámec a verzi,
- vlastníka,
- aktuální krok,
- počet blokujících položek,
- poslední změnu,
- jasnou akci `Pokračovat` doplněnou konkrétním cílem.

Preferovaný text:

- `Zkontrolovat 8 částí struktury`
- `Rozhodnout o 12 vazbách`
- `Vyřešit 3 blokující položky`
- `Připravit export`

Ne pouze `Otevřít`.

## Navigace v projektu

Stálý krokový přehled:

1. **Dokument**
2. **Struktura**
3. **Vazby**
4. **Nálezy**
5. **Export**

Doplňkové sekce v menu projektu:

- Přehled
- Lidé a odpovědnosti
- Historie
- Nastavení projektu

Doplňkové sekce nesmí soutěžit s hlavním krokovým workflow.

## Projektový přehled

Účel: odpovědět vedení a koordinátorovi na otázku „Kde jsme?“

Obsah:

- další doporučený krok,
- průběh pěti etap,
- blokující položky,
- otevřené úkoly podle lidí,
- poslední významné změny,
- verze dokumentu a rámce,
- termín.

Zakázáno:

- dekorativní grafy bez rozhodovací hodnoty,
- deset KPI karet,
- aktivita bez relevance,
- technické statistiky pipeline.

## Dokument

Obsah:

- původní soubor a verze,
- stav zpracování,
- bezpečnostní a retenční informace,
- historie uploadů,
- možnost nahrát novou verzi,
- srozumitelný dopad změny verze.

Nová verze nesmí tiše přepsat rozhodnutí staré verze.

## Struktura

Dva režimy:

### Kontrola problémů

Výchozí režim. Ukazuje pouze části s nízkou jistotou, konfliktem nebo chybějícím zařazením.

### Celý strom

Pokročilý režim pro prohlížení a ruční úpravy.

Uživatel nesmí být nucen potvrdit stovky správně rozpoznaných prvků jednotlivě.

## Vazby

Výchozí pohled je fronta rozhodnutí, ne velká matice.

Filtry:

- předmět / oblast,
- ročník / období,
- stav,
- míra jistoty,
- odpovědná osoba.

Detail jedné vazby otevírá relevantní kontext bez opuštění fronty.

Matice pokrytí může být sekundární přehled, nikoliv jediný způsob práce.

## Nálezy

Primární členění:

- `Blokuje dokončení`
- `Vyžaduje prověření`
- `Vyřešeno`

Sekundární členění:

- mezera,
- duplicita,
- nízká jistota,
- strukturální konflikt,
- chybějící rozhodnutí.

Jazyk musí vysvětlit důsledek. Samotný typ nálezu nestačí.

## Export

Uživatel volí účel, ne technický formát jako první krok.

1. pracovní přehled pro vedení,
2. detailní mapa vazeb,
3. seznam otevřených bodů,
4. auditní historie.

Teprve poté vybírá dostupný formát.

## Škola a uživatelé

Pro MVP:

- název školy,
- členové,
- role,
- pozvánky,
- bezpečnost účtu,
- audit změn oprávnění.

Žádné třídy, žáci, rodiče ani předměty jako globální školní katalog, pokud nejsou odvozeny přímo v projektu.

## Nápověda

Preferované pořadí:

1. kontextová nápověda přímo na obrazovce,
2. krátké odpovědi na běžné problémy,
3. kontakt podpory,
4. technický diagnostický kód.

Dokumentace nesmí být náhradou za nepochopitelné rozhraní.

## URL návrh

```text
/app/projects
/app/projects/:projectId
/app/projects/:projectId/document
/app/projects/:projectId/structure
/app/projects/:projectId/mappings
/app/projects/:projectId/findings
/app/projects/:projectId/export
/app/projects/:projectId/history
/app/organization/members
/app/help
```

Každá URL musí být autorizovaná serverem vůči organization a project contextu.

## Mobilní zobrazení

Produkt je desktop-first, ale responzivní.

Na menší obrazovce musí fungovat:

- přehled stavu,
- čtení komentářů,
- jednoduché schválení jedné vazby,
- bezpečné přihlášení.

Komplexní úprava stromu může doporučit větší obrazovku, nesmí však selhat bez vysvětlení.
