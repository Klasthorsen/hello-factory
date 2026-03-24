# Agents-regler för projektet

## Syfte
Detta dokument styr hur AI-kodagenter arbetar i projektet, från ändring till deploy.

## Omfattning
- Gäller endast AI-kodagenter.
- Alla kodändringar ska följa detta dokument.

## Arbetsprinciper
- Gör små, tydliga och granskningsbara ändringar.
- Följ befintlig kodstil, struktur och beroenden.
- Undvik destruktiva kommandon utan uttryckligt godkännande.
- Lägg aldrig in hemligheter i kod, loggar eller commits.

## Obligatoriskt arbetsflöde
1. Analysera uppgiften och berörda filer.
2. Planera ändringen kort.
3. Implementera minsta säkra lösning.
4. Kör relevanta kontroller (lint/test/typecheck där det finns).
5. Skapa PR och invänta godkänd review.
6. Merga till `main` och verifiera deploy.

## GitHub: obligatorisk koppling och publicering
Projektet ska ligga i ett GitHub-repo och använda `main` som produktionsgren.

### Standardflöde (nytt repo)
1. Initiera lokalt repo.
2. Skapa GitHub-repo med namn `hello-factory`.
3. Koppla `origin` till GitHub-repot.
4. Push av `main` till `origin`.

## Branch- och PR-policy
- Inga direkta commits till `main`.
- Allt arbete görs i feature-branch.
- PR till `main` är obligatorisk.
- Minst en godkänd review krävs innan merge.

## Vercel: obligatorisk deployment via GitHub-integration
1. Skapa ett nytt Vercel-projekt.
2. Importera GitHub-repot `hello-factory` i Vercel.
3. Sätt `main` som production deploy.
4. Använd PR-branches för preview deploys.
5. Verifiera preview innan merge till `main`.

## Kort checklista för hemligheter och miljövariabler
- Inga API-nycklar eller tokens i repositoryt.
- Sätt hemligheter i GitHub Secrets och/eller Vercel Environment Variables.
- Säkerställ att nödvändiga variabler finns i både Preview och Production.

## Definition of Done
- Kod klar och lokalt verifierad.
- PR skapad och godkänd.
- Merge till `main` genomförd.
- Production deploy i Vercel verifierad utan fel.

## Rapporteringsformat från agent
- Kort sammanfattning av ändringen.
- Lista över ändrade filer.
- Resultat från körda kontroller.
- Status för PR/deploy.
