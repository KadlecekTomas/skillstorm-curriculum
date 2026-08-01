# UX/UI Principles

## Základní postoj

Uživatel není „hloupý“. Je vytížený, často pod tlakem, nemusí být technicky zdatný a nechce se učit nový systém. Produkt musí respektovat jeho čas, pozornost a nejistotu.

**Pravidlo:** systém nese složitost; uživatel dostává jednoduché rozhodnutí v jasném kontextu.

## 1. Zero-training UX

První relevantní výsledek musí být dosažitelný bez manuálu a bez školení.

Každá obrazovka musí mít:

- jasný nadpis v jazyce uživatele,
- jednu větu „co se zde děje“,
- jeden dominantní další krok,
- viditelný stav práce,
- možnost vrátit se bez ztráty dat.

Zakázané:

- prázdné dashboardy bez instrukce,
- ikony bez popisku,
- více stejně výrazných primárních tlačítek,
- technické chybové hlášky,
- skryté automatické změny,
- modal za modalem,
- povinné hromadné nastavení před první hodnotou.

## 2. Jazyk rozhraní

Používej slovesa a konkrétní výsledky:

- „Nahrát ŠVP“ místo „Nový asset“
- „Zkontrolovat 12 návrhů“ místo „Mapping queue“
- „Potvrdit vazbu“ místo „Submit“
- „Stáhnout pracovní přehled“ místo „Generate report“

Text tlačítka musí předvídat důsledek. Nepoužívej neurčité „Pokračovat“, pokud lze napsat přesnější akci.

## 3. Jedna obrazovka, jeden hlavní úkol

Povolená struktura:

1. kontext,
2. jedna úloha,
3. potřebné informace,
4. primární akce,
5. vedlejší bezpečný únik.

Na obrazovce kontroly vazby se nemají současně nastavovat uživatelé, export, fakturace a struktura dokumentu.

## 4. Postupné odhalování složitosti

Základní pohled ukazuje pouze informace nutné k rozhodnutí.

Pokročilé detaily se zobrazí na vyžádání:

- původní celý odstavec,
- metadata zpracování,
- alternativní návrhy,
- technická diagnostika pro podporu.

Uživatel nesmí být nucen porozumět všem detailům, aby udělal běžný krok.

## 5. Bezpečí a vratnost

- formuláře se automaticky ukládají,
- stav uložení je viditelný,
- odmítnutý návrh lze obnovit,
- smazání dokumentu vyžaduje potvrzení a vysvětlení dopadu,
- opuštění stránky nesmí ztratit rozpracovanou práci,
- hromadná akce ukáže náhled změn před potvrzením.

## 6. Chyby jako návod

Chybová zpráva musí obsahovat:

1. co se nepodařilo,
2. co zůstalo bezpečně zachováno,
3. co může uživatel udělat,
4. jak získat pomoc.

Příklad:

> Dokument se nepodařilo přečíst. Původní soubor jsme zachovali. Nahrajte prosím verzi bez hesla nebo zvolte „Předat ke kontrole“.

Nikdy nezobrazuj samotné `500`, stack trace, název databázové constrainty nebo ID interního jobu.

## 7. Stav a orientace

Projekt má vždy viditelný postup:

```text
1. Dokument
2. Struktura
3. Vazby
4. Nálezy
5. Export
```

U každého kroku:

- `Nezahájeno`
- `Probíhá`
- `Vyžaduje pozornost`
- `Dokončeno`

Uživatel musí jedním kliknutím přejít na nejbližší blokující položku.

## 8. Rozhodování nad AI návrhy

Každá karta návrhu ukazuje:

- co se propojuje,
- proč byl návrh vytvořen,
- relevantní text na obou stranách,
- míru jistoty lidským jazykem,
- akce `Přijmout`, `Upravit`, `Odmítnout`,
- možnost `Nevím — předat garantovi`.

Barva nesmí být jediným nositelem významu. „Vysoká jistota“ neznamená „správné“.

## 9. Formuláře

- ptej se pouze na údaj potřebný právě teď,
- používej předvyplnění jen tehdy, když je bezpečné,
- povinná pole jasně označ,
- validuj průběžně, ne až po odeslání,
- zachovej zadaná data při chybě,
- u data, role a verze vysvětli jejich dopad.

## 10. Přístupnost

Minimum:

- ovládání klávesnicí,
- viditelný focus,
- smysluplné pořadí nadpisů,
- label pro každé pole,
- dostatečný kontrast,
- textový význam vedle barvy a ikony,
- žádné zásadní workflow závislé na drag-and-drop,
- responzivní web bez požadavku na nativní aplikaci.

## 11. Vizuální styl

- klidný, profesionální a důvěryhodný,
- vysoká čitelnost,
- omezená paleta stavových barev,
- dostatek prostoru,
- žádné dětské herní prvky,
- žádné „AI záření“, animované gradienty nebo efekty, které soutěží s obsahem,
- tabulky pouze tam, kde jsou skutečně nejlepší formou porovnání.

## 12. Povinné UX testy před releasem

Každý kritický průchod se testuje s člověkem, který funkci nevyvíjel.

Sleduj:

- zda chápe první krok do 10 sekund,
- počet dotazů na obsluhu,
- počet návratů a slepých uliček,
- chyby bez možnosti samostatné nápravy,
- čas do prvního dokončeného rozhodnutí,
- zda rozlišuje návrh AI od schváleného výsledku.

Release je blokován, pokud uživatel potřebuje ústní návod pro základní průchod.
