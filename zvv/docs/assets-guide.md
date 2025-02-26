# 🎨 ZVV Assets Guide

Diese Anleitung beschreibt, wie Sie die offiziellen ZVV-Assets (Schriftarten, Icons und Logos) herunterladen und in Ihren Projekten verwenden können.

## 📋 Inhaltsverzeichnis

- [Voraussetzungen](#voraussetzungen)
- [Assets herunterladen](#assets-herunterladen)
  - [Für Unix/Linux/macOS](#für-unixlinuxmacos)
  - [Für Windows](#für-windows)
- [Verwendung der Assets](#verwendung-der-assets)
  - [Schriftarten einbinden](#schriftarten-einbinden)
  - [Icons verwenden](#icons-verwenden)
  - [Logos verwenden](#logos-verwenden)
- [Hinweise und Best Practices](#hinweise-und-best-practices)

## ⚙️ Voraussetzungen

- Git installiert
- Kommandozeilen-Terminal:
  - Bash/Terminal (Unix, Linux, macOS)
  - PowerShell oder Git Bash (Windows)

## 📥 Assets herunterladen

### Für Unix/Linux/macOS

#### Schriftarten (nur ZVV Brown Narrow)

```bash
# Verzeichnis erstellen
mkdir -p fonts/zvv

# Repository klonen und nur benötigte Schriftarten kopieren
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_repo
cp temp_repo/zvv/assets/fonts/ZVVBrownNarrow-Regular.woff fonts/zvv/
cp temp_repo/zvv/assets/fonts/ZVVBrownNarrow-Regular.woff2 fonts/zvv/
cp temp_repo/zvv/assets/fonts/ZVVBrownNarrow-Bold.woff fonts/zvv/
cp temp_repo/zvv/assets/fonts/ZVVBrownNarrow-Bold.woff2 fonts/zvv/
rm -rf temp_repo
```

#### Icons

```bash
# Verzeichnis erstellen
mkdir -p icons/zvv

# Repository klonen und Icons kopieren
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_repo
cp -r temp_repo/zvv/assets/icons/* icons/zvv/
rm -rf temp_repo
```

#### Logos

```bash
# Verzeichnis erstellen
mkdir -p logos/zvv

# Repository klonen und Logos kopieren
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_repo
cp -r temp_repo/zvv/assets/logos/* logos/zvv/
rm -rf temp_repo
```

### Für Windows

#### Schriftarten (nur ZVV Brown Narrow)

```powershell
# Verzeichnis erstellen
New-Item -Path "fonts\zvv" -ItemType Directory -Force

# Repository klonen und nur benötigte Schriftarten kopieren
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_repo
Copy-Item "temp_repo\zvv\assets\fonts\ZVVBrownNarrow-Regular.woff" -Destination "fonts\zvv\"
Copy-Item "temp_repo\zvv\assets\fonts\ZVVBrownNarrow-Regular.woff2" -Destination "fonts\zvv\"
Copy-Item "temp_repo\zvv\assets\fonts\ZVVBrownNarrow-Bold.woff" -Destination "fonts\zvv\"
Copy-Item "temp_repo\zvv\assets\fonts\ZVVBrownNarrow-Bold.woff2" -Destination "fonts\zvv\"
Remove-Item -Recurse -Force temp_repo
```

#### Icons

```powershell
# Verzeichnis erstellen
New-Item -Path "icons\zvv" -ItemType Directory -Force

# Repository klonen und Icons kopieren
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_repo
Copy-Item "temp_repo\zvv\assets\icons\*" -Destination "icons\zvv\" -Recurse
Remove-Item -Recurse -Force temp_repo
```

#### Logos

```powershell
# Verzeichnis erstellen
New-Item -Path "logos\zvv" -ItemType Directory -Force

# Repository klonen und Logos kopieren
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_repo
Copy-Item "temp_repo\zvv\assets\logos\*" -Destination "logos\zvv\" -Recurse
Remove-Item -Recurse -Force temp_repo
```

## 🛠️ Verwendung der Assets

### Schriftarten einbinden

Die ZVV-Schriftart umfasst:
- **ZVV Brown Narrow** - Die offizielle Schriftart des ZVV in den Varianten Regular und Bold

Erstellen Sie eine CSS-Datei für die Schriftarten:

```css
@font-face {
  font-family: 'ZVV Brown Narrow';
  src: url('fonts/zvv/ZVVBrownNarrow-Regular.woff2') format('woff2'),
       url('fonts/zvv/ZVVBrownNarrow-Regular.woff') format('woff');
  font-weight: normal;
  font-style: normal;
  font-display: swap;
}

@font-face {
  font-family: 'ZVV Brown Narrow';
  src: url('fonts/zvv/ZVVBrownNarrow-Bold.woff2') format('woff2'),
       url('fonts/zvv/ZVVBrownNarrow-Bold.woff') format('woff');
  font-weight: bold;
  font-style: normal;
  font-display: swap;
}
```

Für optimale Ladezeiten sollten Sie die Schriftschnitte vorladen:

```html
<link rel="preload" href="fonts/zvv/ZVVBrownNarrow-Regular.woff2" as="font" type="font/woff2" crossorigin>
<link rel="preload" href="fonts/zvv/ZVVBrownNarrow-Bold.woff2" as="font" type="font/woff2" crossorigin>
```

Verwendung in CSS:

```css
body {
    font-family: 'ZVV Brown Narrow', Arial, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
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

## ℹ️ Hinweise und Best Practices

- **Wichtig**: Verwenden Sie ausschließlich die "ZVV Brown Narrow" Schriftart in den Varianten Regular und Bold. Andere Schriftarten sind für ZVV-Projekte nicht relevant.
- **Lizenz**: Die ZVV-Assets sind Eigentum des ZVV und dürfen nur für autorisierte ZVV-Anwendungen verwendet werden. Für die Verwendung ist eine Lizenz erforderlich. Bitte kontaktieren Sie grafik@zvv.ch für weitere Informationen.
- **Pfade anpassen**: Die Pfade in den Beispielen müssen möglicherweise an Ihre Projektstruktur angepasst werden.
- **Performance-Optimierung**:
  - Verwenden Sie WOFF2 für moderne Browser
  - Setzen Sie `font-display: swap` ein, um FOIT (Flash of Invisible Text) zu vermeiden
  - Laden Sie nur die tatsächlich benötigten Schriftschnitte
- **Barrierefreiheit**:
  - Stellen Sie sicher, dass Icons aussagekräftige alt-Texte haben
  - Verwenden Sie ausreichende Kontraste für Text auf farbigen Hintergründen 