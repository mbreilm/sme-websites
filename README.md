# SME Websites – Munich & Traunstein

Ein einzelnes GitHub-Repository mit 20 standalone Handwerker- und Dienstleister-Websites.
Jede Website ist in einem eigenen Unterordner und vollständig unabhängig.

## 📁 Struktur

```
sme-websites-repo/
├── index.html                    # Übersichts- / Landingpage
├── ar-baumontagen/
│   └── index.html                # AR Baumontagen UG
├── jast-handwerk/
│   └── index.html                # JAST Handwerk
├── maler-graf/
│   └── index.html                # Maler Graf
├── ... (20 Unterordner total)
└── README.md
```

## 🚀 Deployment auf Netlify

### Option A: Einzelne Sites (empfohlen – separate URLs pro Kunde)

1. **Gehe zu [netlify.com](https://www.netlify.com/)** und logge dich ein (oder registriere dich kostenlos).
2. Klicke auf **"Add new site"** → **"Import an existing project"**.
3. Wähle dein **GitHub-Repository** (`sme-websites-repo`).
4. Für jede Website wiederhole Schritt 2–3 und setze:
   - **Base directory:** `ar-baumontagen` (oder entsprechender Unterordner)
   - **Build command:** *(leer lassen – keine Build notwendig)*
   - **Publish directory:** *(leer lassen – index.html liegt im Root des Unterordners)*
5. Netlify gibt dir eine URL wie `https://ar-baumontagen-xyz.netlify.app`.
6. Wiederhole für alle 20 Unterordner. Jeder Kunde bekommt seine eigene URL.

> 💡 **Pro-Tipp:** Verwende Netlify's **"Site name"**-Feature, um sprechende URLs zu vergeben (z. B. `ar-baumontagen-demo.netlify.app`).

### Option B: Alles unter einer Domain (Unterordner-URLs)

Wenn du alle 20 Sites unter einer Domain haben möchtest (z. B. `deine-domain.de/ar-baumontagen/`), kannst du einfach alles auf einmal deployen:

1. Gehe zu [netlify.com](https://www.netlify.com/) → **"Add new site"** → **"Deploy manually"**.
2. Ziehe den gesamten `sme-websites-repo`-Ordner per Drag & Drop hoch.
3. Ergebnis:
   - `https://deine-site.netlify.app/` → Landingpage mit Übersicht
   - `https://deine-site.netlify.app/ar-baumontagen/` → AR Baumontagen
   - `https://deine-site.netlify.app/jast-handwerk/` → JAST Handwerk
   - usw.

### Option C: Netlify CLI (für schnelle Updates)

```bash
# Installiere Netlify CLI
npm install -g netlify-cli

# Einzelne Site deployen (aus dem Unterordner heraus)
cd ar-baumontagen
netlify deploy --prod --dir=.

# Oder: Alles auf einmal deployen (aus dem Repo-Root)
cd ..
netlify deploy --prod --dir=.
```

## 🔄 Updates vornehmen

1. Ändere die gewünschte `index.html` im entsprechenden Unterordner.
2. Pushe die Änderung auf GitHub (falls mit GitHub verbunden).
3. Netlify deployed automatisch neu – keine manuelle Arbeit nötig.

## 📝 Technische Details

- **Typ:** Statische HTML-Websites (kein Build erforderlich)
- **CSS-Framework:** Tailwind CSS via CDN
- **Logos:** Inline-SVGs (keine externen Bilddateien)
- **Kein Backend:** Reines Frontend, jede Site ist vollständig unabhängig
- **SEO-ready:** Meta-Tags, Open-Graph, responsive Design

## 🛠️ Neue Website hinzufügen

1. Erstelle einen neuen Unterordner im Repo-Root: `mkdir neue-website`
2. Lege eine `index.html` in den Ordner ab.
3. Commit & Push → Netlify deployed automatisch (falls GitHub-verknüpft).

---

**Fragen oder Probleme?** Netlify's Free-Tier reicht vollkommen für diese 20 Sites aus (100 GB Bandbreite/Monat, unbegrenzte Sites).
