# TaxPilot AI Frontend

Statischer Demo-MVP fuer die TaxPilot-AI-Rechnungsanalyse.

## Start

Die Anwendung besteht aus einer einzelnen `index.html` und kann direkt im Browser geoeffnet werden:

```text
C:\Users\Nori_\Projekte\taxpilot-ai-frontend\index.html
```

Optional kann ein lokaler Webserver genutzt werden:

```bash
npx serve .
```

## Enthalten

- Login-Demo mit Plausibilitaetspruefung
- Dashboard mit Upload per Klick oder Drag and Drop
- Make.com-Webhook-Anbindung fuer Live-Analysen
- PDF-Textextraktion im Browser fuer durchsuchbare PDF-Rechnungen
- Lokaler Demo-Fallback, falls der Webhook nicht erreichbar ist
- Synchronisierte Historie, Statistik und Ergebnisansicht
- CSV-Export der Historie
- Druck/PDF-Ausgabe ueber die Browser-Druckfunktion
- Lokale Speicherung der Demo-Historie im Browser via `localStorage`

## Live-Anbindung

Der Make.com-Webhook ist in `index.html` ueber `MAKE_WEBHOOK_URL` konfiguriert. Fuer eine echte Live-Demo muss das Make-Szenario aktiv sein und eine JSON-Antwort im erwarteten Format liefern.

Der Frontend-Request sendet JSON an den Custom Webhook:

- `fileName` / `filename`
- `mimeType`
- `fileSize`
- `uploadedAt`
- `source`
- `invoiceText`
- `extractionStatus`
- `fileBase64`

Wichtige Felder:

- `taxRelevant`: `Ja`, `Nein` oder `Manuell pruefen`
- `category`
- `vendor`
- `invoiceDate`
- `amountGross`
- `confidence`
- `recommendation`
- `needsManualReview`

Der aktuelle Make.com-Flow passt dazu:

1. Custom Webhook nimmt den Frontend-Request entgegen.
2. Make AI Toolkit analysiert `invoiceText` und gibt ausschliesslich JSON zurueck.
3. JSON Parser parst `Answer`.
4. Webhook Response antwortet mit Status `200` und dem JSON-Body.

## Hinweise

Dies ist ein Frontend-Prototyp. Supabase Auth und Datenpersistenz im Backend sind in der Architektur dokumentiert, aber noch nicht in diesem statischen Frontend implementiert. Fuer gescannte PDFs oder Bildbelege sollte im Make.com-Workflow zusaetzlich OCR bzw. Dokumentenextraktion ergaenzt werden.
