# Roadmap

## Zurückgestellt – nach Fertigstellung der App

### Synchronisierung zwischen mehreren Geräten (Haushalt)
**Problem:** Jedes Gerät speichert seine Daten nur lokal (localStorage). Mehrere Personen sehen deshalb unterschiedliche Stände.

**Geplante Lösung:** Google Firebase (Firestore)
- Region `europe-west3` (Frankfurt)
- Offline-Persistenz von Firestore: Abhaken ohne Netz, automatischer Abgleich bei Empfang
- Echtzeit-Updates zwischen den Geräten
- Anmeldung per E-Mail-Link (passwortlos), Zugriff per Security Rules nur für den Haushalt
- Einmalige Übernahme der bestehenden lokalen Daten beim ersten Login
- Zu synchronisieren: Aufgaben, Buchungen, Personen, **Termine, Einkaufslisten, Einkaufsartikel, Rezepte, Wochenplan** (alle Datensätze haben bereits `id` + `updatedAt`)
- Einkaufsliste und Kalender sind die Funktionen, die am stärksten vom Teilen profitieren
- Backup (.json) und Excel-Export bleiben erhalten

**Voraussetzung:** Firebase-Projekt anlegen (kostenloser Spark-Plan) und Web-Konfiguration bereitstellen.

**Alternative:** Supabase (EU-Region). Firebase bevorzugt wegen ausgereifter Offline-Synchronisierung.

### Rezepte per Link importieren
Browser dürfen fremde Webseiten nicht direkt auslesen (CORS). Lösung: kleiner Server-Baustein
(z. B. Cloud Function oder Cloudflare Worker), der die Rezeptseite abruft und die strukturierten
Rezeptdaten (schema.org `Recipe`, JSON-LD) zurückgibt. Sinnvoll zusammen mit dem Sync umzusetzen.
Bis dahin: Text der Rezeptseite kopieren → „Text einfügen & aufteilen“.

### Aktuelle Angebote / Prospektpreise
Benötigt eine Datenquelle, die Händlerpreise offiziell bereitstellt (lizenzierter Anbieter mit API,
i. d. R. kostenpflichtig). Automatisches Auslesen von Supermarkt- oder Prospektportalen verstößt in
aller Regel gegen deren Nutzungsbedingungen und wird nicht umgesetzt. Offen: geeigneten Anbieter prüfen.

### Wartung
- GitHub-Actions im Deploy-Workflow auf Versionen mit Node.js 24 aktualisieren (Hinweis im Actions-Log).
