# ZVV Design Template

Ein spezialisiertes Design-System für ZVV-Anwendungen, basierend auf den offiziellen ZVV-Assets und optimiert für Mobilitäts-Apps.

## Inhaltsverzeichnis
- [Farbpalette](#farbpalette)
- [Typografie](#typografie)
- [Abstände](#abstände)
- [UI-Elemente](#ui-elemente)
- [Spezifische Komponenten](#spezifische-komponenten)
- [Responsive Design](#responsive-design)
- [Barrierefreiheit](#barrierefreiheit)
- [Schrifteinbindung](#schrifteinbindung)
- [Komponenten-Beispiele](#komponenten-beispiele)
- [Best Practices](#best-practices)

## Farbpalette

### Primärfarben
- **ZVV-Rot**: `#E7000E` (S12, Logo)
- **ZVV-Blau**: `#0085CC` (S30, Logo)
- **ZVV-Grün**: `#009E3C` (S9, Logo)
- **ZVV-Grau**: `#868889` (Logo)
- **Schwarz**: `#000000` (Text)

### S-Bahn-Linienfarben
| Linie | Farbe    | HEX-Code  | Linie | Farbe    | HEX-Code  |
|-------|----------|-----------|-------|----------|-----------|
| S2    | Grün     | `#79B819` | S19   | Orange   | `#F17900` |
| S3    | Blau     | `#008ED1` | S20   | Pink     | `#EA4C8A` |
| S4    | Lachs    | `#F17E5D` | S21   | Hellblau | `#9EC8EA` |
| S5    | Türkis   | `#52B3C9` | S23   | Hellgrün | `#97C64F` |
| S6    | Lila     | `#764493` | S24   | Braun    | `#B48957` |
| S7    | Gelb     | `#FCBB00` | S25   | Magenta  | `#B3007F` |
| S8    | Violett  | `#581F82` | S26   | Petrol   | `#008AAD` |
| S9    | Grün     | `#009E3C` | S29   | Grün     | `#05A74B` |
| S10   | Goldgelb | `#FDC73B` | S30   | Blau     | `#0085CC` |
| S12   | Rot      | `#E7000E` | S33   | Blau     | `#38A3DA` |
| S14   | Braun    | `#7D4900` | S35   | Hellblau | `#83BCE5` |
| S15   | Beige    | `#CEAD87` | S36   | Rosa     | `#CE7DB1` |
| S16   | Grün     | `#6ABA72` | S40   | Flieder  | `#B39DC8` |
| S17   | Türkis   | `#009DBC` |       |          |           |
| S18   | Rot      | `#EB4B30` |       |          |           |

### UI-Farben
- **Hintergrund**: `#F5F5F5` (Hellgrau)
- **Karten**: `#FFFFFF` (Weiß)
- **Fehler**: `#E7000E` (ZVV-Rot)
- **Erfolg**: `#009E3C` (ZVV-Grün)
- **Warnung**: `#FCBB00` (S7-Gelb)
- **Information**: `#0085CC` (ZVV-Blau)

## Typografie

### Schriftarten
- **Primäre Schrift**: "ZVV Brown Narrow S Web", sans-serif
- **Fallback**: Arial, sans-serif

### Schriftschnitte und -größen

| Element          | Schriftschnitt                   | Größe        | Zeilenabstand |
|------------------|----------------------------------|--------------|---------------|
| Überschrift 1    | ZVV Brown Narrow S Web Bold     | 2rem (32px)  | 1.2           |
| Überschrift 2    | ZVV Brown Narrow S Web Bold     | 1.5rem (24px)| 1.2           |
| Überschrift 3    | ZVV Brown Narrow S Web Bold     | 1.25rem (20px)| 1.2          |
| Fließtext        | ZVV Brown Narrow S Web Regular  | 1rem (16px)  | 1.5           |
| Klein            | ZVV Brown Narrow S Web Regular  | 0.875rem (14px)| 1.5         |
| Sehr klein       | ZVV Brown Narrow S Web Regular  | 0.75rem (12px)| 1.5          |
| Hervorhebung     | ZVV Brown Narrow S Web Bold     | -            | -             |

## Abstände

- **Basis-Einheit**: 0.25rem (4px)
- **Standard-Abstand**: 1rem (16px)
- **Abschnitt-Abstand**: 2rem (32px)
- **Komponenten-Abstand**: 1.5rem (24px)
- **Icon-Abstand**: 0.5rem (8px)

## UI-Elemente

### Buttons
| Typ        | Hintergrund       | Text        | Rahmen       | Radius |
|------------|-------------------|-------------|--------------|--------|
| Primär     | ZVV-Rot (#E7000E) | Weiß        | Keiner       | 4px    |
| Sekundär   | Weiß              | ZVV-Blau    | ZVV-Blau 1px | 4px    |
| Tertiär    | Transparent       | ZVV-Blau    | Keiner       | 4px    |
| Deaktiviert| ZVV-Grau (#868889)| Weiß        | Keiner       | 4px    |

### Formulare
- **Eingabefelder**: Weißer Hintergrund, 1px Rahmen, 4px Radius
- **Labels**: Über dem Eingabefeld, Schwarz
- **Fokus-Zustand**: ZVV-Blau für Rahmen, leichter Schatten
- **Fehler-Zustand**: ZVV-Rot für Rahmen und Fehlermeldung

### Karten und Container
- **Hintergrund**: Weiß
- **Schatten**: 0 2px 4px rgba(0, 0, 0, 0.1)
- **Rahmen**: Kein Rahmen oder 1px
- **Ecken**: 8px Radius

## Spezifische Komponenten

### Linien-Anzeige
- **S-Bahn**: Kreisförmiges Badge mit Linienfarbe und weißer Schrift
- **Bus**: Rechteckiges Badge mit Busblau (`#82BFE7`) und weißer Schrift
- **Tram**: Rechteckiges Badge mit entsprechender VBZ-Farbe und weißer Schrift

### Fahrplan-Anzeige
- **Zeit**: Bold, größere Schrift
- **Verspätung**: ZVV-Rot, kursiv
- **Gleis/Haltestelle**: Regular, kleinere Schrift

### Ticket-Anzeige
- **Gültigkeitsdauer**: Bold hervorgehoben
- **QR-Code**: Zentral platziert
- **Ticket-Typ**: Oben, mit Icon
- **Zonen**: Visuell hervorgehoben mit ZVV-Blau

## Responsive Design

| Breakpoint | Breite      | Layout                                |
|------------|-------------|---------------------------------------|
| Mobil      | < 768px     | Volle Breite, vertikale Stapelung    |
| Tablet     | 768-1024px  | Zwei-Spalten-Layout für bestimmte Ansichten |
| Desktop    | > 1024px    | Mehrspaltiges Layout, fixierte Seitenleiste |

## Barrierefreiheit
- **Kontrast**: WCAG AA-Standard für alle Text-Hintergrund-Kombinationen
- **Fokus-Indikatoren**: Deutlich sichtbar für Tastaturnavigation
- **Alternative Texte**: Für alle Icons und funktionalen Bilder
- **Schriftgrößen**: Skalierbar für Benutzer mit Sehbehinderungen

## Schrifteinbindung

### Web-Einbindung
```css
@font-face {
    font-family: 'ZVV Brown Narrow S Web';
    src: url('/fonts/ZVVBrownNarrowSWeb-Regular.woff2') format('woff2'),
         url('/fonts/ZVVBrownNarrowSWeb-Regular.woff') format('woff');
    font-weight: normal;
    font-style: normal;
    font-display: swap;
}

@font-face {
    font-family: 'ZVV Brown Narrow S Web';
    src: url('/fonts/ZVVBrownNarrowSWeb-Bold.woff2') format('woff2'),
         url('/fonts/ZVVBrownNarrowSWeb-Bold.woff') format('woff');
    font-weight: bold;
    font-style: normal;
    font-display: swap;
}

body {
    font-family: 'ZVV Brown Narrow S Web', Arial, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}
```

### Performance-Optimierung
```html
<link rel="preload" href="/fonts/ZVVBrownNarrowSWeb-Regular.woff2" as="font" type="font/woff2" crossorigin>
```

### Hinweise
- Schriftdateien im `/fonts`-Verzeichnis ablegen
- Lizenzierung über ZVV erforderlich (kontaktiere grafik@zvv.ch)
- WOFF2 für bessere Kompression bevorzugen
- `font-display: swap` gegen FOIT einsetzen

## Komponenten-Beispiele

### Header mit Zurück-Button
```html
<header class="zvv-header">
  <button class="zvv-back-button">
    <img src="/icons/back.svg" alt="Zurück">
  </button>
  <h1 class="zvv-title">Fahrplan</h1>
</header>
```

### Verbindungsanzeige
```html
<div class="zvv-connection">
  <div class="zvv-connection-time">14:42</div>
  <div class="zvv-connection-details">
    <div class="zvv-line-container">
      <span class="zvv-line zvv-line-s12">S12</span>
      <span class="zvv-destination">Flughafen Zürich</span>
    </div>
    <div class="zvv-platform">Gleis 41/42</div>
  </div>
</div>
```

### Ticket-Karte
```html
<div class="zvv-ticket-card">
  <div class="zvv-ticket-header">
    <img src="/icons/ticket.svg" alt="Ticket" class="zvv-ticket-icon">
    <h3 class="zvv-ticket-title">Einzelbillett</h3>
  </div>
  <div class="zvv-ticket-body">
    <p class="zvv-ticket-validity">Gültig bis: 15.06.2023, 23:59 Uhr</p>
    <p class="zvv-ticket-zones">Zonen: 110, 121</p>
    <div class="zvv-ticket-qr">
      <!-- QR-Code hier einfügen -->
    </div>
  </div>
</div>
```

### Tab-Navigation
```html
<nav class="zvv-tab-bar">
  <a href="#" class="zvv-tab">
    <img src="/icons/map.svg" alt="" class="zvv-tab-icon">
    <span class="zvv-tab-label">In der Nähe</span>
  </a>
  <a href="#" class="zvv-tab zvv-tab-active">
    <img src="/icons/timetable.svg" alt="" class="zvv-tab-icon">
    <span class="zvv-tab-label">Fahrplan</span>
  </a>
  <a href="#" class="zvv-tab">
    <img src="/icons/ticket.svg" alt="" class="zvv-tab-icon">
    <span class="zvv-tab-label">Tickets</span>
  </a>
  <a href="#" class="zvv-tab">
    <img src="/icons/more.svg" alt="" class="zvv-tab-icon">
    <span class="zvv-tab-label">Mehr</span>
  </a>
</nav>
```

## Best Practices

### Farbverwendung
- Linienfarben nur für die entsprechenden Verkehrslinien verwenden
- ZVV-Rot für primäre Aktionen und wichtige Hinweise reservieren
- ZVV-Blau für sekundäre Elemente und Informationen nutzen
- Ausreichende Farbkontraste für Barrierefreiheit sicherstellen

### Typografie
- Konsistente Schriftgrößen innerhalb der definierten Hierarchie verwenden
- Textausrichtung: Links für Fließtext, zentriert für kurze Überschriften
- Zeilenabstände für optimale Lesbarkeit anpassen
- Nicht mehr als drei Schriftgrößen pro Ansicht verwenden

### Icons
- Einheitliche Größen verwenden (24×24px Standard)
- Konsistenten Stil für alle Icons beibehalten
- Alternative Texte für Barrierefreiheit bereitstellen
- SVG-Format für optimale Skalierbarkeit verwenden

### Performance
- Schriftarten mit `font-display: swap` laden
- Kritische CSS inline einbinden
- Bilder und Icons optimieren
- Lazy Loading für nicht-kritische Inhalte implementieren

