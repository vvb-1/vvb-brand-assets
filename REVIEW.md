# REVIEW.md

## PR-riskklassning

- **Docs-only:** ändringar enbart i `README.md`, `AGENTS.md`, `REVIEW.md`, `CHANGELOG.md` eller `docs/`.
- **Low risk:** tillägg av nya, redan godkända asset-filer (t.ex. en helt ny version-mapp under `assets/`) utan att röra befintliga filer.
- **Medium risk:** ersättning av en befintlig, redan publicerad assetfil, eller ändring av checksummor/filroller i `manifest.json`.
- **High risk:** allt som rör ny design eller omdesign av logotypen, borttagning av assets, eller ändringar av repots synlighet/behörigheter.

## Obligatorisk checklista

- [ ] **Dokumentation:** README och `docs/` speglar den faktiska filstrukturen efter ändringen.
- [ ] **Säkerhet:** diffen innehåller inga hemligheter, kunddata, interna URL:er eller annan intern information (repot är publikt - dubbelkolla extra noga).
- [ ] **Test:** SHA256-checksumman för varje ny/ändrad fil stämmer i `manifest.json` (om tillämpligt).
- [ ] **VVB-domän:** en ny/ändrad logotyp är uttryckligen godkänd av ansvarig person - inte AI-genererad eller omdesignad.
- [ ] **Risk/rollback:** ändringen kan återställas via git-historiken; inga destruktiva raderingar utan uttryckligt godkännande.

## Merge-gate

- PR:n ska vara granskad innan merge.
- PR-titeln måste följa conventional commits (`fix|feat|docs|style|refactor|perf|test|build|ci|chore|revert`), vilket verifieras automatiskt via `.mergify.yml`.
- Merga inte om checklistan ovan inte är komplett ikryssad.
