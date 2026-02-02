# Agiles Projekt- und Prozessmanagement – Prototyp

**Kreisverwaltung Herford**
Projektteam: Baran, Adriana, Ferhat

---

## Beschreibung

Dieser Prototyp ist eine Electron-Desktop-Anwendung zur strukturierten Erfassung und Analyse von Digitalisierungsproblemen in der Kreisverwaltung Herford. Über einen mehrstufigen Fragebogen (Problemlandkarte) werden Schwachstellen identifiziert, bewertet und in einem IT-Dashboard visualisiert.

## Funktionen

- **Startscreen** mit Logo der Kreisverwaltung Herford
- **Personenerfassung** – Name, Digitalisierungsbewertung und Wünsche
- **Mehrstufiger Fragebogen** (5 Schritte):
  1. Kontext (Amt, Prozessart, Kanäle, Volumen, betroffene Mitarbeitende)
  2. Problemcluster-Bewertung (5 Bereiche mit Drilldown-Fragen bei Bewertung 0–3)
  3. Priorisierung und Auswirkung
  4. Allgemeine Bemerkungen
  5. Übersicht mit Score- und Risiko-Kreisdiagrammen
- **IT-Dashboard** mit KPI-Übersicht, Falltabelle und Detail-Drawer
- **Scoring-System** mit Risikobewertung und kontextabhängigen Boostern
- **Automatische Stichpunkt-Generierung** basierend auf den Fragebogen-Antworten
- **Ladebildschirm** mit animiertem GIF zwischen Seitenwechseln
- **Endscreen** mit Projektcredits und Neustart-Option

### Problemcluster

| Cluster | Drilldown-Fragen |
|---|---|
| Medienbruch / Copy-Paste / Papier | Wo, Häufigkeit, betroffene Systeme |
| Wartezeiten / Liegezeiten / Freigaben | Ursachen, Engpass, Prozessdauer |
| Fehlerquote / Nacharbeit / Rückläufer | Art der Nacharbeit, Fehlerhäufigkeit |
| IT-Infrastruktur / Systeme | IT-Probleme, Häufigkeit |
| Wissen / Schulung / Akzeptanz | Defizite, gewünschte Hilfe |

## Technologie

- **Electron** (v40.1.0)
- Reines HTML/CSS/JavaScript (keine Frameworks, keine externen Bibliotheken)
- **localStorage** als Datenspeicher zwischen den Seiten
- CSS `conic-gradient` für Kreisdiagramme

## Installation und Start

```bash
npm install
npm start
```

## Projektstruktur

```
├── main.js                          # Electron Main-Prozess
├── dashboard_problemlandkarte.html  # Startscreen, Personeneingabe, Fragebogen
├── loading.html                     # Ladebildschirm (5s)
├── it_dashboard.html                # IT-Dashboard mit Auswertung
├── end_screen.html                  # Endscreen mit Credits
├── logo-kreis-herford.jpg           # Logo
├── progressbar.gif                  # Lade-Animation
└── package.json
```

## Datenfluss

```
Startscreen → Personeneingabe → Fragebogen (5 Schritte) → Ladescreen → IT-Dashboard → Ladescreen → Endscreen
```

Alle Daten werden über `localStorage` weitergegeben:
- `problemlandkarte_person` – Personendaten
- `problemlandkarte_current` – Fragebogen-Ergebnisse inkl. Score, Risiko und Stichpunkte

## Lizenz

Prototyp v1.0 – Agiles Projekt- und Prozessmanagement, Kreisverwaltung Herford
