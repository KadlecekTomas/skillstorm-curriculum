# Non-Goals

## Proč tento dokument existuje

Největším rizikem projektu není nedostatek nápadů. Je jím rozšíření scope dříve, než bude ověřena ochota škol platit za hlavní výsledek.

Následující oblasti jsou vědomě mimo první produkt.

## 1. Školní informační systém

Nebudujeme:

- matriku,
- docházku,
- klasifikaci,
- rozvrh,
- omluvenky,
- třídní knihu,
- běžnou komunikaci s rodiči.

Důvod: vysoká migrace, provozní kritičnost, silná konkurence a nulová potřeba pro kurikulární audit.

## 2. LMS

Nebudujeme:

- distribuci domácích úkolů,
- testovací platformu,
- videokurzy,
- žákovské odevzdávání,
- známkování.

Důvod: jiný buyer, jiný workflow a potřeba každodenní adopce učiteli i žáky.

## 3. Žákovské a rodičovské profily

MVP nemá uživatele typu student ani parent.

Důvod: osobní údaje, složitější oprávnění, vyšší adopční bariéra a nulová potřeba pro vstupní produkt.

## 4. Gamifikace

Žádné XP, levely, odznaky, streaky ani avatary.

Důvod: neřeší nákupní problém vedení školy a snižují profesionální důvěryhodnost produktu pro tento use case.

## 5. Automatický generátor celého ŠVP

Produkt neslibuje „ŠVP jedním kliknutím“.

Důvod:

- odborná odpovědnost školy,
- kontext školy nelze bezpečně odvodit pouze z obecného dokumentu,
- vysoké reputační riziko,
- falešný pocit správnosti.

AI navrhuje dílčí vazby a upozornění. Člověk rozhoduje.

## 6. Inspekční nebo právní certifikace

Produkt nevydává závazné prohlášení o souladu a nenahrazuje kontrolní orgán, právníka ani odborného metodika.

## 7. Veřejné srovnávání škol

Nebudujeme rating, žebříček ani veřejný profil „kvality ŠVP“.

Důvod: produkt má pomáhat bezpečné interní práci, ne vytvářet reputační tlak nebo nekvalitní srovnání.

## 8. Marketplace

Nebudujeme prodej materiálů, šablon ani konzultantů.

Důvod: dvoustranné tržiště je samostatný obchodní model a odvádí pozornost od hlavního workflow.

## 9. Nativní mobilní aplikace

Primární práce probíhá na desktopu. Responzivní web je dostatečný.

## 10. Masová samoobsluha od prvního dne

První piloty mohou obsahovat ruční podporu. Cílem je pochopit proces a automatizovat opakující se práci, ne předstírat škálovatelnost.

## 11. Více zemí a rámců současně

Datový model má být přenositelný, ale produkt se nejdříve ověřuje na jednom trhu a jednom podporovaném rámci.

## 12. Komplexní integrace

Bez důkazu nepřidáváme:

- Bakaláře,
- EduPage,
- Školu Online,
- Microsoft Teams,
- Google Classroom,
- obecné integrační marketplace.

Jednoduchý import/export je povolen, pokud přímo odblokuje pilot.

## 13. Vlastní obecný editor dokumentů

Produkt není náhradou Wordu nebo Google Docs. Umožní opravit strukturovaná data a rozhodnutí, nikoliv nabídnout plnohodnotnou sazbu dokumentu.

## 14. Konzultační agentura bez produktizace

Ruční pilot je prostředek učení. Každý ruční krok se měří a vyhodnocuje, zda má být:

- automatizován,
- standardizován,
- zachován jako placená odborná služba,
- odstraněn.

Projekt nesmí nekontrolovaně sklouznout k individuálním zakázkám bez opakovatelného procesu.

## Jak přidat výjimku

Výjimka vyžaduje:

1. konkrétní důkaz z placeného pilotu,
2. popis dopadu na hlavní workflow,
3. bezpečnostní a UX dopad,
4. odhad nákladů,
5. rozhodnutí v `DECISION-LOG.md`,
6. aktualizaci `MVP-SCOPE.md`.

Bez těchto kroků je požadavek automaticky backlog, nikoliv závazek.
