# TaxPilot AI Architektur

Diese Architektur ist als **LikeC4-Modell** umgesetzt. Die Datei `taxpilot.c4` beschreibt die Systemlandschaft, Container und Komponenten von TaxPilot AI.

## Voraussetzungen

Du brauchst:

- **Node.js** inkl. `npm`
- Einen Code-Editor, empfohlen: **Visual Studio Code**
- Optional: die **LikeC4 VS Code Extension** für Live Preview, Autocomplete und Validierung
- Die Datei `taxpilot.c4`

## Projekt starten

Lege `taxpilot.c4` in einen Projektordner, öffne den Ordner im Terminal und starte LikeC4:

```bash
npx likec4 start
```

Danach öffnet sich die lokale LikeC4-Vorschau im Browser. Dort kannst du zwischen den Architektur-Views wechseln und per Drill-down durch die Ebenen navigieren.

## Enthaltene Views

Das Modell enthält mehrere Sichten auf die Architektur:

- **System Context**: User, TaxPilot AI, Make.com, OpenAI API und Supabase
- **Container View**: Frontend Web App, Make.com Workflow, OpenAI Completion Endpoint und Supabase
- **Frontend Components**: Login, Dashboard, PDF-Extraktion, Historie, API Client und Ergebnisanzeige
- **Make.com AI Flow**: Webhook, AI Toolkit, JSON Parser und Response
- **Data and Security**: Supabase Auth, RLS Policies, Tabellen `rechnungen` und `feedback`

## Diagramme exportieren

Um die Diagramme als PNG-Dateien zu exportieren:

```bash
npx likec4 export png -o ./diagrams
```

Die exportierten Bilder liegen danach im Ordner `diagrams`.

## Architektur ausführen vs. Architektur anzeigen

Diese README beschreibt, wie du die **Architekturvisualisierung** startest. Sie startet nicht die eigentliche TaxPilot-AI-Anwendung.

Für die echte Anwendung werden zusätzlich benötigt:

- Frontend-Code der Web-App
- Supabase-Projekt mit Auth, Datenbanktabellen und RLS Policies
- Make.com-Szenario mit Webhook und OpenAI-Schritt
- OpenAI API Key
- Konfiguration der Umgebungsvariablen im Frontend und in Make.com

## Empfohlener Workflow

1. `taxpilot.c4` in Git versionieren
2. Änderungen an der Architektur im Modell pflegen
3. Views lokal mit `npx likec4 start` prüfen
4. Bei Bedarf Diagramme exportieren und in Dokumentation oder Präsentationen verwenden
