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
- Zu synchronisieren: Aufgaben, Buchungen, Personen, **Termine, Einkaufslisten, Einkaufsartikel** (alle Datensätze haben bereits `id` + `updatedAt`)
- Einkaufsliste und Kalender sind die Funktionen, die am stärksten vom Teilen profitieren
- Backup (.json) und Excel-Export bleiben erhalten

**Voraussetzung:** Firebase-Projekt anlegen (kostenloser Spark-Plan) und Web-Konfiguration bereitstellen.

**Alternative:** Supabase (EU-Region). Firebase bevorzugt wegen ausgereifter Offline-Synchronisierung.
