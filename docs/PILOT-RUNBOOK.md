# Pilot Runbook

## Účel

Tento runbook zajišťuje, že každý pilot proběhne stejným způsobem, vzniknou srovnatelná data a škola dostane jasně vymezený výsledek.

## Fáze A — Kvalifikace

Pilot se nabídne pouze škole, která má:

- konkrétní problém,
- vlastníka projektu,
- reálný dokument,
- ochotu věnovat čas kontrole,
- nákupního schvalovatele,
- dohodnutý výstup.

### Kvalifikační checklist

- [ ] Známe typ školy a rozhodující roli.
- [ ] Známe současný postup.
- [ ] Známe termín nebo naléhavost.
- [ ] Známe přibližný objem dokumentu.
- [ ] Známe osobu, která bude schvalovat návrhy.
- [ ] Známe nákupní postup.
- [ ] Cena nebyla prezentována jako bezplatná zkouška.

## Fáze B — Objednávka a scope

Před zahájením:

- písemně potvrdit rozsah,
- potvrdit cenu a platební podmínky,
- potvrdit referenční rámec a verzi,
- určit vlastníka na obou stranách,
- definovat termíny,
- definovat zacházení s daty,
- uvést, co pilot negarantuje.

### Scope freeze

Po zahájení se nové požadavky zapisují jako:

- nutné k dokončení dohodnutého výstupu,
- změnový požadavek,
- nápad do backlogu.

Ne každý požadavek školy se implementuje během pilotu.

## Fáze C — Bezpečný příjem dat

- [ ] Škola obdržela instrukci, co nenahrávat.
- [ ] Dokument je předán schváleným kanálem.
- [ ] Je ověřen formát, velikost a čitelnost.
- [ ] Je vytvořen checksum a verze.
- [ ] Je zaznamenán čas převzetí.
- [ ] Je potvrzena retence a plán smazání.
- [ ] Původní dokument zůstává neměnný.

## Fáze D — Baseline měření

Před zpracováním zjistit:

- kolik lidí na úkolu pracuje,
- kolik času již investovali,
- kolik částí dokumentu ručně kontrolují,
- jaký používají nástroj,
- kde očekávají největší úsporu,
- jak dnes poznají dokončení.

Bez baseline nelze důvěryhodně tvrdit úsporu.

## Fáze E — Zpracování

Interní postup:

1. validace dokumentu,
2. extrakce,
3. rozpoznání struktury,
4. interní QA vzorku,
5. import referenční verze,
6. vytvoření návrhů,
7. kontrola zdrojovosti,
8. označení nejistot,
9. příprava review prostředí.

Každý ruční zásah se měří. Cílem je poznat budoucí automatizační priority.

## Fáze F — Review školy

Úvod review má trvat maximálně tolik, aby uživatel pochopil první krok. Nemá suplovat dlouhé školení.

Sleduj:

- zda uživatel chápe stav návrhu,
- zda najde zdroj,
- zda umí přijmout, upravit a odmítnout,
- zda dokáže předat nejistotu garantovi,
- zda rozumí rozdílu mezi blokujícím nálezem a doporučením,
- kde žádá o pomoc.

Podpora nesmí uživateli klikat workflow místo něj, pokud nejde o technickou poruchu.

## Fáze G — QA před exportem

- [ ] Neexistuje automaticky schválená vazba.
- [ ] Každá schválená vazba má rozhodující osobu.
- [ ] Blokující nálezy jsou vyřešené nebo explicitně označené.
- [ ] Export odpovídá aktuální revizi.
- [ ] Zdrojové reference jsou dohledatelné.
- [ ] Neunikají data jiné organizace.
- [ ] Export obsahuje datum, verzi a disclaimer.

## Fáze H — Předání

Škola dostane:

- dohodnuté exporty,
- stručný přehled výsledku,
- seznam otevřených bodů,
- popis omezení,
- datum plánovaného smazání nebo pokračování,
- termín závěrečného vyhodnocení.

## Fáze I — Závěrečné vyhodnocení

Otázky:

- Co by škola bez produktu dělala ručně?
- Kolik času skutečně strávila?
- Kde byla největší úspora?
- Který výstup použije dál?
- Čemu nevěřila?
- Která chyba byla nejzávažnější?
- Zaplatila by znovu?
- Za co by platila průběžně?
- Doporučí konkrétní další školu?

## Fáze J — Interní post-mortem

Do 48 hodin zapiš:

- plán vs. skutečnost,
- příjem a všechny náklady,
- interní hodiny podle kroku,
- kvalitu návrhů,
- UX problémy,
- bezpečnostní incidenty nebo near misses,
- opakující se ruční práci,
- požadavky školy,
- rozhodnutí `GO / ADJUST / STOP`.

## Eskalace

Pilot se pozastaví při:

- podezření na únik dat,
- cross-tenant problému,
- nahrání zjevně nevhodných citlivých údajů,
- nesprávné referenční verzi,
- zásadní chybě mapování, která může poškodit důvěru,
- nejasném vlastnictví dokumentu nebo oprávnění k jeho použití.

Rychlost dodání nemá přednost před bezpečností a důvěryhodností.
