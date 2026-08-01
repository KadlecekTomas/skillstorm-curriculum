# Domain Model

## Cíl

Datový model musí podporovat auditovatelné mapování kurikula bez závislosti na jednom národním názvosloví. České termíny patří do lokalizační a obsahové vrstvy, nikoliv do univerzálního jádra.

## Hlavní agregáty

## Organization

Reprezentuje školu nebo pilotní organizaci.

Pole:

- `id`
- `name`
- `countryCode`
- `organizationType`
- `status`
- `createdAt`, `updatedAt`, `deletedAt`

Invarianta: všechna projektová data jsou vlastněna právě jednou organizací.

## User

Identita člověka. Přístup k organizaci vzniká pouze přes membership.

Pole:

- `id`
- `email`
- `name`
- `status`
- autentizační metadata

## Membership

Vazba uživatele na organizaci.

Role pro MVP:

- `OWNER`
- `COORDINATOR`
- `REVIEWER`
- `VIEWER`
- interně oddělený `SUPPORT` s kontrolovaným přístupem

Invarianta: role je vždy vyhodnocena v kontextu konkrétní organizace a projektu.

## CurriculumProject

Řízený audit jedné školy vůči jedné verzi referenčního rámce.

Pole:

- `id`
- `organizationId`
- `name`
- `frameworkVersionId`
- `ownerMembershipId`
- `status`
- `dueAt`
- `completedAt`
- `createdAt`, `updatedAt`, `deletedAt`

Invarianta: projekt nesmí v průběhu tiše změnit referenční verzi.

## SourceDocument

Původní nahraný soubor.

Pole:

- `id`
- `projectId`
- `originalFileName`
- `mimeType`
- `sizeBytes`
- `storageKey`
- `checksum`
- `version`
- `processingStatus`
- `uploadedBy`
- `uploadedAt`
- `deletedAt`

Invarianta: původní soubor je neměnný; nová verze je nový záznam.

## DocumentNode

Strukturovaný prvek získaný z dokumentu.

Příklady typů:

- `DOCUMENT`
- `SECTION`
- `SUBJECT`
- `GRADE_BAND`
- `OUTCOME`
- `CONTENT_ITEM`
- `NOTE`
- `UNKNOWN`

Pole:

- `id`
- `documentId`
- `parentId`
- `nodeType`
- `title`
- `text`
- `order`
- `sourceLocator`
- `extractionConfidence`
- `reviewStatus`
- `reviewedBy`, `reviewedAt`

`sourceLocator` musí umožnit návrat k původní stránce, odstavci nebo jiné dohledatelné pozici.

## Framework

Obecná definice národního nebo jiného referenčního rámce.

Pole:

- `id`
- `countryCode`
- `code`
- `name`
- `authority`

## FrameworkVersion

Neměnná publikovaná verze rámce.

Pole:

- `id`
- `frameworkId`
- `versionLabel`
- `effectiveFrom`
- `sourceUrl`
- `sourceChecksum`
- `status`
- `publishedAt`

Invarianta: změna obsahu vytváří novou verzi.

## FrameworkNode

Hierarchický prvek rámce.

Pole:

- `id`
- `frameworkVersionId`
- `parentId`
- `code`
- `nodeType`
- `title`
- `text`
- `order`
- `sourceLocator`
- `metadata`

## MappingSuggestion

Automaticky nebo ručně navržená vazba mezi `DocumentNode` a `FrameworkNode`.

Pole:

- `id`
- `projectId`
- `documentNodeId`
- `frameworkNodeId`
- `origin` (`AI`, `RULE`, `HUMAN`)
- `confidenceScore`
- `confidenceBand`
- `rationale`
- `modelRunId`
- `status`
- `createdAt`

Stavy:

- `PROPOSED`
- `ACCEPTED`
- `REJECTED`
- `SUPERSEDED`

Invarianta: `PROPOSED` nikdy není považováno za schválené pokrytí.

## MappingDecision

Lidské rozhodnutí nad návrhem.

Pole:

- `id`
- `mappingSuggestionId`
- `decision`
- `decidedBy`
- `reason`
- `createdAt`

Rozhodnutí jsou append-only. Oprava vytváří nové rozhodnutí, nikoliv přepsání historie.

## Finding

Problém nebo doporučení zjištěné analýzou.

Typy:

- `POSSIBLE_GAP`
- `POSSIBLE_DUPLICATION`
- `LOW_CONFIDENCE`
- `STRUCTURE_CONFLICT`
- `MISSING_DECISION`
- `VERSION_CONFLICT`

Pole:

- `id`
- `projectId`
- `findingType`
- `severity`
- `title`
- `description`
- `sourceReferences`
- `status`
- `assigneeMembershipId`
- `resolvedBy`
- `resolvedAt`

## Comment

Diskuse vázaná na konkrétní node, mapping nebo finding. Pro MVP stačí jednoduché chronologické komentáře bez sociálních funkcí.

## Export

Neměnný snapshot výstupu.

Pole:

- `id`
- `projectId`
- `exportType`
- `format`
- `projectRevision`
- `storageKey`
- `checksum`
- `createdBy`
- `createdAt`

## AuditEvent

Dohledatelná událost.

Pole:

- `id`
- `organizationId`
- `projectId`
- `actorId`
- `action`
- `entityType`
- `entityId`
- `before`
- `after`
- `ipAddress`
- `userAgent`
- `createdAt`

Audit nesmí ukládat hesla, tokeny ani celý obsah dokumentů bez důvodu.

## AIModelRun

Reprodukovatelný záznam automatického zpracování.

Pole:

- `id`
- `projectId`
- `operationType`
- `provider`
- `model`
- `promptVersion`
- `inputReferences`
- `outputHash`
- `status`
- `startedAt`, `completedAt`
- nákladová metadata bez citlivého obsahu

## Vztahy ve zkratce

```text
Organization
 ├─ Membership ─ User
 └─ CurriculumProject
     ├─ SourceDocument ─ DocumentNode
     ├─ FrameworkVersion ─ FrameworkNode
     ├─ MappingSuggestion ─ MappingDecision
     ├─ Finding
     ├─ Comment
     ├─ Export
     ├─ AIModelRun
     └─ AuditEvent
```

## Co nepřebírat ze širokého SkillStorm schématu

Do tohoto produktu se bez důvodu nepřenáší:

- Student,
- Parent,
- Classroom,
- Submission,
- Question,
- XP a level,
- MaterialPurchase,
- testové assignmenty.

Sdílená značka neznamená sdílenou databázi ani povinnost přenést celý starý model.
