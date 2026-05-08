# Anahata Business Circle – Landingpage

Single-file Landingpage für die Bewerbung der Business-Circle-Abende im Juni 2026 in Wien, Linz und Graz.

```
anahata-business-circle/
├── index.html             ← die komplette Seite (HTML + CSS + JS inline)
├── README.md              ← dieses Dokument
└── img/
    ├── hero-{480,800,1600}w.jpg              Foto: Halbporträt cremefarbener Blazer
    ├── gerlinde-portrait-{480,800,1600}w.jpg Foto: am Tisch sitzend
    └── gerlinde-energie-{480,800,1600}w.jpg  Foto: lebendiges Lachen, blauer Blazer
```

## Vor dem Live-Schalten zu erledigen

Suche und ersetze in `index.html` folgende Platzhalter:

### 1. ActiveCampaign – Anmeldeformular

| Platzhalter | Was eintragen | Wo finden |
|---|---|---|
| `REPLACE_WITH_ACTIVECAMPAIGN_FORM_ACTION_URL` | Action-URL des Anmelde-Formulars | AC → Site → Forms → Embed-Code (Inline-Form) |
| `REPLACE_WITH_AC_ACCOUNT_ID` | Numerische Account-ID | gleicher Embed-Code, Hidden-Field `u` |
| `REPLACE_WITH_AC_FORM_ID` | Form-ID | Embed-Code, Hidden-Field `f` |
| `field[TERMIN_FIELD_ID]` | Custom-Field-ID für „Termin" | Custom Field anlegen → ID aus Embed übernehmen |
| `field[UNTERNEHMEN_FIELD_ID]` | Custom-Field-ID für „Unternehmen" | dito |
| `field[UID_FIELD_ID]` | Custom-Field-ID für „UID" | dito |
| `field[JAHRGANG_FIELD_ID]` | Custom-Field-ID für „Jahrgang" | dito |
| `field[NEWSLETTER_FIELD_ID]` | Custom-Field-ID für „Newsletter-Opt-In" | dito |

### 2. ActiveCampaign – Newsletter-Formular

Eigenes Formular in AC anlegen (eigene Liste / eigenes Tag, damit Newsletter-Anmeldungen klar von Event-Anmeldungen getrennt bleiben). Dann ersetzen:

| Platzhalter | Was eintragen |
|---|---|
| `REPLACE_WITH_ACTIVECAMPAIGN_NEWSLETTER_FORM_ACTION_URL` | Action-URL des Newsletter-Formulars |
| `REPLACE_WITH_AC_NEWSLETTER_FORM_ID` | Form-ID des Newsletter-Formulars |

### 3. Inhaltliche To-Dos

Im HTML markiert mit `TODO` oder als Platzhalter-Text:

- **Locations Wien / Linz / Graz** – sobald fix, in den drei Date-Cards (`<section id="anmeldung">`) einsetzen. Aktueller Text: „Location wird kurzfristig bekanntgegeben".
- **Logo „Gerlinde Pramer Management"** – `img/logo-gpm.svg` (oder `.png`) ablegen, dann den auskommentierten `<img>` im Footer aktivieren (`<!-- TODO: Logo einfügen -->`).
- **Mail-Adresse** im Footer prüfen: aktuell `office@gerlindepramer.at` als Platzhalter.
- **Datenschutz- und Impressum-Seite** verlinken (`#datenschutz`, `#impressum` durch echte URLs ersetzen).

## Foto-Auswahl & Fallback

Verwendet werden drei Aufnahmen aus dem Daniela-Köppl-Shooting (Februar 2026). Die Originale liegen im Eltern-Ordner unter `Gerlinde Pramer Fotoshooting Dani_Feb26/`. Falls Gerlinde andere Bilder bevorzugt: einfach in `img/` mit gleichen Dateinamen austauschen oder im HTML die Dateinamen anpassen. Empfohlene Maße: min. 1600px Breite, 4:3 oder 3:2 Querformat.

## Designsystem (zur Referenz)

| Token | Wert | Bedeutung |
|---|---|---|
| `--cream` | `#FAF7F2` | Bühne / Background |
| `--cream-deep` | `#F2EDE3` | abgesetzter Sektion-Background |
| `--ink` | `#1A2332` | Headline-Farbe / Primary Button |
| `--ink-soft` | `#3F4A5C` | Body-Text |
| `--blue` | `#6B89A6` | Akzent (Bluse) |
| `--blue-deep` | `#2B5A8C` | Hauptakzent (Blazer) |
| `--gold` | `#B89968` | Münze / Akzentlinien |
| Schriften | Outfit (Headlines) + Inter (Body) | beide via Google Fonts |
| Body-Größe | 18 px | Mindestlesbarkeit für 40+ |
| Min Touch Target | 48 px | Buttons / Inputs |

## Hosting

Reines statisches HTML. Funktioniert auf jedem Webhoster, auf Netlify, Vercel, GitHub Pages, oder als Subdomain bei Gerlindes bestehender Hosting-Lösung. Keine Build-Schritte, keine Datenbank, keine Server-Logik. Einfach den ganzen Ordner hochladen.

## Bekannte Lücken / Ideen für später

- **Logo Anahata Business Circle** – derzeit eine SVG-Münze als Markenzeichen (CSS, im Topbar). Sobald ein eigenes Logo gestaltet ist, in `.brand__mark` ersetzen.
- **Strukturierte Daten** – `Event`-Schema (schema.org) ergänzen, sobald Locations final sind. Verbessert Suchmaschinen-Snippets.
- **Tracking** – AC trackt selbst. Falls zusätzlich Plausible/Matomo/GA gewünscht: Snippet vor `</head>` einfügen.
- **A/B-Variante des Hero** – falls die Conversion auf der Wien-Karte hoch und auf Graz/Linz niedrig ist, könnte man später pro Stadt eine eigene Subseite ableiten.
