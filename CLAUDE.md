# CLAUDE.md — Projektkontext 7shorts Brand Hub

> Diese Datei gibt Claude Code dauerhaften Kontext für dieses Repo. Beim Arbeiten im Terminal
> immer zuerst diese Datei und `Brand.md` lesen.

## Was dieses Projekt ist
Ein statischer, zweisprachig vorbereiteter (DE jetzt / EN strukturell) **Brand Hub** für die
Marke **7shorts** — eine Single-Page-Anwendung (`index.html`) mit inline CSS/JS, ohne Framework,
ohne Build-Schritt. Gehostet über GitHub Pages, gepflegt über Claude Code.

7shorts ist ein **B2C-Online-Händler** für Herren-Unterwäsche und Basics. Schwerpunkt aktuell
Amazon-Marktplatz, eigener Shop unter 7shorts.com (aktuell JTL-Shop, Migration zu Shopify geplant).
Aktuell **keine Eigenmarke** — perspektivisch geplant.

## Wichtigste Dateien
- `index.html` — die gesamte Anwendung (Inhalt + CSS + JS). Sektionen werden per JS ein-/ausgeblendet.
- `Brand.md` — **inhaltliches Rückgrat.** Hieraus werden die HTML-Sektionen und der LLM-Prompt gespeist.
- `CHANGELOG.md` — Versionshistorie (semantisch, Start 0.1.0).
- `README.md` — Setup, Deploy-Zyklus, Asset-Beschaffung.
- `assets/logo/` — Logo-Dateien (noch zu befüllen, siehe README §Assets).

## Inhalts-Status-System (gilt überall)
- **[FAKT]** / Tag „Fakt“ — von 7shorts oder 7shorts.com verifiziert.
- **[VORSCHLAG]** / Tag „Vorschlag“ — Entwurf, muss bestätigt/ersetzt werden.
- **[TODO]** / Tag „TODO“ — offen; Inhalt muss vom Markeninhaber kommen.

## Harte Regeln (NICHT brechen)
1. **Markeninhalte kommen von 7shorts, nie aus dem Modell.** Fehlt etwas → als TODO markieren,
   nicht erfinden.
2. **Jeder sichtbare Text** in `index.html` bekommt `data-de` UND `data-en`. (EN darf aktuell
   eine erste Übersetzung oder Kopie sein, aber das Attribut muss da sein.)
3. **Branding-Tokens** nur zentral in `:root` (CSS-Variablen) pflegen. Primärblau = `#0075BE`.
4. **Pro veröffentlichtem Stand genau eine Versionsnummer** im Sidebar-Footer (`#verLabel`) UND
   ein CHANGELOG-Eintrag.
5. **Neue Assets vor dem Push mit `git add` versionieren** (sonst kaputte Bilder live). Vor Push
   `git status` prüfen.
6. **Clientseitiges Passwort ist KEIN echter Schutz** — vor einer echten Auslieferung klären
   (siehe README §Zugriffsschutz).

## Typische Aufgaben
- „Befülle Sektion X aus Brand.md“ → Brand.md lesen, Sektion in index.html aktualisieren, beide
  Sprachattribute setzen, Version + CHANGELOG hochzählen.
- „Mach den Vorschlag in Sektion Y zum Fakt“ → Tag von „Vorschlag“ auf „Fakt“ ändern in index.html
  UND Status in Brand.md von [VORSCHLAG] auf [FAKT].
- „Füge Logo ein“ → Datei unter assets/logo/ ablegen, Fallback-Schriftzug in `.nav-brand` durch
  `<img>` ersetzen, in Brand.md §11 Status aktualisieren.

## Deploy-Zyklus
Inhalt umsetzen → Version im Sidebar-Footer hochzählen → CHANGELOG ergänzen → committen → pushen
→ live prüfen (Desktop + mobil).

## Lokal ansehen
```bash
python3 -m http.server   # dann http://localhost:8000
```
