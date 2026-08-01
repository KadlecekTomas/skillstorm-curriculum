# Research Backlog

## Účel

Tento dokument odděluje skutečně ověřená fakta od předpokladů. Každá významná produktová nebo obchodní otázka musí mít vlastníka, způsob ověření a rozhodnutí, které výsledek ovlivní.

## Evidence standard

### FACT

Musí mít alespoň jeden z následujících podkladů:

- primární oficiální zdroj,
- smlouvu, objednávku nebo fakturu,
- reálná anonymizovaná produktová data,
- zaznamenané pozorování skutečného workflow,
- opakovaný konzistentní výsledek pilotů.

### HYPOTHESIS

Je pracovní předpoklad. Musí uvádět:

- proč mu věříme,
- co by ho potvrdilo,
- co by ho vyvrátilo,
- do kdy ho ověříme.

### DECISION

Je volba týmu. Nemusí být univerzálně pravdivá, ale musí mít zdůvodnění, vlastníka a datum revize.

## Priorita P0 — před vývojem pilotního MVP

### R1 — Skutečný postup škol

Otázka:

> Jak školy dnes prakticky porovnávají a upravují ŠVP?

Metoda:

- 15–20 rozhovorů,
- alespoň 5 ukázek skutečného postupu nebo anonymizovaných artefaktů,
- evidence nástrojů, rolí, času a schvalování.

Rozhodnutí:

- pořadí hlavního workflow,
- které části mají být automatizované,
- zda je problém dostatečně častý.

### R2 — Ochota platit

Otázka:

> Zaplatí škola 15–25 tisíc Kč za omezený auditní pilot?

Metoda:

- konkrétní nabídky,
- sledování konverze,
- rozbor námitek,
- minimálně 3 objednávky jako první práh.

Rozhodnutí:

- pokračovat / změnit nabídku / zastavit.

### R3 — Opakovaná hodnota

Otázka:

> Co škola potřebuje po prvotním auditu?

Metoda:

- závěrečný rozhovor po pilotu,
- nabídka pokračujícího workspace,
- sledování skutečného používání.

Rozhodnutí:

- SaaS, produktizovaná služba nebo jednorázový audit.

### R4 — Důvěryhodnost automatických návrhů

Otázka:

> Jaké vysvětlení, zdrojovost a jistota jsou nutné, aby uživatel návrh bezpečně použil?

Metoda:

- prototypové testy,
- acceptance/edit/rejection data,
- kvalitativní pozorování.

Rozhodnutí:

- UI karty návrhu,
- minimální evidence,
- fallback na ruční práci.

### R5 — Licenční a zdrojová použitelnost rámců

Otázka:

> Za jakých podmínek lze referenční dokumenty ukládat, strukturovat, verzovat a zobrazovat?

Metoda:

- ověření oficiálních podmínek,
- právní konzultace před komerčním provozem,
- dokumentace původu každé verze.

Rozhodnutí:

- importer, způsob zobrazení, distribuce a export.

## Priorita P1 — před placeným produkčním pilotem

### R6 — Bezpečnostní požadavky škol

Zjistit:

- požadovanou datovou lokalitu,
- smluvní podklady,
- pravidla účtů a MFA,
- retenci,
- přístup podpory,
- očekávané incident response.

### R7 — Formáty dokumentů

Změřit:

- podíl PDF, DOCX a skenů,
- typické velikosti,
- kvalitu struktury,
- tabulky, přílohy a více souborů,
- četnost heslem chráněných dokumentů.

### R8 — Kvalita extrakce

Vytvořit eval set s kategoriemi:

- strojové PDF,
- složité PDF,
- DOCX,
- tabulky,
- sken,
- nestandardní struktura.

### R9 — Exportní potřeby

Ověřit, co uživatel skutečně použije:

- XLSX,
- PDF,
- DOCX,
- CSV,
- interní webový pohled.

Nevyvíjet všechny formáty automaticky.

## Priorita P2 — po prvních pilotech

### R10 — Partnerství

- metodici,
- konzultanti,
- zřizovatelé,
- vzdělávací organizace.

Testovat, zda partner zkracuje sales cycle nebo pouze přidává vrstvu koordinace.

### R11 — Další trh

Před výběrem země hodnotit:

- podobnost problému,
- centralizaci kurikula,
- dostupnost rámců,
- jazykovou a právní náročnost,
- lokálního partnera,
- ochotu platit.

### R12 — Integrace

Integrace se hodnotí podle počtu reálných pilotů, které blokuje. „Školy používají systém X“ samo o sobě není důvod integraci stavět.

## Research debt

Výzkumný dluh vzniká, když:

- rozhodnutí stojí na nepotvrzeném předpokladu,
- tým používá zastaralý zdroj,
- jeden hlasitý zákazník nahrazuje celý vzorek,
- chybí baseline před pilotem,
- do roadmapy vstoupí funkce bez evidence.

Výzkumný dluh se eviduje stejně vážně jako technický dluh.

## Šablona výzkumné položky

```md
### RX — Název

- Status: OPEN | IN_PROGRESS | VERIFIED | REJECTED
- Owner:
- Deadline:
- Hypothesis:
- Evidence needed:
- Method:
- Result:
- Decision affected:
- Sources:
```

Citlivé rozhovory a dokumenty se necommitují. Repo obsahuje pouze anonymizované závěry a odkazy na schválené interní úložiště.
