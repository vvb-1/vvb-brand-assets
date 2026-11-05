# VVB Brand Assets

Standardiserade brand-assets för **VVB**.

## Syfte

Detta repo är den godkända källan (source-of-truth) för VVB:s logotyper, favicons och relaterade grafiska assets. Syftet är att alla VVB-dokument, PDF:er, appar och webbprojekt ska återanvända exakt samma godkända filer istället för egna kopior, skärmdumpar eller nya varianter.

## Scope

Detta repo innehåller **enbart statiska assets** (bilder, ikoner, ett manifest och användningsdokumentation) - ingen körbar kod, inget byggsystem och inga beroenden att installera.

Ingår:
<!-- coderabbit-ai-generated:v1 -->

<!-- coderabbit-ai-generated-section:v1:0fbfda0984d9f4e85231645c1befe382c3a8272901be18c0c949fa7504140334 -->

- Godkänd standard och utvalda assets: `assets/vvb-brand-standard-v1/`
- Godkänd källbundle och kompletterande webbikoner: `assets/vvb-logo-ratt-v4/`

<!-- /coderabbit-ai-generated:v1 -->
- Favicons, app-ikoner och webmanifest för webbprojekt
- Originalzip för spårbarhet (`source-bundle/`)
- Manifest med filroller och SHA256-checksummor

Ingår INTE:
- Nya logotypvarianter eller omdesign (se "Viktig regel" nedan)
- Kod, byggskript eller CI/CD-pipelines
- Kund- eller verksamhetsdata (repot är publikt, se "Säkerhet" nedan)

## Snabbstart

Det finns inget att installera eller bygga - använd filerna direkt:

1. Klona repot, eller länka direkt till en fil via en `raw.githubusercontent.com`-URL (se "Raw GitHub URLs" nedan).
2. Välj rätt fil efter behov, se "Rekommenderade filer" nedan.
<!-- coderabbit-ai-generated:v1 -->

<!-- coderabbit-ai-generated-section:v1:2fdbf8d7e79246d95a289853e0374b149569eeb82418f24fe3f0e87d6773e8f8 -->

3. För V4-filer: verifiera vid behov filens integritet mot `assets/vvb-logo-ratt-v4/manifest.json` (SHA256-checksum). Manifestet omfattar endast V4-bundlen.

<!-- /coderabbit-ai-generated:v1 -->

Se `docs/usage.md` för konkreta kodexempel (PDF-header, webbfavicons).

## Struktur

<!-- coderabbit-ai-generated:v1 -->

<!-- coderabbit-ai-generated-section:v1:d48444397bfc6da57231ed18661c601ed4ca434904cdb11056271683c5784ec9 -->

```
assets/vvb-brand-standard-v1/
├── VVB-BRAND-STANDARD.md  Godkänd standard och filroller
└── assets/
    ├── primary/          Primära logotyper och favicons
    └── secondary/        Kompletterande assets
assets/vvb-logo-ratt-v4/
├── logos/           Logotyper i SVG/PNG, olika storlekar och färgvarianter
├── favicons/         Favicons, app-ikoner och site.webmanifest för webbprojekt
├── source-bundle/    Originalzip från designkällan, sparad för spårbarhet
└── manifest.json      Filroller och SHA256-checksummor för samtliga assets
docs/
└── usage.md           Konkreta användningsexempel (PDF-header, webbfavicons)
```

<!-- /coderabbit-ai-generated:v1 -->

## Source of truth

<!-- coderabbit-ai-generated:v1 -->

<!-- coderabbit-ai-generated-section:v1:b67fc87fb803eb816e600037ad61135cc28047ae15db9bfca004cb7dc44c07b4 -->

Aktuell standard: `assets/vvb-brand-standard-v1/VVB-BRAND-STANDARD.md` (godkänd av Kristian 2026-11-05).

Använd filerna i `assets/vvb-brand-standard-v1/assets/` enligt standardens filroller. V4-bundlen i `assets/vvb-logo-ratt-v4/` behålls för befintliga länkar och kompletterande webbikoner (Apple touch icon och webmanifest).

<!-- /coderabbit-ai-generated:v1 -->

## Viktig regel

Automatiserade verktyg ska **inte designa om** VVB-logotypen. Använd befintliga godkända assets exakt, eller lyft separat designbehov innan nya varianter skapas.

## Rekommenderade filer

