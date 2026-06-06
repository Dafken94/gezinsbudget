# 🌷 Gezinsbudget

Een persoonlijke budgettracker PWA (Progressive Web App) voor David & Lauren — volledig offline bruikbaar, geen server vereist.

## Functies

- **4 rekeningen** — Overzicht, David, Lauren, Gemeenschappelijk
- **Vast / Variabel** — Markeer elke post als vast of variabel; keuze wordt onthouden voor volgende maanden
- **Terugkerende kosten** — Kopieer vaste posten van de vorige maand met één knop
- **Maand vergrendelen** — Sluit een afgelopen maand af zodat data niet per ongeluk gewijzigd wordt
- **Jaarverzicht** — Tabel met alle 12 maanden: inkomsten, uitgaven, gespaard en saldo
- **Notitieveld** — Voeg een notitie toe per maand (zichtbaar in het jaarverzicht)
- **Gedetailleerd rapport** — Uitsplitsing per persoon met vast/variabel percentage
- **Uitgaven ranking** — Uitgaven gesorteerd van hoog naar laag
- **CSV export** — Download het volledige jaar als spreadsheet
- **Spaardoelen** — Volg voortgang naar financiële doelen
- **Abonnementen** — Gedeelde lijst voor alle rekeningen
- **Gedeelde sessie** — Deel de app via een link zodat beide partners dezelfde data zien
- **Dark mode** — Donker thema voor 's avonds
- **Offline** — Werkt volledig zonder internetverbinding na eerste bezoek (PWA)

## Installatie

### Lokaal draaien

Geen server vereist — open gewoon `index.html` in een browser.

Voor de PWA-functies (offline, installeren op beginscherm) heb je een lokale server nodig:

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .
```

Open vervolgens `http://localhost:8080` in je browser.

### GitHub Pages (aanbevolen)

1. Fork of push deze repository naar GitHub
2. Ga naar **Settings → Pages**
3. Stel **Source** in op `main` branch, map `/` (root)
4. De app is beschikbaar op `https://<gebruikersnaam>.github.io/<repo-naam>/`

Op iOS: open de link in Safari → **Deel → Zet op beginscherm** voor de volledige app-ervaring.

## Bestandsstructuur

```
gezinsbudget/
├── index.html       # De volledige app (één bestand)
├── manifest.json    # PWA manifest
├── sw.js            # Service worker (offline ondersteuning)
├── icons/
│   ├── icon-152.png
│   ├── icon-167.png
│   ├── icon-180.png
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

## Data & privacy

Alle data wordt **lokaal opgeslagen** in de browser (`localStorage`). Er wordt niets naar een server gestuurd. Via de deelknop kan een sessie-ID gedeeld worden zodat twee browsers dezelfde data synchroniseren via `BroadcastChannel` — dit werkt alleen op hetzelfde apparaat/netwerk.

## Technologie

- Vanilla HTML/CSS/JavaScript — geen framework, geen build-stap
- PWA met service worker voor offline gebruik
- `localStorage` voor data-opslag
