# VVB Brand Assets

Standardiserade brand-assets för **VVB**.

## Syfte

Detta repo är den godkända källan (source-of-truth) för VVB:s logotyper, favicons och relaterade grafiska assets. Syftet är att alla VVB-dokument, PDF:er, appar och webbprojekt ska återanvända exakt samma godkända filer istället för egna kopior, skärmdumpar eller nya varianter.

## Scope

Detta repo innehåller **enbart statiska assets** (bilder, ikoner, ett manifest och användningsdokumentation) - ingen körbar kod, inget byggsystem och inga beroenden att installera.

Ingår:
- Godkänd logotyp-bundle: `assets/vvb-logo-ratt-v4/`
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
3. Verifiera vid behov filens integritet mot `assets/vvb-logo-ratt-v4/manifest.json` (SHA256-checksum).

Se `docs/usage.md` för konkreta kodexempel (PDF-header, webbfavicons).

## Struktur

```
assets/vvb-logo-ratt-v4/
├── logos/           Logotyper i SVG/PNG, olika storlekar och färgvarianter
├── favicons/         Favicons, app-ikoner och site.webmanifest för webbprojekt
├── source-bundle/    Originalzip från designkällan, sparad för spårbarhet
└── manifest.json      Filroller och SHA256-checksummor för samtliga assets
docs/
└── usage.md           Konkreta användningsexempel (PDF-header, webbfavicons)
```

## Source of truth

Aktuell standard: `assets/vvb-logo-ratt-v4/`

Dessa filer är den godkända asset-bundlen och ska användas som source-of-truth i VVB-dokument, PDF:er, appar och webbprojekt.

## Viktig regel

Automatiserade verktyg ska **inte designa om** VVB-logotypen. Använd befintliga godkända assets exakt, eller lyft separat designbehov innan nya varianter skapas.

## Rekommenderade filer

- PDF-/dokumentheader: `assets/vvb-logo-ratt-v4/logos/04b-main-logo-horisontell-liten-ren_4x.png`
- Stor huvudlogga: `assets/vvb-logo-ratt-v4/logos/01-main-logo-stor_4x.png`
- Favicon ICO: `assets/vvb-logo-ratt-v4/favicons/favicon.ico`
- Apple touch icon: `assets/vvb-logo-ratt-v4/favicons/apple-touch-icon.png`
- Webmanifest: `assets/vvb-logo-ratt-v4/favicons/site.webmanifest`

## Raw GitHub URLs

När en extern PDF-renderare behöver absolut publik bild-URL, använd raw.githubusercontent.com-länkar från detta repo.

Exempel PDF-header-logo:

https://raw.githubusercontent.com/vvb-1/vvb-brand-assets/main/assets/vvb-logo-ratt-v4/logos/04b-main-logo-horisontell-liten-ren_4x.png

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
