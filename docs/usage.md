# Användning i VVB-projekt

## PDFNoodle / HTML till PDF

Använd denna som standard för faktura-/servicedokument-header:

```text
https://raw.githubusercontent.com/vvb-1/vvb-brand-assets/main/assets/vvb-logo-ratt-v4/logos/04b-main-logo-horisontell-liten-ren_4x.png
```

Sätt explicit storlek i HTML/CSS enligt PDF best practices, exempel:

```html
<img class="vvb-logo" src="https://raw.githubusercontent.com/vvb-1/vvb-brand-assets/main/assets/vvb-logo-ratt-v4/logos/04b-main-logo-horisontell-liten-ren_4x.png" width="220" height="59" alt="Vi Vet Bil AB">
```

```css
.vvb-logo {
  width: 220px;
  height: auto;
  object-fit: contain;
  page-break-inside: avoid;
}
```

## Webbfavicons

Kopiera filerna från `assets/vvb-logo-ratt-v4/favicons/` till projektets public-root och använd `html-head-snippet.txt` som startpunkt.

## Förbud

- Skapa inte ny VVB-logotyp med AI.
- Ändra inte färger/form utan Kristians uttryckliga godkännande.
- Använd inte screenshot-crop som source om dessa assets finns.
