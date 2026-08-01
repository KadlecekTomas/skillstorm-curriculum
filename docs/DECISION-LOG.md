# Decision Log

## Jak log používat

Každé významné rozhodnutí musí mít:

- ID,
- datum,
- status,
- kontext,
- rozhodnutí,
- důsledky,
- podmínku revize.

Status:

- `PROPOSED`
- `ACCEPTED`
- `SUPERSEDED`
- `REJECTED`

Rozhodnutí se nemažou. Novější rozhodnutí odkazuje na nahrazené.

---

## D-001 — Samostatný repozitář

- Datum: 2026-08-02
- Status: ACCEPTED

### Kontext

Původní SkillStorm pokrývá široké oblasti LMS, testování, uživatelů, obsahu a dalších školních workflow. Kurikulární produkt potřebuje úzký scope a samostatný vývojový rytmus.

### Rozhodnutí

SkillStorm Curriculum vzniká v samostatném repozitáři `skillstorm-curriculum`.

### Důsledky

- nepřenáší se automaticky celý původní datový model,
- sdílí se značka a vybrané technické zkušenosti,
- změny produktu nejsou blokované širokou platformou,
- případná budoucí integrace bude explicitní.

### Revize

Až bude existovat ověřený důvod pro společnou platformní vrstvu.

---

## D-002 — Vstupní produkt je kurikulární audit

- Datum: 2026-08-02
- Status: ACCEPTED

### Rozhodnutí

První prodejný workflow je:

> nahrát ŠVP → potvrdit strukturu → navrhnout vazby → vyřešit mezery a nejistoty → exportovat výsledek

### Důsledky

Žádný LMS, žákovské účty, rodičovské účty, známky, docházka, gamifikace ani marketplace v MVP.

### Revize

Po minimálně pěti placených pilotních projektech nebo zásadním vyvrácení obchodní hypotézy.

---

## D-003 — Placený concierge pilot před plným MVP

- Datum: 2026-08-02
- Status: ACCEPTED

### Rozhodnutí

Nejprve se prodává omezený, částečně ručně podporovaný pilot. Automatizuje se až opakující se a změřená práce.

### Důsledky

- vývoj nezačíná masovou samoobsluhou,
- ruční kroky se měří,
- cena je součást validace,
- pochvala bez objednávky není dostatečný důkaz.

### Revize

Po dokončení prvních tří placených pilotů.

---

## D-004 — Žádná data žáků v první verzi

- Datum: 2026-08-02
- Status: ACCEPTED

### Rozhodnutí

MVP nebude vyžadovat ani zpracovávat seznamy žáků, známky, docházku nebo individuální výsledky.

### Důsledky

- jednodušší doména a onboarding,
- nižší bezpečnostní a právní riziko,
- uživatelské role se týkají pracovníků školy,
- importy původního SkillStormu se nepřenášejí.

### Revize

Pouze pokud budoucí ověřená evidence layer skutečně vyžaduje individuální data a projde samostatným právním a bezpečnostním rozhodnutím.

---

## D-005 — Human-in-the-loop je povinný

- Datum: 2026-08-02
- Status: ACCEPTED

### Rozhodnutí

Automatický návrh nikdy není schváleným výsledkem bez explicitního lidského rozhodnutí.

### Důsledky

- stav `PROPOSED` je oddělený od `ACCEPTED`,
- každé rozhodnutí má autora a čas,
- export rozlišuje návrhy a schválené vazby,
- AI nemůže vydat konečný verdikt o souladu.

### Revize

Neplánuje se pro kritická kurikulární rozhodnutí.

---

## D-006 — Zero-training UX

- Datum: 2026-08-02
- Status: ACCEPTED

### Rozhodnutí

Hlavní workflow musí být dokončitelné bez školení a bez pomoci vývojáře.

### Důsledky

- jedna dominantní akce na obrazovku,
- systémové termíny se nepoužívají v UI,
- chyby vždy obsahují nápravu,
- viditelný postup a automatické ukládání,
- uživatelský test je release gate.

### Revize

Princip zůstává. Konkrétní UI se mění podle testů.

---

## D-007 — Modulární monolit

- Datum: 2026-08-02
- Status: ACCEPTED

### Rozhodnutí

Pilotní produkt bude modulární monolit s odděleným worker procesem podle provozní potřeby.

### Důsledky

- žádné mikroservisy a Kubernetes bez důkazu,
- jednodušší transakce a provoz,
- jasné modulové hranice připraví případné pozdější oddělení.

### Revize

Při doloženém škálovacím, bezpečnostním nebo týmovém bottlenecku.

---

## D-008 — Shared database, tenant-scoped data

- Datum: 2026-08-02
- Status: ACCEPTED

### Rozhodnutí

MVP používá sdílenou PostgreSQL databázi a povinný organization scope.

### Důsledky

- tenant context se odvozuje na serveru,
- cross-tenant negativní testy jsou povinné,
- support access je auditovaný,
- RLS lze přidat jako druhou vrstvu.

### Revize

Při požadavku enterprise zákazníka, datové rezidence nebo izolace na samostatnou databázi.

---

## D-009 — Český trh první, mezinárodně přenositelný model

- Datum: 2026-08-02
- Status: ACCEPTED

### Rozhodnutí

Produkt se nejprve ověřuje v Česku. Datový model odděluje obecné entity od národního názvosloví a rámců.

### Důsledky

- žádná paralelní lokalizace několika zemí,
- framework data jsou verzovaná,
- UI a exportní texty jsou lokalizovatelné,
- evropská expanze následuje až po českém product-market fitu.

### Revize

Po opakovatelném prodeji a provozu na českém trhu.

---

## D-010 — Počáteční cenová hypotéza

- Datum: 2026-08-02
- Status: ACCEPTED

### Rozhodnutí

První omezený pilot se nabízí v pracovním pásmu 15 000–25 000 Kč bez DPH.

### Důsledky

- nejde o finální ceník,
- cena se testuje objednávkou,
- bezplatné piloty se nezapočítávají jako hlavní důkaz ochoty platit,
- po pilotu se vyhodnotí skutečná marže.

### Revize

Po každých třech konkrétních nabídkách a po každém dokončeném pilotu.
