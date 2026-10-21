# abc.pramer.com (Anahata Business Circle) – Arbeitsanleitung für Claude

Landingpage für den **Anahata Business Circle** von **Mag. Gerlinde Pramer** – Abende für Führungskräfte in Wien, Linz und Graz. Sie pflegt die Seite selbst – mit Claude. Sie ist keine Entwicklerin: Erkläre alles in einfachen Worten, ohne Fachbegriffe, auf Deutsch.

## So arbeitest du in diesem Repo

- **Nie direkt auf `main` arbeiten.** Jede Änderung in einem eigenen Branch, danach einen Pull Request mit einer kurzen deutschen Beschreibung öffnen.
- **Kleine, gezielte Änderungen.** Nur das ändern, worum gebeten wurde.
- Wenn ein Wunsch unklar ist: **zuerst nachfragen**, dann ändern.
- Am Ende in 2–4 Sätzen sagen, was geändert wurde, und dass Mag. Gerlinde Pramer jetzt auf GitHub den Pull Request mit „Merge pull request" übernehmen kann. Danach ist die Änderung nach ca. 1–2 Minuten in der **Vorschau** sichtbar (GitHub Pages dieses Repos: `https://<github-name>.github.io/anahata-business-circle/`).
- **Übernehmen und live schalten nur auf ausdrückliche Anweisung.**
  - Sagt Mag. Gerlinde Pramer z. B. „Übernimm die Änderung“: den Pull Request in `main` mergen (`gh pr merge --merge`). Danach sagen, dass die Vorschau in 1–2 Minuten aktualisiert ist, und die Vorschau-Adresse nennen.
  - Sagt sie z. B. „Schalte live“: den Ablauf starten mit `gh workflow run live-schalten.yml --ref main -f testlauf=false`, ca. 1–3 Minuten warten, mit `gh run list --workflow=live-schalten.yml --limit 1` das Ergebnis prüfen und in einem Satz melden (erfolgreich oder fehlgeschlagen).
  - Nie von dir aus übernehmen oder live schalten, auch nicht „zur Sicherheit“ oder als Test. Vorher immer die Vorschau von ihr bestätigen lassen.
  - Klappt das Starten nicht (fehlende Rechte o. Ä.): erklären, dass sie es auf github.com unter „Actions“ → „Website live schalten“ → „Run workflow“ selbst starten kann.
- **Rückgängig machen:** Sagt sie „Mach die letzte Änderung rückgängig“, einen Pull Request mit `git revert` der letzten Änderung anlegen – nie Verlauf löschen oder überschreiben.
- Keine Zugangsdaten, Passwörter oder Tokens in Dateien schreiben. Dieses Repo ist öffentlich.

## Welche Dateien zählen

- **Live sind nur:** `index.html`, `impressum.html`, `datenschutz.html`, `robots.txt`, `sitemap.xml`, Ordner `img/` und `video/`.
- Veraltet, **nicht bearbeiten**: `index-*.html`, `*-V1.html`, `*-violet.html`, `img-originale-archiv/`.

## Sprache, Ton, Design

- Österreichisches Deutsch mit „ß", Besucher:innen in der **Sie-Form**, Ton warm und **bescheiden** (keine Superlative wie „exklusiv").
- Immer **„Mag. Gerlinde Pramer"** – nie ohne akademischen Titel.
- Farben: Navy `#1A3A6B`, Gold `#B89968`, Creme `#FAF7F2` (CSS-Variablen in `index.html` verwenden, keine neuen Farbwerte, **kein Lila/Violett**). Schriften: Outfit (Überschriften), Inter (Text).
- Keine Hover-Effekte auf Termin-Karten. Logo-Farbwechsel nur per `opacity` über zwei Bilder.
- Jede Änderung auch auf dem Handy prüfen (ca. 375 px): Bildausschnitte, Buttons, mobiles Menü.

## Termine (häufigste Änderung) – alle Stellen gemeinsam ändern

In `index.html` stehen Termine an mehreren Stellen, immer in der Reihenfolge Linz – Wien – Graz:
1. Save-the-Date-Boxen bzw. Termin-Karten (`date-card`) mit Datum, Uhrzeit, Location und Adresse
2. Auswahlliste im Anmeldeformular
3. Terminliste im Footer
4. Hinweistext zu weiteren Terminen (mit Link auf pramer.com/termine)
5. Strukturierte Daten: Event-Angaben in `<script type="application/ld+json">` (Datum, Ort, Adresse) und ggf. die FAQ-Antworten (sichtbar **und** im FAQ-JSON-LD)

**Außerhalb dieses Repos** – am Ende der Aufgabe ausdrücklich darauf hinweisen:
- die Termin-Tabelle auf **pramer.com/termine** (eigenes Repo `pramer-com`),
- die Bestätigungsmails in **ActiveCampaign** (Automationen „ABC Anmeldung Linz/Wien/Graz").

## Nicht ohne ausdrücklichen Auftrag ändern

- Das Anmeldeformular und das Newsletter-Formular (ActiveCampaign: versteckte Felder, Listen-Zuordnung je Stadt, JavaScript-Rückmeldungen). Texte rundherum dürfen geändert werden.
- Pflicht-Checkbox Datenschutz samt Fehlermeldung.
- Rechtliche Texte in `impressum.html` und `datenschutz.html`.
