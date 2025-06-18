# Multi-Datensatz Messdaten-Eingabe

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/greenenergylab/datahandling/HEAD?urlpath=%2Fdoc%2Ftree%2Fdata_import.ipynb)

Eine interaktive Jupyter-Notebook-Anwendung zur Erfassung und Verwaltung von Messdaten mit mehreren Datensätzen.

## Features

- **Multi-Datensatz-Verwaltung**: Erstellen und verwalten Sie mehrere unabhängige Datensätze
- **Messdatenerfassung**: Eingabe von Spannung, Stromstärke, Drehzahl und optionalen Notizen
- **Automatische Berechnungen**: Berechnung der elektrischen Leistung (P = U × I)
- **Datenvisualisierung**: Anzeige der Daten in tabellarischer Form mit Statistiken
- **Export-Funktionen**: Export einzelner oder aller Datensätze als CSV-Dateien
- **Session-Management**: Speichern und Laden kompletter Arbeitssitzungen als JSON
- **Benutzerfreundliche GUI**: Intuitive Bedienung über Jupyter Widgets

## Verwendung

### Lokale Installation

1. Repository klonen:
```bash
git clone https://github.com/DEIN-GITHUB-USERNAME/DEIN-REPOSITORY-NAME.git
cd DEIN-REPOSITORY-NAME
```

2. Abhängigkeiten installieren:
```bash
pip install -r requirements.txt
```

3. Jupyter Notebook starten:
```bash
jupyter notebook
```

4. Das Notebook `Dateneingabemaske.ipynb` öffnen und ausführen

### Online mit Binder

Klicken Sie einfach auf den Binder-Badge oben, um die Anwendung direkt im Browser zu starten - keine Installation erforderlich!

## Anleitung

### 1. Neuen Datensatz erstellen
- Geben Sie einen Namen für Ihren Datensatz ein
- Klicken Sie auf "Neuen Datensatz erstellen"

### 2. Messwerte eingeben
- **Spannung**: Wert in Volt (V)
- **Stromstärke**: Wert in Milliampere (mA)
- **Drehzahl**: Wert in Umdrehungen pro Minute (U/min)
- **Notiz**: Optionale zusätzliche Informationen
- Klicken Sie auf "Wert hinzufügen"

### 3. Daten verwalten
- **Datensatz anzeigen**: Zeigt alle Messungen mit Statistiken
- **Übersicht**: Zeigt alle vorhandenen Datensätze
- **Letzten Wert löschen**: Entfernt die neueste Messung
- **Datensatz löschen**: Entfernt den kompletten Datensatz

### 4. Export und Speicherung
- **Datensatz als CSV**: Exportiert den aktuellen Datensatz
- **Alle als CSV**: Exportiert alle Datensätze einzeln
- **Session speichern**: Speichert alle Daten als JSON-Datei
- **Session laden**: Lädt eine gespeicherte JSON-Datei

## Datenformat

Die Anwendung erfasst folgende Messwerte:
- Zeitstempel (automatisch)
- Spannung in Volt
- Stromstärke in Milliampere
- Drehzahl in U/min
- Berechnete Leistung in Milliwatt (P = U × I)
- Optionale Notiz

## PDF-Export

Die Binder-Umgebung unterstützt den Export von Notebooks als PDF:

1. **Über das Menü**: `File` → `Download as` → `PDF via LaTeX (.pdf)`
2. **Über die Kommandozeile** (im Terminal):
   ```bash
   jupyter nbconvert --to pdf Dateneingabemaske.ipynb
   ```

### Voraussetzungen für PDF-Export
- LaTeX-Installation (automatisch in Binder verfügbar)
- Pandoc (automatisch installiert)
- NBConvert (in requirements.txt enthalten)

## Technische Details

- **Python**: ≥3.7
- **Jupyter Widgets**: Für die interaktive Benutzeroberfläche
- **Pandas**: Für Datenverarbeitung und -analyse
- **NBConvert**: Für PDF-Export
- **LaTeX**: Für PDF-Generierung (XeTeX)
- **JSON**: Für Session-Speicherung
- **CSV**: Für Datenexport

## Beitragen

Verbesserungsvorschläge und Bug-Reports sind willkommen! Erstellen Sie gerne Issues oder Pull Requests.

## Lizenz

Dieses Projekt steht unter der MIT-Lizenz.

## Hinweise

- Verwenden Sie Komma oder Punkt als Dezimaltrennzeichen
- Leere Felder werden als 0 interpretiert
- Mindestens ein Messwert muss eingegeben werden
- Sessions werden als JSON-Dateien gespeichert und können zwischen Sitzungen übertragen werden

## Fehlerbehebung

**Problem**: Widgets werden nicht angezeigt
- **Lösung**: Stellen Sie sicher, dass ipywidgets installiert und aktiviert ist:
```bash
jupyter nbextension enable --py widgetsnbextension
```

**Problem**: CSV-Export funktioniert nicht
- **Lösung**: Überprüfen Sie die Schreibberechtigungen im Arbeitsverzeichnis

**Problem**: PDF-Export schlägt fehl
- **Lösung**: Stellen Sie sicher, dass LaTeX installiert ist. In Binder ist dies automatisch verfügbar.
- **Alternative**: Verwenden Sie `File` → `Download as` → `HTML (.html)` und drucken Sie dann als PDF

**Problem**: PDF enthält keine Widget-Ausgaben
- **Lösung**: Führen Sie alle Zellen vor dem Export aus, damit die Ausgaben sichtbar sind
