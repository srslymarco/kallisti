# CLAUDE.md – Arbeitsregeln für καλλιστι

Dieses Repo ist die Quelle der Website https://srslymarco.github.io/kallisti/ (GitHub Pages, Jekyll, `baseurl: /kallisti`). Autor: Marco (srslymarco). Alle Texte sind deutschsprachige Essays über Eris, Zwietracht, Religion und Atheismus.

## Struktur

- `essays/<slug>.md` – ein Essay pro Datei, Slug in Kleinbuchstaben, Umlaute als `ae`/`oe`/`ue`/`ss`
- `bilder/` – Abbildungen (PNG), Dateinamen mit Großbuchstaben am Wortanfang, z. B. `St-Gravitas.png`
- `README.md` – Startseite mit nummerierter Textliste; neue Essays unten anhängen
- `_layouts/default.html` – einziges Layout, keine externen Ressourcen (keine Fonts, kein Tracking, keine CDNs); das ist Voraussetzung für die Aussagen in `DATENSCHUTZ.md`
- `_drafts/` – für unveröffentlichte Texte verwenden, nicht `essays/`

## Aufbau eines Essays

```markdown
---
title: Titel des Essays
---

# Titel des Essays

Fließtext …

---

![Bildunterschrift](../bilder/Datei.png)
```

- Front Matter mit `title` ist Pflicht (sonst trägt der Browser-Tab nur „καλλιστι“).
- Links im README relativ ohne führenden Schrägstrich: `essays/slug.md`.
- Bilder aus Essays mit `../bilder/…` einbinden.

## Typografie (verbindlich)

- Deutsche Anführungszeichen: öffnend „ (U+201E), schließend “ (U+201C). Niemals `"` (U+0022), niemals ” (U+201D). Vor jedem Commit prüfen:
  `grep -Pn '[\x{22}\x{201D}]' essays/*.md README.md | grep -v ':title:'` (mit UTF-8-Locale, z. B. `LC_ALL=C.UTF-8`) darf nichts finden.
- Gedankenstrich mit Leerzeichen: ` – ` (U+2013), kein Bindestrich als Gedankenstrich.
- Griechisch bleibt Griechisch (καλλιστι, Namen der Goldenen Äpfel in Majuskeln mit Transliteration).

## Stil und Lektorat

- Die Texte sind Marcos eigene Stimme: Ich-Perspektive, Du-Anrede an die Lesenden, trocken-pathetisch. Bei Korrekturen nur Fehler beheben (Rechtschreibung, Grammatik, Kommasetzung, Typografie), keinen Stil glätten und nichts umformulieren, was nicht falsch ist.
- Inhaltliche Anmerkungen gehören in die PR-Beschreibung oder den Chat, nicht still in den Text.
- Vor dem Veröffentlichen neuer Texte ein Korrektorat nach dem Skill `deutsches-lektorat` durchführen.
- Begriffe konsistent halten: „Erisentum“ (Marcos Position), „orthodoxer Discordianismus“ (die Principia-Tradition), „die Göttin“, „der Heilige Ernst / St. Gravitas“, „die 5 Heiligen Kränkungen“, „die 5 Goldenen Äpfel“.

## Workflow

- Änderungen auf einem eigenen Branch, dann Pull Request gegen `main`; nicht direkt auf `main` pushen.
- Commit-Nachrichten auf Deutsch, knapp: was und warum.
- Rechtstexte (`IMPRESSUM.md`, `DATENSCHUTZ.md`, `LICENSE.md`) nur auf ausdrücklichen Wunsch ändern.
