# SME Websites – Munich & Traunstein

Ein einzelnes GitHub-Repository mit 22 standalone Handwerker- und Dienstleister-Websites.
Jede Website ist in einem eigenen Unterordner und vollständig unabhängig.

## 📁 Struktur (22 Sites)

```
sme-websites-repo/
├── index.html                         # Übersichts- / Landingpage
├── ar-baumontagen/                    # AR Baumontagen UG
├── jast-handwerk/                     # JAST Handwerk
├── maler-graf/                        # Maler Graf
├── gutes-handwerk-joerk/              # Gutes Handwerk Jörk
├── handwerk-design/                   # Handwerk Design
├── herrlinger-dienstleistungen/       # Herrlinger Dienstleistungen
├── bixheku-erjal/                     # Bixheku Erjal
├── elektro-fritz/                     # Elektro Fritz
├── mhb-panitz/                        # MHB Panitz
├── nageldesign-christina/             # Nageldesign Christina
├── friseur-haarmonie/                 # Friseur Haarmonie (Classic)
├── friseur-haarmonie-gold/            # Friseur Haarmonie – Gold Design
├── friseur-haarmonie-gruen/           # Friseur Haarmonie – Grün Design
├── fuermann-waltraud/                 # Führmann Waltraud
├── erber-sanitaer/                    # Erber Sanitär
├── elektro-ortner/                    # Elektro Ortner
├── star-doener-pizza/                 # Star Döner & Pizza
├── mitterbichler-kraemer/             # Mitterbichler Krämer
├── bandtlow-physiotherapie/           # Bandtlow Physiotherapie
├── golden-star-restaurant/            # Golden Star Restaurant
├── sander-peter-friseur/              # Sander Peter Friseur
├── elektro-rueckert/                  # Elektro Rückert
└── README.md
```

## 🚀 Deployment auf Netlify

### Option A: Einzelne Sites (empfohlen – separate URLs pro Kunde)

1. **Gehe zu [netlify.com](https://www.netlify.com/)** und logge dich ein.
2. Klicke auf **"Add new site"** → **"Import an existing project"**.
3. Wähle dein **GitHub-Repository** (`sme-websites-repo`).
4. Für jede Website wiederhole Schritt 2–3 und setze:
   - **Base directory:** `ar-baumontagen` (entsprechender Unterordner)
   - **Build command:** *(leer lassen)*
   - **Publish directory:** *(leer lassen)*
5. Netlify gibt dir eine URL wie `https://ar-baumontagen-xyz.netlify.app`.
6. Wiederhole für alle 22 Unterordner.

### Option B: Alles unter einer Domain (Unterordner-URLs)

- Netlify → **"Deploy manually"** → ziehe den gesamten Ordner per Drag & Drop hoch.
- Ergebnis: `yoursite.netlify.app/ar-baumontagen/`, `yoursite.netlify.app/friseur-haarmonie-gold/`, etc.

### Option C: Netlify CLI

```bash
npm install -g netlify-cli
cd friseur-haarmonie-gold
netlify deploy --prod --dir=.
```

## 🔄 Updates

Ändere eine `index.html` → `git push` → Netlify deployed automatisch neu.

## 📝 Technische Details

- **Typ:** Statische HTML-Websites (kein Build erforderlich)
- **CSS-Framework:** Tailwind CSS via CDN
- **Bilder:** Inline base64 (keine externen Dateien nötig)
- **Kein Backend:** Reines Frontend, jede Site ist unabhängig
