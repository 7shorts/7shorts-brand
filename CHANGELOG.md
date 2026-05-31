# Changelog — 7shorts Brand Hub

Alle nennenswerten Änderungen an diesem Hub. Format angelehnt an [Keep a Changelog](https://keepachangelog.com/de/),
Versionierung nach [SemVer](https://semver.org/lang/de/).

## [0.6.0] — 2026-05-31
### Hinzugefügt
- Logo (`assets/logo/7shorts-logo.svg`) in Sidebar (`.nav-brand`) als `<img>` eingebunden.
- Logo in Visuelles-Sektion (Sektion 08) als `<img>` eingebunden.

### Entfernt
- Text-Fallback `.logo-fallback` und separater Claim-Text `.nav-claim` aus Sidebar entfernt
  (Claim ist im SVG-Logo enthalten).
- Ungenutzte CSS-Regeln `.nav-brand .logo-fallback` und `.nav-claim` entfernt.

### Geändert
- Logo-Vorschau in Visuelles-Sektion: Hintergrund von `var(--brand-tint)` auf `var(--surface)`
  (Weiß) geändert — blaues Logo auf weißem Grund.

## [0.5.0] — 2026-05-31
### Entfernt
- Clientseitiges Passwort-Overlay (`#gate`, `.gate-card`, CSS/HTML/JS) vollständig entfernt —
  Hub lädt jetzt direkt ohne Zugangssperre.

## [0.4.0] — 2026-05-31
### Geändert
- Navigation: Sidebar ist jetzt auf **allen Bildschirmbreiten** eine echte vertikale linke Spalte
  (kein Dropdown, kein Hamburger-Overlay).
- `@media (max-width: 880px)`: Sidebar-Breite reduziert auf 210 px, bleibt im Dokumentfluss.
- `@media (max-width: 500px)`: Sidebar-Breite 160 px; Padding und Schriftgröße der Nav-Links
  leicht reduziert für sehr enge Viewports.
- `position: fixed`, `transform: translateX(-100%)`, `.open`-Toggle, `.scrim`-Overlay und
  `.menu-btn` (Hamburger) komplett entfernt.

## [0.1.0] — 2026-05-31
### Hinzugefügt
- Erstes Grundgerüst des Brand Hubs (`index.html`) als zweisprachig vorbereitete Single-Page-App.
- 11 Sektionen: Identität, Unternehmen, Zielgruppen, Customer Journey, Produkte, Eigenmarke,
  Marktplatz & Kanäle, Visuelles, Tone of Voice, Messaging, LLM/AI.
- `Brand.md` als inhaltliches Rückgrat, befüllt mit verifizierten 7shorts.com-Fakten und klar
  markierten Vorschlägen ([FAKT] / [VORSCHLAG] / [TODO]).
- Branding-Token-System mit verifiziertem Primärblau `#0075BE`.
- DE/EN-Sprachumschaltung über `data-de`/`data-en` (DE befüllt, EN als erste Fassung/Struktur).
- Fertiger On-Brand-LLM-System-Prompt (DE) in der LLM/AI-Sektion.
- `CLAUDE.md`, `README.md`, `.gitignore`.

### Offen / nächste Schritte
- Logo & Favicon ins Repo legen (aktuell Fallback-Schriftzug).
- Mission/Vision/Werte, Personas, Messaging-Pillars von 7shorts bestätigen lassen.
- EN-Übersetzungen vervollständigen.
- Echten Zugriffsschutz vor Auslieferung klären.
