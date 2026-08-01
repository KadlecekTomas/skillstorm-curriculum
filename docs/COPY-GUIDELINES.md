# Copy Guidelines

## Cíl

Text v produktu musí snížit nejistotu a vést uživatele k bezpečnému dalšímu kroku. Uživatel nemá luštit systémovou terminologii ani domýšlet dopad akce.

## Základní pravidla

- Piš česky, konkrétně a aktivně.
- Jedna věta má sdělovat jednu hlavní myšlenku.
- Používej známé školní termíny, ne interní názvy modelů.
- Popisuj výsledek akce, ne technickou operaci.
- Nikdy neslibuj jistotu, kterou systém nemá.
- Neobviňuj uživatele za chybu.
- Nezvyšuj stres vykřičníky, červenou barvou a naléhavostí bez důvodu.

## Tlačítka

Dobré:

- `Nahrát ŠVP`
- `Zkontrolovat strukturu`
- `Přijmout vazbu`
- `Upravit návrh`
- `Předat garantovi`
- `Vyřešit 3 blokující položky`
- `Připravit pracovní export`

Špatné:

- `OK`
- `Submit`
- `Execute`
- `Continue`
- `Process`
- `Ano`

Obecný text je povolen pouze tehdy, když je důsledek z kontextu naprosto zřejmý.

## Nadpisy obrazovek

Nadpis má popsat úkol:

- `Nahrajte současné ŠVP`
- `Zkontrolujte rozpoznané předměty`
- `Rozhodněte o navržených vazbách`
- `Vyřešte položky, které blokují export`

Nepoužívej interní názvy:

- `Document ingestion`
- `Node review`
- `Mapping management`
- `Finding resolution center`

## Stavové texty

Doporučené uživatelské stavy:

- `Čeká na zahájení`
- `Zpracováváme dokument`
- `Potřebujeme vaši kontrolu`
- `Připraveno k exportu`
- `Dokončeno`
- `Zpracování se nepodařilo`

U dlouhé operace vždy vysvětli:

- co systém dělá,
- zda uživatel může odejít,
- jak se dozví o dokončení.

Příklad:

> Rozpoznáváme strukturu dokumentu. Můžete tuto stránku zavřít; rozpracovaný projekt zůstane uložený.

## AI terminologie

Používej:

- `Návrh`
- `Doporučená vazba`
- `Možná duplicita`
- `Míra jistoty návrhu`
- `Vyžaduje lidskou kontrolu`

Nepoužívej:

- `AI rozhodla`
- `Systém ověřil správnost`
- `Garantovaný soulad`
- `Automaticky správně`
- `100% přesnost`

## Míra jistoty

Každé pásmo musí mít slovní vysvětlení:

- **Vysoká jistota návrhu** — texty a struktura se výrazně podobají; stále je potřeba lidské potvrzení.
- **Střední jistota** — vazba je pravděpodobná, ale část kontextu je nejasná.
- **Nízká jistota** — návrh slouží jako podnět ke kontrole.

Nikdy nezobrazuj samotné procento bez interpretace.

## Chybové zprávy

Struktura:

1. co se nepodařilo,
2. co je v bezpečí,
3. jak pokračovat,
4. kde získat pomoc.

### Příklad: nečitelný soubor

> Dokument se nepodařilo přečíst. Původní soubor jsme zachovali. Nahrajte verzi bez hesla nebo zvolte „Předat ke kontrole“.

### Příklad: výpadek zpracování

> Zpracování jsme nedokončili. Vaše nahrané data zůstávají uložená. Zkuste operaci zopakovat; pokud se chyba vrátí, kontaktujte podporu s kódem uvedeným níže.

### Příklad: ztráta oprávnění

> K tomuto projektu už nemáte přístup. Požádejte vlastníka školy o obnovení oprávnění.

Zakázané:

- `Something went wrong`
- `Invalid request`
- `Constraint failed`
- stack trace
- kód chyby bez lidského vysvětlení

## Potvrzovací dialogy

Potvrzení se používá pouze u skutečně rizikových akcí.

Dialog musí uvést konkrétní dopad:

> **Odstranit dokument?**
>
> Dokument a jeho odvozené zpracování budou odstraněny z aktivního projektu. Schválená rozhodnutí zůstanou zachovaná pouze v auditní historii podle retenčních pravidel.

Tlačítka:

- `Ponechat dokument`
- `Odstranit dokument`

Ne:

- `Zrušit`
- `Ano`

## Empty states

Prázdná obrazovka musí říct:

- proč je prázdná,
- co vznikne po prvním kroku,
- co má uživatel udělat.

Příklad:

> Zatím zde nejsou žádné návrhy vazeb. Nejprve potvrďte strukturu nahraného dokumentu.
>
> `Zkontrolovat strukturu`

## Nápověda

Nápověda má být v kontextu. Preferujeme jednu krátkou větu nebo příklad před odkazem na dlouhý manuál.

Tooltip nesmí obsahovat informaci nezbytnou k dokončení úkolu, protože může být nedostupný na dotykovém zařízení nebo pro asistivní technologie.

## E-mailové texty

Každý e-mail má obsahovat:

- kdo a proč píše,
- název školy nebo projektu,
- jednu hlavní akci,
- případný termín,
- bezpečnostní kontext,
- kontakt na podporu.

E-mail nesmí obsahovat citlivé části dokumentu ani dlouhodobě platný přímý odkaz ke stažení.

## Tone of voice

- klidný,
- profesionální,
- podporující,
- přímočarý,
- bez marketingového přehánění,
- bez dětského tónu,
- bez předpokladu technických znalostí.

Produkt má působit jako spolehlivý kolega, ne jako vševědoucí robot ani jako úřední formulář.
