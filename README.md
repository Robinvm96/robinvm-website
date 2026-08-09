# robinvm-website

Persönliche Portfolio-Website von Robin von Malottki — Data Analyst mit Fokus auf Analytics, Machine Learning und n8n-/AI-gestützter Workflow-Automatisierung. Zweisprachig (DE/EN), mit Hell-/Dunkelmodus, Case-Study-Übersicht, Referenzen, Blog-Verweisen und Kontaktformular.

## Womit es gebaut wurde

Die Seite kommt aus [Claude Design](https://claude.ai/design) und nutzt dessen Komponenten-Templateformat:

- **`Portfolio.dc.html`** — die Seite selbst. Kein reines statisches HTML, sondern ein Template mit `{{ }}`-Platzhaltern und `<sc-for>`/`<sc-if>`-Tags, das erst im Browser gerendert wird.
- **`support.js`** — die Render-Engine, die dieses Template zur Laufzeit im Browser in echtes HTML umwandelt. Zwingend erforderlich, ohne sie bleibt die Seite leer.
- **`_ds/modernist-.../`** — das verwendete Design-System ("Modernist"): `styles.css` (Farb-/Typografie-/Abstands-Tokens plus Komponentenklassen), dazu Metadaten und Doku (`readme.md`, `_ds_manifest.json`, `_adherence.oxlintrc.json`) als Referenz.
- **`assets/robin-portrait.png`** — Portraitfoto.

Alle Projekt- und Blog-Bilder werden extern von Pexels bzw. Medium eingebunden, kein Build-Schritt, kein npm/Framework nötig.

## Lokal starten

Da `Portfolio.dc.html` per `fetch`/Skript nachlädt (`support.js`, `styles.css`), reicht ein direkter Doppelklick auf die Datei (`file://`) je nach Browser nicht — stattdessen über einen einfachen lokalen Webserver öffnen, z. B.:

```bash
python -m http.server 8000
```

Danach im Browser: [http://localhost:8000/Portfolio.dc.html](http://localhost:8000/Portfolio.dc.html)

Alternativ jeder andere statische Server (`npx serve`, VS-Code-Live-Server, …).

## Deployment

Statische Seite — lässt sich unverändert auf GitHub Pages, Netlify, Vercel o. ä. hosten. Kein Server-Backend nötig.

## Offene Punkte

- Der "Resume"-Button (`links.resume` in `Portfolio.dc.html`) verlinkt noch auf `#` — sobald ein Lebenslauf-PDF vorliegt, hier auf die Datei verweisen.
- Das Kontaktformular ist als Platzhalter verdrahtet (`handleSubmit`) — für den Live-Betrieb an einen Formular-Dienst wie Formspree oder Resend anbinden.