<!-- coderabbit-ai-generated:v1 -->

<!-- coderabbit-ai-generated-section:v1:1461240d1b7142221cb968c717518d6033fd321d3174bf8f586526319a20fd3f -->

- PDF-/dokumentheader: `assets/vvb-brand-standard-v1/assets/primary/vvb-logo-horizontal-small.png` (på svart yta enligt standarden)
- Stor huvudlogga: `assets/vvb-brand-standard-v1/assets/primary/vvb-monogram-lockup-rod-rod-vit.png`
- Favicon SVG: `assets/vvb-brand-standard-v1/assets/primary/vvb-favicon-red.svg` eller `assets/vvb-brand-standard-v1/assets/primary/vvb-favicon-dark.svg`
- Favicon ICO: `assets/vvb-brand-standard-v1/assets/primary/favicon.ico`

<!-- /coderabbit-ai-generated:v1 -->
- Apple touch icon: `assets/vvb-logo-ratt-v4/favicons/apple-touch-icon.png`
- Webmanifest: `assets/vvb-logo-ratt-v4/favicons/site.webmanifest`

## Raw GitHub URLs

När en extern PDF-renderare behöver absolut publik bild-URL, använd raw.githubusercontent.com-länkar från detta repo.

Exempel PDF-header-logo:

<!-- coderabbit-ai-generated:v1 -->

<!-- coderabbit-ai-generated-section:v1:ab4c09189aed8438a5a2218335cb96eb885944a78eb7f95629e1673a5417dae3 -->

https://raw.githubusercontent.com/vvb-1/vvb-brand-assets/main/assets/vvb-brand-standard-v1/assets/primary/vvb-logo-horizontal-small.png

<!-- /coderabbit-ai-generated:v1 -->

## Manifest

Se `assets/vvb-logo-ratt-v4/manifest.json` för checksum och rekommenderade filroller.

## Test

Inga automatiserade tester - repot innehåller enbart statiska filer utan körbar kod. Verifiering sker manuellt:
- Kontrollera att filens SHA256-checksum matchar posten i `manifest.json`.
- Öppna/rendera filen visuellt (logotyp, favicon) innan den används i ett nytt projekt.

## Deploy eller release

Repot har ingen deploy-pipeline. En "release" av en ny asset-version görs så här:

1. Lägg den nya, godkända bundlen i en egen mapp under `assets/` (t.ex. `vvb-logo-ratt-v5/`) - skriv inte över den gamla mappen.
2. Uppdatera/lägg till ett `manifest.json` för den nya mappen med korrekta SHA256-checksummor.
3. Uppdatera README:ts "Source of truth"-rad till den nya mappen när den nya bundlen är godkänd.
4. Behåll den gamla mappen orörd (bakåtkompatibilitet för befintliga raw-URL:er och länkar i andra VVB-projekt).

## Säkerhet

- Detta repo är **publikt** - allt som committas är synligt för vem som helst på internet.
- Lägg aldrig till kunddata, interna URL:er, nycklar/hemligheter eller annan intern information i något dokument eller någon fil här.
- Endast färdiga, godkända exportfiler ska committas - inga arbetsfiler eller skärmdumpar med potentiellt dold metadata.
- Ändringar går alltid via en egen branch och PR, aldrig direkt mot huvudgrenen (se `REVIEW.md`).

## Drift och felsökning

- **Trasig raw-länk**: kontrollera att sökvägen matchar den faktiska mappstrukturen och att default-branchen fortfarande heter `main`.
- **Checksum matchar inte `manifest.json`**: filen har ändrats sedan manifestet skrevs - jämför mot originalet i `source-bundle/` eller efterfråga en ny godkänd export innan filen används.
- **Fel logotypvariant används i ett projekt**: se "Rekommenderade filer" ovan innan en ny variant tas fram eller en gammal fil ändras.

## Definition of Done

En ändring i detta repo är klar när:

- Endast godkända, oförändrade assets har lagts till (ingen AI-omdesign av logotypen).
- `manifest.json` är uppdaterat med korrekta SHA256-checksummor för alla nya/ändrade filer.
- README.md och `docs/usage.md` speglar den faktiska filstrukturen.
- Diffen är genomgången och innehåller inga hemligheter, kunddata eller annan intern information (repot är publikt).
- PR:n är granskad enligt `REVIEW.md` innan merge.
