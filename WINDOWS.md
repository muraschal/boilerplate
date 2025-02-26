# 🪟 ZVV Boilerplate Assets für Windows-Benutzer

Dieses Dokument beschreibt, wie Windows-Benutzer spezifische Assets (Schriftarten, Icons und Logos) aus dem ZVV Boilerplate Repository herunterladen können.

## 📋 Inhaltsverzeichnis

- [Voraussetzungen](#voraussetzungen)
- [Befehle für PowerShell](#befehle-für-powershell)
  - [Schriftarten herunterladen](#schriftarten-herunterladen)
  - [Icons herunterladen](#icons-herunterladen)
  - [Logos herunterladen](#logos-herunterladen)
  - [Alle Assets auf einmal herunterladen](#alle-assets-auf-einmal-herunterladen)
- [Befehle für Git Bash](#befehle-für-git-bash)
- [Sparse Checkout in PowerShell](#sparse-checkout-in-powershell-git-225)
- [Hinweise](#hinweise)

## ⚙️ Voraussetzungen

- Git für Windows installiert (https://git-scm.com/download/win)
- PowerShell oder Git Bash

## 💻 Befehle für PowerShell

### 🔤 Schriftarten herunterladen

```powershell
# Erstellen Sie ein Verzeichnis für die Schriftarten
New-Item -Path "fonts\zvv" -ItemType Directory -Force

# Klonen Sie das Repository temporär, kopieren Sie die Schriftarten und löschen Sie das Repository
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_boilerplate
Copy-Item -Path "temp_boilerplate\assets\zvv\font\*" -Destination "fonts\zvv\" -Recurse
Remove-Item -Path "temp_boilerplate" -Recurse -Force
```

### 🖼️ Icons herunterladen

```powershell
# Erstellen Sie ein Verzeichnis für die Icons
New-Item -Path "icons\zvv" -ItemType Directory -Force

# Klonen Sie das Repository temporär, kopieren Sie die Icons und löschen Sie das Repository
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_boilerplate
Copy-Item -Path "temp_boilerplate\assets\zvv\icons\*" -Destination "icons\zvv\" -Recurse
Remove-Item -Path "temp_boilerplate" -Recurse -Force
```

### 🏷️ Logos herunterladen

```powershell
# Erstellen Sie ein Verzeichnis für die Logos
New-Item -Path "logos\zvv" -ItemType Directory -Force

# Klonen Sie das Repository temporär, kopieren Sie die Logos und löschen Sie das Repository
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_boilerplate
Copy-Item -Path "temp_boilerplate\assets\zvv\logos\*" -Destination "logos\zvv\" -Recurse
Remove-Item -Path "temp_boilerplate" -Recurse -Force
```

### 📦 Alle Assets auf einmal herunterladen

```powershell
# Erstellen Sie Verzeichnisse für alle Asset-Typen
New-Item -Path "assets\zvv\font" -ItemType Directory -Force
New-Item -Path "assets\zvv\icons" -ItemType Directory -Force
New-Item -Path "assets\zvv\logos" -ItemType Directory -Force

# Klonen Sie das Repository temporär und kopieren Sie alle Assets
git clone --depth 1 https://github.com/muraschal/boilerplate.git temp_boilerplate
Copy-Item -Path "temp_boilerplate\assets\zvv\font\*" -Destination "assets\zvv\font\" -Recurse
Copy-Item -Path "temp_boilerplate\assets\zvv\icons\*" -Destination "assets\zvv\icons\" -Recurse
Copy-Item -Path "temp_boilerplate\assets\zvv\logos\*" -Destination "assets\zvv\logos\" -Recurse
Remove-Item -Path "temp_boilerplate" -Recurse -Force
```

## 🐱 Befehle für Git Bash

Wenn Sie Git Bash verwenden, können Sie die Befehle aus der [ZVV-ASSETS.md](ZVV-ASSETS.md) unverändert nutzen, da Git Bash Unix-ähnliche Befehle unterstützt.

## 🔍 Sparse Checkout in PowerShell (Git 2.25+)

Für fortgeschrittene Benutzer, die nur bestimmte Teile des Repositories herunterladen möchten:

### 🔤 Schriftarten mit Sparse Checkout

```powershell
# Erstellen Sie ein Verzeichnis für die Schriftarten
New-Item -Path "fonts\zvv" -ItemType Directory -Force

# Verwenden Sie sparse-checkout, um nur die Schriftarten zu holen
git clone --depth 1 --filter=blob:none --sparse https://github.com/muraschal/boilerplate.git temp_boilerplate
Set-Location -Path "temp_boilerplate"
git sparse-checkout set assets/zvv/font
Copy-Item -Path "assets\zvv\font\*" -Destination "..\fonts\zvv\" -Recurse
Set-Location -Path ".."
Remove-Item -Path "temp_boilerplate" -Recurse -Force
```

### 🖼️ Icons mit Sparse Checkout

```powershell
# Erstellen Sie ein Verzeichnis für die Icons
New-Item -Path "icons\zvv" -ItemType Directory -Force

# Verwenden Sie sparse-checkout, um nur die Icons zu holen
git clone --depth 1 --filter=blob:none --sparse https://github.com/muraschal/boilerplate.git temp_boilerplate
Set-Location -Path "temp_boilerplate"
git sparse-checkout set assets/zvv/icons
Copy-Item -Path "assets\zvv\icons\*" -Destination "..\icons\zvv\" -Recurse
Set-Location -Path ".."
Remove-Item -Path "temp_boilerplate" -Recurse -Force
```

### 🏷️ Logos mit Sparse Checkout

```powershell
# Erstellen Sie ein Verzeichnis für die Logos
New-Item -Path "logos\zvv" -ItemType Directory -Force

# Verwenden Sie sparse-checkout, um nur die Logos zu holen
git clone --depth 1 --filter=blob:none --sparse https://github.com/muraschal/boilerplate.git temp_boilerplate
Set-Location -Path "temp_boilerplate"
git sparse-checkout set assets/zvv/logos
Copy-Item -Path "assets\zvv\logos\*" -Destination "..\logos\zvv\" -Recurse
Set-Location -Path ".."
Remove-Item -Path "temp_boilerplate" -Recurse -Force
```

## ℹ️ Hinweise

- **Lizenz**: Die ZVV-Schriftarten sind Eigentum des ZVV und dürfen nur für autorisierte ZVV-Anwendungen verwendet werden. Für die Verwendung ist eine Lizenz erforderlich. Bitte kontaktieren Sie grafik@zvv.ch für weitere Informationen.
- Die Pfade in den Beispielen müssen möglicherweise an Ihre Projektstruktur angepasst werden.
- Wenn Sie auf Probleme mit PowerShell-Berechtigungen stoßen, starten Sie PowerShell als Administrator oder passen Sie Ihre Ausführungsrichtlinien an mit `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`. 