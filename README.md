# 7shorts Brand Hub

Die zentrale **Single Source of Truth** für die Marke **7shorts** — Identität, Zielgruppen,
Produkte, Tone of Voice, Messaging und ein fertiger LLM-Prompt, gebündelt als eine Website.

Technisch eine statische Single-Page-Anwendung: eine `index.html` mit eingebettetem CSS und
JavaScript, kein Framework, kein Build-Schritt. Sprachumschaltung DE/EN über `data-de`/`data-en`.

---

## Schnellstart (lokal ansehen)

```bash
# im Repo-Verzeichnis
python3 -m http.server
# dann im Browser: http://localhost:8000
```

Zugangswort (clientseitig, Platzhalter): `7shorts` — siehe §Zugriffsschutz.

---

## Projektstruktur

```
7shorts-brand/
├── index.html        # die gesamte Anwendung (Inhalt + CSS + JS)
├── Brand.md          # inhaltliches Rückgrat — hieraus wird der Hub gespeist
├── CLAUDE.md         # Projektkontext für Claude Code
├── CHANGELOG.md      # Versionshistorie
├── README.md         # diese Datei
├── favicon.svg       # (noch einzufügen, siehe §Assets)
└── assets/
    ├── logo/         # Logo-Varianten
    ├── products/     # Produkt-/Kategorie-Icons (optional)
    └── fonts/        # Brand-Font (optional, DSGVO-konform lokal)
```

---

## Inhaltlich arbeiten — der Workflow

1. **`Brand.md` ist die Quelle.** Inhalte erst dort denken/festhalten, dann in `index.html` umsetzen.
2. **Status-System beachten:** `[FAKT]` / `[VORSCHLAG]` / `[TODO]`. Nichts erfinden — Lücken bleiben TODO.
3. **Pflege per Claude Code:** Im Repo `claude` starten und Aufgaben in natürlicher Sprache
   beschreiben (z. B. „Befülle die Personas aus den neuen Amazon-Daten“). `CLAUDE.md` gibt den Kontext.

---

## Assets — Logo & Favicon einbinden

Das Logo liegt aktuell nur auf der Live-Website. Zum sauberen Einbinden lokal herunterladen
und ins Repo legen:

| Datei | Quelle (7shorts.com) | Ziel im Repo |
|-------|----------------------|--------------|
| Logo mit Claim (SVG) | `/media/image/storage/opc/Verschiedenes/7shorts-logo_claim.svg` | `assets/logo/7shorts-logo.svg` |
| Logo (PNG, 400×108) | `/bilder/intern/shoplogo/Logo-7shorts400x108blau.png` | `assets/logo/7shorts-logo.png` |
| Favicon (SVG) | `/media/image/storage/opc/CD-7shorts/favicon.svg` | `favicon.svg` |

Danach in `index.html` den Fallback-Schriftzug in `.nav-brand` durch ein `<img>` ersetzen, z. B.:

```html
<img src="assets/logo/7shorts-logo.svg" alt="7shorts">
```

> **Regel, die Bilder rettet:** Neue Assets immer mit `git add` versionieren und vor dem Push per
> `git status` prüfen. Fehlt eine referenzierte Datei im Repo, erscheinen live kaputte Bilder.

---

## Branding-Tokens

Alle Farben/Schriften zentral in `index.html` unter `:root` (CSS-Variablen). Verifiziert:
**Primärblau `#0075BE`** (theme-color der Website). Sekundär-/Akzentfarben und Brand-Font sind
Vorschläge bis zur Bestätigung durch 7shorts.

---

## Veröffentlichen (GitHub Pages)

```bash
git init
git add -A && git commit -m "init: 7shorts brand hub v0.1.0"
git remote add origin https://github.com/<org>/7shorts-brand.git
git push -u origin main
```

Dann: Repo → **Settings → Pages → Branch `main` / Root → Save**. Nach ~1 Min. live unter
`https://<org>.github.io/7shorts-brand/`.

### Deploy-Zyklus (jede Änderung)
Inhalt umsetzen → Versionsnummer im Sidebar-Footer (`#verLabel`) hochzählen → `CHANGELOG.md`
ergänzen → committen → pushen → live prüfen (Desktop + mobil).

---

## Versionierung

Semantische Versionsnummer (`MAJOR.MINOR.PATCH`), gepflegt an **zwei** Stellen synchron:
1. Sidebar-Footer in `index.html` (`#verLabel`)
2. `CHANGELOG.md`

- **PATCH** — Tippfehler, kleine Textkorrekturen
- **MINOR** — neue Inhalte/Sektionen, [VORSCHLAG] → [FAKT]
- **MAJOR** — strukturelle Umbauten, neue Hauptsektionen

---

## Zugriffsschutz (wichtig)

Der Hub hat ein **clientseitiges Passwort-Overlay**. Das Wort steht im ausgelieferten HTML und
ist damit **kein echter Schutz**. Vor einer Auslieferung an Dritte:
- echten Schutz davorschalten (z. B. Cloudflare Access oder Host mit serverseitigem Login), oder
- bewusst akzeptieren, dass der Inhalt faktisch öffentlich ist.

Das Platzhalter-Wort in `index.html` (`ACCESS_WORD`) vor Live-Gang ändern.

---

## Weiterentwicklung — offene Punkte

Siehe das **Offene-Punkte-Register** am Ende von `Brand.md`. Kurzfassung:
Mission/Vision/Werte bestätigen · Personas mit echten Daten validieren · Messaging-Pillars mit
Proof Points härten · offizielle Farben/Font klären · Logo ins Repo · Eigenmarken-Roadmap
konkretisieren · JTL→Shopify-Fahrplan · Kundenstimmen mit Quelle · EN-Übersetzungen ergänzen.
