# Dokumentační mapa

Tento adresář je jediný zdroj pravdy pro produktovou, UX, obchodní a technickou podobu SkillStorm Curriculum.

## Jak dokumenty číst

1. **Směr:** [`PRODUCT-DOCTRINE.md`](PRODUCT-DOCTRINE.md), [`PRODUCT-VISION.md`](PRODUCT-VISION.md)
2. **Uživatelé a rozhraní:** [`USER-PERSONAS.md`](USER-PERSONAS.md), [`UX-UI-PRINCIPLES.md`](UX-UI-PRINCIPLES.md), [`COPY-GUIDELINES.md`](COPY-GUIDELINES.md), [`INFORMATION-ARCHITECTURE.md`](INFORMATION-ARCHITECTURE.md)
3. **Ověření trhu:** [`PROBLEM-VALIDATION.md`](PROBLEM-VALIDATION.md), [`RESEARCH-BACKLOG.md`](RESEARCH-BACKLOG.md), [`INTERVIEW-GUIDE.md`](INTERVIEW-GUIDE.md)
4. **Nabídka a obchod:** [`PILOT-OFFER.md`](PILOT-OFFER.md), [`BUSINESS-MODEL.md`](BUSINESS-MODEL.md), [`SUCCESS-METRICS.md`](SUCCESS-METRICS.md)
5. **První produkt:** [`MVP-SCOPE.md`](MVP-SCOPE.md), [`PRIMARY-USER-FLOW.md`](PRIMARY-USER-FLOW.md), [`NON-GOALS.md`](NON-GOALS.md)
6. **Návrh systému:** [`DOMAIN-MODEL.md`](DOMAIN-MODEL.md), [`ARCHITECTURE.md`](ARCHITECTURE.md), [`SECURITY-PRIVACY.md`](SECURITY-PRIVACY.md), [`AI-GOVERNANCE.md`](AI-GOVERNANCE.md)
7. **Realizace a provoz:** [`ROADMAP.md`](ROADMAP.md), [`PILOT-RUNBOOK.md`](PILOT-RUNBOOK.md), [`DECISION-LOG.md`](DECISION-LOG.md)
8. **Vývojová pravidla:** [`../CONTRIBUTING.md`](../CONTRIBUTING.md)

## Stav tvrzení

Každé důležité tvrzení má patřit do jedné z kategorií:

- **FACT** — doložené zdrojem nebo reálnými daty.
- **HYPOTHESIS** — předpoklad, který musí být ověřen.
- **DECISION** — vědomé rozhodnutí týmu.
- **OPEN** — nezodpovězená otázka.

Dokument nesmí převádět hypotézu na fakt pouze proto, že se opakovala v několika diskusích.

## Priorita při konfliktu

1. `PRODUCT-DOCTRINE.md`
2. `MVP-SCOPE.md`
3. `NON-GOALS.md`
4. `ROADMAP.md`
5. `DECISION-LOG.md`
6. ostatní dokumenty

Při konfliktu se nižší dokument upraví. Scope se nerozšiřuje bez záznamu v `DECISION-LOG.md` a bez jasného důkazu, že změna zvyšuje šanci na placený pilot nebo snižuje zásadní riziko.

## Údržba dokumentace

- Každá významná produktová změna upraví odpovídající dokument ve stejném PR.
- Změna scope vyžaduje aktualizaci `MVP-SCOPE.md`, `NON-GOALS.md` a `DECISION-LOG.md`.
- Změna AI workflow vyžaduje aktualizaci `AI-GOVERNANCE.md`.
- Změna práce s daty vyžaduje aktualizaci `SECURITY-PRIVACY.md`.
- Ověřená nebo vyvrácená hypotéza se propíše do `PROBLEM-VALIDATION.md` a `RESEARCH-BACKLOG.md`.
