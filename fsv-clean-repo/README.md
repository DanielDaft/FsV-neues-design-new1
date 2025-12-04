# FsV - Deutsche Fahrschul-App

Eine moderne, responsive Progressive Web App (PWA) zur Verwaltung von Fahrschülern und deren Ausbildungsfortschritt.

![Version](https://img.shields.io/badge/version-7.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)

## ✨ Features

### 🎯 Führerscheinklassen-Management
- Unterstützung für **10 Führerscheinklassen**: B, BE, AM, A1, A2, A, C, CE, C1, C1E
- Klassenspezifische Ausbildungsinhalte und Anforderungen
- Anpassbare Trainings-Kategorien pro Klasse

### 👥 Schülerverwaltung
- Vollständige Schülerdaten (Name, Adresse, Kontakt, Geburtsdatum)
- Ausbildungsbeginn und Prüfungsdaten
- Theorie- und Praxisprüfungsstatus
- Brillenträger-Kennzeichnung

### 📊 Fortschritts-Tracking
- **Interaktive Kreise** für Übungsstunden (Ü-Kreise)
- **Viertelkreise** für Sonderfahrten-Tracking
- **Blaue PS-Kreise** für Pflichtfahrten (Überland, Autobahn, Nacht)
- **Checkboxen-System** mit 3 Status-Stufen (/, ×, ⊗)
- Echtzeit-Fortschrittsanzeige in Prozent

### 📱 Modernes Design
- **3-Spalten Grid-Layout** auf Desktop
- Responsive Design für Tablet (2 Spalten) und Mobile (1 Spalte)
- **Dark/Light Mode** mit automatischer Theme-Erkennung
- Touch-optimierte Bedienung für Smartphones und Tablets

### 📄 Export & Speicherung
- **PDF-Export** des Ausbildungsnachweises
- **LocalStorage-Persistierung** - Daten bleiben lokal gespeichert
- Keine Server-Abhängigkeit
- Offline-fähig durch PWA-Technologie

### ⚡ Progressive Web App (PWA)
- Installierbar auf Desktop und Mobile
- Offline-Funktionalität durch Service Worker
- App-ähnliches Erlebnis
- Schnelle Ladezeiten

## 🚀 Schnellstart

### Lokale Verwendung

1. **Repository klonen:**
```bash
git clone https://github.com/dein-username/fsv-fahrschul-app.git
cd fsv-fahrschul-app
```

2. **Mit lokalem Server öffnen:**
```bash
# Python 3
python3 -m http.server 8080

# Oder Python 2
python -m SimpleHTTPServer 8080

# Oder mit Node.js
npx http-server -p 8080
```

3. **Im Browser öffnen:**
```
http://localhost:8080
```

### Direkter Start

Alternativ kannst du die `index.html` direkt im Browser öffnen (einige Funktionen benötigen jedoch einen Server).

## 📱 Installation als PWA

### Desktop (Chrome, Edge, Safari)
1. App im Browser öffnen
2. Browser-Menü → "App installieren" oder "Zu Startbildschirm hinzufügen"
3. Bestätigen

### Mobile (iOS & Android)
1. App im Browser öffnen
2. **iOS**: Safari → Teilen-Button → "Zum Home-Bildschirm"
3. **Android**: Chrome → Menü → "App installieren" oder "Zum Startbildschirm hinzufügen"

## 🎨 Führerscheinklassen

| Klasse | Fahrzeugtyp | Beschreibung |
|--------|-------------|-------------|
| **B** | PKW | Personenkraftwagen bis 3,5t |
| **BE** | PKW + Anhänger | PKW mit schwerem Anhänger |
| **AM** | Moped | Leichte zweirädrige Kraftfahrzeuge |
| **A1** | Leichtkraftrad | Motorrad bis 125 ccm |
| **A2** | Kraftrad | Motorrad bis 35 kW |
| **A** | Kraftrad | Motorrad ohne Leistungsbeschränkung |
| **C** | LKW | Kraftfahrzeuge über 3,5t |
| **CE** | LKW + Anhänger | LKW mit schwerem Anhänger |
| **C1** | Leicht-LKW | Kraftfahrzeuge 3,5-7,5t |
| **C1E** | Leicht-LKW + Anhänger | Leicht-LKW mit Anhänger |

## 🛠️ Technologie-Stack

- **Frontend**: Vanilla JavaScript (ES6+)
- **Styling**: CSS3 mit CSS Variables
- **Layout**: CSS Grid & Flexbox
- **Storage**: LocalStorage API
- **PWA**: Service Worker, Web App Manifest
- **Icons**: Unicode-Emojis & SVG
- **Responsive**: Mobile-First Design

## 📂 Dateistruktur

```
fsv-fahrschul-app/
├── index.html          # Haupt-HTML mit eingebettetem CSS & JS
├── manifest.json       # PWA Manifest (App-Metadaten)
├── sw.js              # Service Worker (Offline-Funktionalität)
├── README.md          # Diese Datei
└── .gitignore         # Git-Ignore-Regeln
```

## 💾 Datenspeicherung

Alle Daten werden **lokal im Browser** gespeichert:

- **Schülerdaten**: `localStorage: fahrschul_students_{klasse}`
- **Fortschrittsdaten**: `localStorage: fahrschul_progress_{klasse}_{schülerId}`
- **Theme-Einstellung**: `localStorage: fahrschul-theme`

⚠️ **Wichtig**: Bei Browser-Cache-Löschung gehen Daten verloren. Für Backup: PDF-Export nutzen!

## 🎯 Nutzung

### 1. Klasse wählen
- Nach dem Start: Führerscheinklasse auswählen
- Über Hamburger-Menü: Jederzeit zwischen Klassen wechseln

### 2. Schüler hinzufügen
- Button "+ Neuer Schüler"
- Formular ausfüllen (Name, Adresse, Telefon, etc.)
- Speichern

### 3. Fortschritt tracken

**Kartenansicht (Standard)**:
- Alle Kategorien als Cards
- Farb-kodiert nach Trainingstyp
- Fortschritt in Prozent

**Listenansicht**:
- Detaillierte Übersicht pro Kategorie
- Checkboxen für einzelne Items
- Kreise für Übungsstunden

**Interaktive Elemente**:
- **Ü-Kreise**: Klick zum Füllen/Leeren
- **Viertelkreise**: Klick zum Toggle
- **PS-Kreise**: Klick zum Markieren (nummeriert)
- **Checkboxen**: 3-Stufen-System (leer → / → × → ⊗)

### 4. PDF exportieren
- Button "PDF Exportieren"
- Vollständiger Ausbildungsnachweis
- Druckbar oder speicherbar

## 🌙 Dark Mode

- **Automatisch**: Folgt System-Theme
- **Manuell**: Toggle-Button oben links
- **Persistiert**: Einstellung wird gespeichert

## 🔄 Updates & Versionierung

Service Worker-Version in `sw.js`:
```javascript
const APP_VERSION = '7.0-FORCE-AM-CLASS-UPDATE';
```

Bei Updates:
1. Version in `sw.js` ändern
2. Browser-Cache wird automatisch geleert
3. Neue Version lädt

## 🤝 Contributing

Beiträge sind willkommen! 

1. Fork das Repository
2. Erstelle einen Feature-Branch (`git checkout -b feature/AmazingFeature`)
3. Commit deine Änderungen (`git commit -m 'Add some AmazingFeature'`)
4. Push zum Branch (`git push origin feature/AmazingFeature`)
5. Öffne einen Pull Request

## 📝 Lizenz

MIT License - siehe [LICENSE](LICENSE) für Details

## 🐛 Bug Reports & Feature Requests

Bitte nutze die [GitHub Issues](https://github.com/dein-username/fsv-fahrschul-app/issues) für:
- Bug Reports
- Feature Requests
- Verbesserungsvorschläge

## 👨‍💻 Autor

Erstellt mit ❤️ für deutsche Fahrschulen

## 🙏 Danksagungen

- Deutsche Fahrlehrer-Community
- Alle Tester und Feedback-Geber

---

**Version**: 7.0  
**Letzte Aktualisierung**: Dezember 2024  
**Status**: ✅ Produktionsbereit