# 🏠 HausManager

Wartung und Projekte rund ums Haus – als Web-App fürs iPhone (Home-Bildschirm), komplett offline-fähig.

- **Daten** liegen ausschließlich lokal auf dem Gerät (localStorage). Dieses Repository enthält nur die App, keine Daten.
- **Backup/Wiederherstellung** über Einstellungen → Datensicherung (.json).
- **Wartung:** wiederkehrende Aufgaben mit Saison, Projekte, Zeit- und Kostenbuchung, Verlauf mit Excel-Export.
- **Familienkalender:** Termine pro Person (farbig), ganztägig/mehrtägig, Wiederholungen; Wartungsfälligkeiten erscheinen automatisch. Import aus .ics-Dateien.
- **Einkaufslisten:** mehrere Listen, Mengen-Erkennung („2 Milch“, „500 g Mehl“), Vorschläge aus häufig gekauften Artikeln, Teilen als Text.
- **Rezepte:** eigene Sammlung mit Portionsrechner; Rezepte per Foto scannen (Texterkennung direkt auf dem Gerät, Tesseract.js – wird erst beim ersten Scan geladen) oder Text einfügen; Zutaten mit einem Tipp auf die Einkaufsliste (gleiche Zutaten werden zusammengerechnet).
- **Wochenplan:** Gerichte pro Tag planen, Zutaten der ganzen Woche auf die Einkaufsliste, Gerichte erscheinen im Kalender.

## Aufbau

| Datei | Zweck |
|---|---|
| `app/index.html` | Die komplette App (HTML, CSS, JS in einer Datei) |
| `app/sw.js` | Service Worker: Offline-Start, Cache wird pro Deployment erneuert |
| `app/manifest.webmanifest` | App-Name, Icon, Vollbild-Modus |
| `app/*.png` | App-Icons |
| `.github/workflows/deploy.yml` | Veröffentlicht `app/` bei jedem Push auf `main` auf GitHub Pages |

## Installation aufs iPhone

1. Die GitHub-Pages-Adresse in **Safari** öffnen.
2. Teilen → **Zum Home-Bildschirm**.

## Updates

Änderungen an `app/` committen und auf `main` pushen. Die Action veröffentlicht automatisch;
die App lädt beim nächsten Öffnen mit Internet die neue Version. Daten bleiben erhalten.
