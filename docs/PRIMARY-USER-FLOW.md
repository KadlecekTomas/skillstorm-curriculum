# Primary User Flow

## Persona

Primární uživatel je koordinátor ŠVP nebo člen vedení školy. Má omezený čas, odpovídá za výsledek a nemusí být technicky zdatný.

## Cíl

Dokončit kontrolovatelný audit dokumentu bez znalosti interní architektury a bez podpory vývojáře.

## Stavový model projektu

```text
DRAFT
→ DOCUMENT_UPLOADED
→ PARSING
→ STRUCTURE_REVIEW
→ MAPPING_REVIEW
→ FINDINGS_REVIEW
→ READY_TO_EXPORT
→ COMPLETED
```

Vedlejší stavy:

- `NEEDS_INPUT`
- `PROCESSING_FAILED`
- `ARCHIVED`

Technické názvy se v UI nepoužívají. Uživatel vidí lidské varianty.

## Krok 0 — Vytvoření projektu

### Uživatel vidí

- název projektu,
- školu,
- referenční rámec a jeho verzi,
- očekávaný výstup,
- jednoduchý přehled pěti kroků.

### Uživatel udělá

- pojmenuje projekt,
- vybere podporovaný rámec,
- potvrdí odpovědnou osobu.

### Systém udělá

- vytvoří oddělený projekt,
- zapíše auditní událost,
- zobrazí krok „Nahrát dokument“.

## Krok 1 — Nahrání dokumentu

### Obrazovka

Nadpis: **Nahrajte současné ŠVP**

Doprovodný text:

> Nahrajte PDF nebo DOCX. Dokument nejprve pouze přečteme a nic v něm nezměníme.

### Povinnosti systému

- zobrazit podporované typy a limit,
- před nahráním vysvětlit zacházení s daty,
- ukazovat průběh,
- umožnit bezpečné opakování,
- zachovat původní soubor,
- informovat uživatele po dokončení.

### Chybové větve

- soubor chráněný heslem,
- obrázkový sken bez použitelného textu,
- poškozený dokument,
- příliš velký soubor,
- nepodporovaný formát.

Každá větev nabídne konkrétní nápravu nebo předání podpoře.

## Krok 2 — Kontrola struktury

### Cíl

Uživatel nepotvrzuje každou větu. Potvrzuje pouze strukturu, která ovlivní další analýzu.

### Uživatel vidí

- strom dokumentu,
- rozpoznané předměty a ročníky,
- části s nízkou jistotou,
- počet položek vyžadujících kontrolu.

### Akce

- potvrdit,
- přejmenovat,
- změnit typ,
- přesunout,
- sloučit,
- rozdělit,
- označit jako nerelevantní.

### UX pravidlo

Systém nejprve nabídne pouze problematické položky. Správně rozpoznaná většina nesmí uživatele nutit ke stovkám zbytečných kliknutí.

## Krok 3 — Kontrola vazeb

### Jednotka práce

Jedna karta = jedno rozhodnutí.

Karta obsahuje:

- text nebo shrnutí prvku ŠVP,
- navržený prvek rámce,
- zvýrazněný relevantní kontext,
- vysvětlení návrhu,
- jistotu,
- historii předchozího rozhodnutí,
- akce `Přijmout`, `Upravit`, `Odmítnout`, `Předat garantovi`.

### Navigace

- další nevyřešená položka,
- filtrovat podle předmětu, ročníku, odpovědné osoby a stavu,
- uložit filtr jako pracovní pohled až mimo první pilot, pokud není nutný.

### Hromadné akce

Pouze pro bezpečné, podobné položky. Před potvrzením se zobrazí počet a náhled dopadu.

## Krok 4 — Nálezy

Systém rozdělí nálezy na:

### Blokující

- chybí rozhodnutí,
- nečitelná část,
- konflikt verzí,
- nepokrytý povinný prvek podle nastavených pravidel.

### K prověření

- možná duplicita,
- slabá vazba,
- neobvyklé rozložení,
- doporučení k diskuzi.

Každý nález má:

- lidský název,
- vysvětlení,
- zdrojový kontext,
- prioritu,
- odpovědnou osobu,
- stav,
- komentář,
- rozhodnutí.

## Krok 5 — Kontrola dokončení

Obrazovka odpoví:

- Co je dokončeno?
- Co blokuje export?
- Co je pouze doporučení?
- Kdo má otevřené úkoly?
- Kdy byla data naposledy změněna?

Primární akce:

- `Vyřešit poslední 3 blokující položky`, nebo
- `Připravit export`, pokud nic neblokuje.

## Krok 6 — Export

Uživatel nejprve vybere účel:

- pracovní přehled pro vedení,
- detailní mapa vazeb,
- seznam otevřených nálezů,
- auditní přehled rozhodnutí.

Systém ukáže:

- co export obsahuje,
- aktuální verzi,
- datum a autora,
- upozornění, pokud existují nevyřešená doporučení.

## Krok 7 — Závěr pilotu

Po exportu systém neukáže generický dashboard. Nabídne:

- stáhnout výstupy,
- pozvat dalšího hodnotitele,
- zaznamenat zpětnou vazbu,
- naplánovat závěrečné vyhodnocení,
- archivovat projekt.

## Kritické analytické události

- projekt vytvořen,
- dokument nahrán,
- zpracování dokončeno / selhalo,
- první potvrzená struktura,
- první rozhodnutí o vazbě,
- blokující nález vyřešen,
- projekt připraven k exportu,
- export vytvořen,
- pilot dokončen.

Analytika nesmí ukládat obsah citlivých dokumentů do externího event nástroje.
