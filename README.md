# TaxPilot AI Frontend

Demo-MVP zur KI-gestützten Vorprüfung von Rechnungen für Freelancer und Selbstständige in Deutschland.

Live-Demo:  
https://tax-pilot-ai-kappa.vercel.app/

## Was macht TaxPilot AI?

TaxPilot AI analysiert hochgeladene Rechnungen und gibt eine erste Einschätzung zurück:

- steuerlich relevant: `Ja`, `Nein` oder `Manuell prüfen`
- erkannte Kategorie, z. B. Software, Hardware, Weiterbildung oder Sonstiges
- Anbieter, Rechnungsdatum und Beträge
- Confidence-Wert
- kurze Begründung und Empfehlung

Hinweis: TaxPilot AI ist keine Steuerberatung, sondern nur eine automatische Vorprüfung.

## Wie funktioniert es?

```text
Vercel Frontend
→ PDF-Upload im Browser
→ Textextraktion mit pdf.js
→ Make.com Webhook
→ KI-Analyse mit Make AI Toolkit / OpenAI
→ Supabase Storage + Datenbank
→ Ergebnis zurück ans Frontend
