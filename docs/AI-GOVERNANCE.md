# AI Governance

## Účel

AI v SkillStorm Curriculum má snižovat ruční práci, nikoliv nahrazovat odpovědnost školy nebo vytvářet dojem automatické správnosti.

## Povolené použití v MVP

AI může pomáhat s:

- klasifikací části dokumentu,
- rozpoznáním předmětu, ročníku nebo typu výstupu,
- návrhem vazby mezi prvkem ŠVP a rámce,
- návrhem vysvětlení podobnosti,
- označením možné duplicity,
- prioritizací položek ke kontrole,
- shrnutím otevřených rozhodnutí.

## Zakázané použití v MVP

AI nesmí:

- sama schválit vazbu,
- deklarovat úplnost nebo soulad jako definitivní fakt,
- přepsat originální dokument bez potvrzení,
- generovat právní nebo inspekční garanci,
- skrývat zdroj a míru jistoty,
- automaticky hodnotit pracovníka školy,
- používat vstupy školy k trénování bez výslovného právního a smluvního základu.

## Human-in-the-loop

Každý významný návrh má:

- stav `PROPOSED`,
- zdrojový kontext,
- vysvětlení,
- míru jistoty,
- možnost přijmout, upravit nebo odmítnout,
- audit lidského rozhodnutí.

Systém nesmí započítat návrh jako schválené pokrytí před lidským rozhodnutím.

## Míra jistoty

Interní numerické skóre lze používat pro řazení. Uživatel vidí srozumitelná pásma:

- **Vysoká jistota návrhu** — silná textová a strukturální shoda; stále vyžaduje kontrolu.
- **Střední jistota** — pravděpodobná vazba s nejasností.
- **Nízká jistota** — návrh slouží hlavně jako podnět ke kontrole.

Text nikdy nesmí naznačovat, že vysoké skóre znamená zaručenou správnost.

## Zdrojovost

Každý návrh musí být dohledatelný k:

- konkrétnímu fragmentu školního dokumentu,
- konkrétnímu prvku a verzi rámce,
- verzi promptu nebo pravidla,
- modelu a běhu, který návrh vytvořil.

Vysvětlení bez zdroje není pro kritický workflow dostatečné.

## Strukturované výstupy

Model vrací výstup proti explicitnímu schématu. Výstup se:

1. parsuje,
2. validuje,
3. kontroluje vůči povoleným ID,
4. omezuje rozsahem,
5. ukládá jako návrh,
6. teprve potom zobrazuje uživateli.

Volný text modelu nesmí přímo měnit doménová data.

## Ochrana před prompt injection

Obsah nahraného dokumentu je nedůvěryhodný vstup. Instrukce obsažené v dokumentu nesmí měnit systémová pravidla.

Minimum:

- oddělení instrukcí a dat,
- povolený výstup pouze ve schématu,
- žádné nástroje s oprávněním měnit data bez mezivrstvy,
- whitelist povolených referencí,
- testy s útočnými texty v dokumentu.

## Evaluace

Před produkčním použitím vznikne anonymizovaný nebo syntetický eval set.

Měří se:

- přesnost rozpoznání struktury,
- precision návrhů vazeb,
- recall relevantních kandidátů,
- podíl přijatých návrhů,
- podíl zásadně opravených návrhů,
- počet nebezpečně sebevědomých chyb,
- náklady a latence.

Hlavní metrikou není „AI odpověděla“. Hlavní metrikou je, zda člověku bezpečně ušetřila práci.

## Model changes

Změna modelu, promptu nebo preprocessing pipeline je verzovaná změna.

Před nasazením:

- proběhne eval,
- porovnají se výsledky s předchozí verzí,
- ověří se náklady,
- zkontroluje se bezpečnost,
- existuje rollback.

Staré návrhy se bez vědomí uživatele nepřepočítávají.

## Fallback

Systém musí podporovat:

- ruční klasifikaci,
- ruční vytvoření vazby,
- předání problematické položky internímu specialistovi,
- opakování zpracování,
- pokračování projektu i při dočasné nedostupnosti AI služby.

AI provider nesmí být single point of failure celého produktu.

## Transparentnost vůči škole

Škola musí vědět:

- kde se AI používá,
- že jde o návrhy,
- kdo má poslední slovo,
- jaká data mohou opustit infrastrukturu,
- jak lze požádat o odstranění,
- jak se řeší chyba.

Marketing nesmí tvrdit „automaticky zaručí soulad“.
