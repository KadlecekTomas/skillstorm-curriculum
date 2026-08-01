# Product Doctrine

## 1. Účel

SkillStorm Curriculum existuje proto, aby škole snížil nejistotu a množství ruční práce při převodu, kontrole a dlouhodobé správě kurikula.

Neexistuje proto, aby byl „další školní platformou“.

## 2. Neměnné principy

### 2.1 Jeden naléhavý problém před deseti zajímavými funkcemi

První produkt řeší jediný výsledek:

> Škola získá kontrolovatelnou mapu mezi vlastním ŠVP a referenčním vzdělávacím rámcem, včetně mezer, duplicit, nejasností a dohledatelných rozhodnutí.

Funkce bez přímé vazby na tento výsledek do první verze nepatří.

### 2.2 Člověk rozhoduje

Automatizace může:

- rozpoznat strukturu,
- navrhnout klasifikaci,
- doporučit vazbu,
- upozornit na možný problém,
- vysvětlit důvod návrhu.

Automatizace nesmí bez lidského schválení:

- prohlásit školní dokument za správný nebo úplný,
- měnit schválené kurikulum,
- skrýt nejistotu,
- vydávat návrh za odborný nebo právní verdikt.

### 2.3 Zero-training UX

Produkt musí být použitelný bez školení a bez znalosti interní datové struktury.

Každá obrazovka musí odpovědět na čtyři otázky:

1. Co právě vidím?
2. Co se ode mě očekává?
3. Co se stane po kliknutí?
4. Jak se vrátím nebo opravím chybu?

### 2.4 Systém nese složitost

Uživatel nemá řešit:

- interní identifikátory,
- datové modely,
- technické názvy stavů,
- rozdíl mezi parserem, modelem a validačním pravidlem,
- formát API,
- proč selhalo zpracování na technické úrovni.

Uživatel má dostat lidsky srozumitelné vysvětlení a konkrétní další krok.

### 2.5 Důvěryhodnost před efektem

Preferujeme:

- zdroj před sebevědomým tvrzením,
- míru jistoty před falešnou přesností,
- možnost opravy před plnou automatizací,
- auditní stopu před „magickým“ výsledkem,
- stabilní workflow před vizuální exhibicí.

### 2.6 Žádná data žáků v pilotu

První produkt pracuje s kurikulárními dokumenty a rolemi pracovníků školy. Nevyžaduje seznam žáků, známky, docházku ani individuální vzdělávací výsledky.

### 2.7 Prodejní důkaz před škálováním

Za ověření se považuje:

- zaplacený pilot,
- dokončený reálný workflow,
- měřitelná úspora práce,
- důvěra ve výstup,
- důvod pokračovat po prvotním převodu.

Za ověření se nepovažuje:

- pochvala,
- počet registrací,
- bezplatný test,
- počet vytvořených funkcí,
- technická propracovanost.

## 3. Produktové testy pro každou novou funkci

Nová funkce smí postoupit do realizace pouze tehdy, když lze odpovědět „ano“ alespoň na jednu otázku a zároveň nevzniká zásadní nové riziko:

- Zvyšuje pravděpodobnost placeného pilotu?
- Zkracuje čas potřebný k dokončení hlavního workflow?
- Snižuje počet závažných chyb nebo nejistot?
- Zvyšuje důvěru v závěr?
- Je nutná pro bezpečnost, soukromí nebo auditovatelnost?

„Je to cool“ není produktový důvod.

## 4. Anti-principy

SkillStorm Curriculum nebude:

- nahrazovat Bakaláře, EduPage nebo jiný SIS,
- vytvářet další komunikační kanál pro rodiče,
- hodnotit žáky,
- slibovat právní nebo odbornou bezchybnost,
- generovat celý ŠVP jedním tlačítkem bez kontroly,
- nutit školu migrovat provozní data,
- skrývat omezení AI.

## 5. Hlavní věta produktu

> Nahrajte své ŠVP. Společně z něj vytvoříme kontrolovatelnou mapu vůči referenčnímu rámci, ukážeme nejasnosti a připravíme podklady k rozhodnutí — bez dat žáků a bez výměny vašich současných systémů.
