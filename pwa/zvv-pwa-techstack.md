# ZVV-Kontrollapp Techstack-Referenz

## Übersicht

Diese Referenz definiert den bewährten Techstack der ZVV-Kontrollapp als Vorlage für zukünftige Projekte. Der Stack bietet eine optimale Balance zwischen Entwicklungsgeschwindigkeit, Wartbarkeit und Benutzererfahrung für Progressive Web Apps.

---

## Frontend

### Kernkomponenten
- **JavaScript**: Vanilla JS ohne Framework
  - Direkte DOM-Manipulation
  - Fetch API für Netzwerkanfragen
  - Event-basierte Programmierung
- **CSS**: 
  - CSS-Variablen für konsistentes Theming
  - Responsive Design mit Flexbox/Grid
  - Medienspezifische Anpassungen
- **HTML5**: 
  - Semantische Elemente
  - Barrierefreiheit durch ARIA-Attribute
  - Meta-Tags für PWA-Unterstützung

### Bibliotheken
- **Chart.js**: Für Datenvisualisierung und Diagramme
- **Lottie**: Für komplexe Animationen
- **FontAwesome**: Für Icons und visuelle Elemente

### PWA-Funktionalität
- **Service Worker**: Für Offline-Funktionalität
- **Manifest.json**: Für Installation auf Geräten
- **Cache API**: Für Ressourcen-Caching

---

## Backend

### Server
- **Node.js**: JavaScript-Runtime
- **Express.js**: Minimalistisches Web-Framework
  - RESTful API-Endpunkte
  - JSON-Verarbeitung
  - Statisches Datei-Serving

### Datenverarbeitung
- **ExcelJS**: Für Excel-Export-Funktionalität
- **dotenv**: Für Umgebungsvariablen-Management

---

## Datenspeicherung

### Primärspeicher
- **Redis** (Upstash): 
  - Schlüssel-Wert-Speicher
  - Serverless-kompatibel
  - Einfache JSON-Speicherung

### Fallback-Speicher
- **localStorage**: 
  - Clientseitiger Speicher
  - Offline-Funktionalität
  - Synchronisierung bei Wiederverbindung

---

## Deployment

### Hosting
- **Vercel**: 
  - Serverless-Deployment
  - Automatische HTTPS-Konfiguration
  - Einfache CI/CD-Pipeline

### Konfiguration
- **vercel.json**: 
  - Routing-Regeln
  - Build-Konfiguration
  - Umgebungsvariablen-Management

---

## Architekturprinzipien

### Datenfluss
- **Offline-First**: Lokale Datenspeicherung mit Server-Synchronisation
- **Einfache API**: Klare, RESTful Endpunkte
- **Fehlerbehandlung**: Robuste Fallback-Mechanismen

### Benutzeroberfläche
- **Mobile-First**: Optimiert für Mobilgeräte, skaliert für Desktop
- **Visuelles Feedback**: Animationen und Farbcodierung für Benutzeraktionen
- **Intuitive Navigation**: Tab-basierte Oberfläche mit klaren Aktionen

---

## Optimierungen für zukünftige Projekte

### Codeorganisation
- JavaScript in Module aufteilen
- Komponenten-basierte Struktur implementieren
- Globale Zustände besser kapseln

### Sicherheit
- API-Authentifizierung verbessern
- CSRF-Schutz implementieren
- Sensible Daten sicher verwalten

### Testbarkeit
- Unit-Tests für Kernfunktionen
- End-to-End-Tests für kritische Pfade
- Automatisierte Builds mit Testintegration

---

## Anwendungsfälle

Dieser Techstack eignet sich besonders für:

- **Progressive Web Apps** mit Offline-Funktionalität
- **Datenerfassungsanwendungen** mit einfacher Struktur
- **Mobile-orientierte Tools** für Feldarbeit
- **Interne Unternehmensanwendungen** mit schneller Entwicklungszeit
- **Prototypen** mit Potenzial zur Produktionsreife

---

*Version: 1.0.0*  
*Letzte Aktualisierung: 2024* 