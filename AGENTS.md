# AGENTS.md

## Repo-identitet

- **Namn:** vvb-brand-assets
- **Ägare:** Vi Vet Bil AB (VVB)
- **Typ:** Rent tillgångs-repo (statiska brand assets - logotyper, favicons, manifest). Ingen körbar kod, inget byggsystem.
- **Synlighet:** PUBLIKT - synligt för alla på internet. Detta repo behöver vara publikt eftersom `raw.githubusercontent.com`-länkar till logotypfilerna används av externa verktyg (t.ex. PDF-renderare), se README.

## Läsordning

1. `README.md` - source-of-truth, godkända filer, snabbstart, struktur.
2. `docs/usage.md` - konkreta användningsexempel (PDF-header, webbfavicons).
3. `assets/vvb-logo-ratt-v4/manifest.json` - filroller och SHA256-checksummor.
4. `REVIEW.md` - PR-riskklassning och checklista innan en ändring mergas.

## Förbjudna åtgärder

- Designa aldrig om eller generera nya varianter av VVB-logotypen, inklusive med AI/bildgenerering.
- Lägg aldrig till kunddata, interna URL:er, hemligheter, API-nycklar eller annan intern information - repot är publikt.
- Radera aldrig godkända assets eller originalet i `source-bundle/` utan uttrycklig instruktion från användaren.
- Pusha aldrig direkt mot huvudgrenen (`main`) - använd alltid branch + PR.

## Säkerhetsregler

- Repot är publikt: allt som committas är synligt för alla. Granska alltid diffen extra noga för känslig information innan commit, eftersom detta repo har lägre tröskel för skada än VVB:s privata repon.
- Endast färdiga, godkända exportfiler får läggas till - inga arbetsfiler, skärmdumpar eller filer med potentiellt dold metadata.
- Ändringar i redan godkända assets (färg, form, filinnehåll) kräver uttryckligt godkännande innan de committas (se README > Viktig regel).

## Branch-/commit-regler

- Arbeta alltid i en egen branch, aldrig direkt mot `main`.
- Öppna PR för alla ändringar; merge sker efter granskning enligt `REVIEW.md`.
- Använd conventional commits (`docs:`, `fix:`, `feat:`, `chore:` m.fl.) - PR-titeln måste följa detta format, vilket kontrolleras av `.mergify.yml`.

## Testkrav

Repot har ingen körbar kod och därför inga automatiserade tester. Innan en PR mergas:

- Verifiera att SHA256-checksumman för varje ny/ändrad fil stämmer i `manifest.json`.
- Öppna/granska filen visuellt (logotyp/favicon) för att bekräfta att den är korrekt och oförändrad jämfört med den godkända källan.

## Stop-villkor

Stanna och fråga användaren innan du:

- Skapar en ny logotypvariant eller ändrar färg/form på en befintlig, godkänd logotyp.
- Tar bort en fil under `assets/`.
- Lägger till uppgifter (URL:er, kommandon, checksummor, filroller) du inte kan verifiera mot faktiska filer i repot.

## Definition of Done

Se README.md > "Definition of Done".
