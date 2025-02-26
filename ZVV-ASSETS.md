# 🎨 ZVV Boilerplate Assets

Dieses Dokument beschreibt, wie Sie spezifische Assets (Schriftarten, Icons und Logos) aus dem ZVV Boilerplate Repository herunterladen können, ohne das gesamte Repository klonen zu müssen.

## 📋 Inhaltsverzeichnis

- [Voraussetzungen](#voraussetzungen)
- [Schriftarten herunterladen](#schriftarten-herunterladen)
- [Icons herunterladen](#icons-herunterladen)
- [Logos herunterladen](#logos-herunterladen)
- [Alle Assets auf einmal herunterladen](#alle-assets-auf-einmal-herunterladen)
- [Verwendung der Assets in Ihrem Projekt](#verwendung-der-assets-in-ihrem-projekt)
  - [Schriftarten einbinden](#schriftarten-einbinden)
  - [Icons verwenden](#icons-verwenden)
  - [Logos verwenden](#logos-verwenden)
- [Hinweise](#hinweise)

## ⚙️ Voraussetzungen

- Git installiert
- Bash-Terminal oder Git Bash (für Windows-Benutzer)
- curl oder wget (optional für direkte Downloads)

> **Hinweis für Windows-Benutzer**: Diese Anleitung verwendet Unix-basierte Befehle. Spezifische Anweisungen für Windows mit PowerShell-Befehlen finden Sie in der [WINDOWS.md](WINDOWS.md) Datei.

## 🔤 Schriftarten herunterladen

Um nur die ZVV-Schriftarten herunterzuladen, können Sie einen der folgenden Befehle verwenden:

### Methode 1: Temporäres Klonen und Kopieren

```bash
# Erstellen Sie ein Verzeichnis für die Schriftarten
mkdir -p fonts/zvv

# Klonen Sie das Repository temporär, kopieren Sie die Schriftarten und löschen Sie das Repository
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_boilerplate
cp -r temp_boilerplate/assets/zvv/font/* fonts/zvv/
rm -rf temp_boilerplate
```

### Methode 2: Sparse Checkout (Git 2.25+)

```bash
# Erstellen Sie ein Verzeichnis für die Schriftarten
mkdir -p fonts/zvv

# Verwenden Sie sparse-checkout, um nur die Schriftarten zu holen
git clone --depth 1 --filter=blob:none --sparse https://github.com/muraschal/boilerplate.git temp_boilerplate
cd temp_boilerplate
git sparse-checkout set assets/zvv/font
cp -r assets/zvv/font/* ../fonts/zvv/
cd ..
rm -rf temp_boilerplate
```

## 🖼️ Icons herunterladen

Um nur die ZVV-Icons herunterzuladen:

### Methode 1: Temporäres Klonen und Kopieren

```bash
# Erstellen Sie ein Verzeichnis für die Icons
mkdir -p icons/zvv

# Klonen Sie das Repository temporär, kopieren Sie die Icons und löschen Sie das Repository
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_boilerplate
cp -r temp_boilerplate/assets/zvv/icons/* icons/zvv/
rm -rf temp_boilerplate
```

### Methode 2: Sparse Checkout (Git 2.25+)

```bash
# Erstellen Sie ein Verzeichnis für die Icons
mkdir -p icons/zvv

# Verwenden Sie sparse-checkout, um nur die Icons zu holen
git clone --depth 1 --filter=blob:none --sparse https://github.com/muraschal/boilerplate.git temp_boilerplate
cd temp_boilerplate
git sparse-checkout set assets/zvv/icons
cp -r assets/zvv/icons/* ../icons/zvv/
cd ..
rm -rf temp_boilerplate
```

## 🏷️ Logos herunterladen

Um nur die ZVV-Logos herunterzuladen:

### Methode 1: Temporäres Klonen und Kopieren

```bash
# Erstellen Sie ein Verzeichnis für die Logos
mkdir -p logos/zvv

# Klonen Sie das Repository temporär, kopieren Sie die Logos und löschen Sie das Repository
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_boilerplate
cp -r temp_boilerplate/assets/zvv/logos/* logos/zvv/
rm -rf temp_boilerplate
```

### Methode 2: Sparse Checkout (Git 2.25+)

```bash
# Erstellen Sie ein Verzeichnis für die Logos
mkdir -p logos/zvv

# Verwenden Sie sparse-checkout, um nur die Logos zu holen
git clone --depth 1 --filter=blob:none --sparse https://github.com/muraschal/boilerplate.git temp_boilerplate
cd temp_boilerplate
git sparse-checkout set assets/zvv/logos
cp -r assets/zvv/logos/* ../logos/zvv/
cd ..
rm -rf temp_boilerplate
```

## 📦 Alle Assets auf einmal herunterladen

Um alle ZVV-Assets (Schriftarten, Icons und Logos) auf einmal herunterzuladen:

```bash
# Erstellen Sie Verzeichnisse für alle Asset-Typen
mkdir -p assets/zvv/font assets/zvv/icons assets/zvv/logos

# Klonen Sie das Repository temporär und kopieren Sie alle Assets
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_boilerplate
cp -r temp_boilerplate/assets/zvv/font/* assets/zvv/font/
cp -r temp_boilerplate/assets/zvv/icons/* assets/zvv/icons/
cp -r temp_boilerplate/assets/zvv/logos/* assets/zvv/logos/
rm -rf temp_boilerplate
```

## 🛠️ Verwendung der Assets in Ihrem Projekt

### Schriftarten einbinden

Die ZVV-Schriftarten umfassen zwei Hauptfamilien:
- **ZVV Brown Narrow S Web** - Die schmale Variante, optimiert für Benutzeroberflächen
- **ZVV Brown Narrow Web** - Die Standardvariante

Für die einfachste Einbindung können Sie die mitgelieferte CSS-Datei verwenden:

```html
<link rel="stylesheet" href="fonts/zvv/stylesheet.css">
```

Alternativ können Sie die Schriftarten manuell in Ihrem CSS einbinden:

```css
@font-face {
  font-family: 'ZVV Brown Narrow S Web';
  src: url('fonts/zvv/ZVVBrownNarrowSWeb-Regular.woff2') format('woff2'),
       url('fonts/zvv/ZVVBrownNarrowSWeb-Regular.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'ZVV Brown Narrow S Web';
  src: url('fonts/zvv/ZVVBrownNarrowSWeb-Bold.woff2') format('woff2'),
       url('fonts/zvv/ZVVBrownNarrowSWeb-Bold.woff') format('woff');
  font-weight: bold;
  font-style: normal;
}

/* Weitere Schriftschnitte nach Bedarf */
```

Für optimale Ladezeiten sollten Sie die wichtigsten Schriftschnitte vorladen:

```html
<link rel="preload" href="fonts/zvv/ZVVBrownNarrowSWeb-Regular.woff2" as="font" type="font/woff2" crossorigin>
<link rel="preload" href="fonts/zvv/ZVVBrownNarrowSWeb-Bold.woff2" as="font" type="font/woff2" crossorigin>
```

Verwendung in CSS:

```css
body {
    font-family: 'ZVV Brown Narrow S Web', Arial, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}

h1, h2, h3 {
    font-weight: bold;
}
```

### Icons verwenden

Die SVG-Icons können direkt in HTML eingebunden oder als Hintergrundbilder in CSS verwendet werden:

```html
<!-- Direkt im HTML -->
<img src="icons/zvv/suchen.svg" alt="Suchen Icon">

<!-- Oder als Inline SVG für bessere Kontrolle -->
<svg>
  <use xlink:href="icons/zvv/suchen.svg#icon"></use>
</svg>
```

### Logos verwenden

```html
<img src="logos/zvv/ZVV-logo-rgb-pos.png" alt="ZVV Logo">
```

## ℹ️ Hinweise

- **Lizenz**: Die ZVV-Schriftarten sind Eigentum des ZVV und dürfen nur für autorisierte ZVV-Anwendungen verwendet werden. Für die Verwendung ist eine Lizenz erforderlich. Bitte kontaktieren Sie grafik@zvv.ch für weitere Informationen.
- Die Pfade in den Beispielen müssen möglicherweise an Ihre Projektstruktur angepasst werden.
- Für Windows-Benutzer: Verwenden Sie Git Bash oder passen Sie die Befehle entsprechend an. 