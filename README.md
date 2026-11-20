# 🏠 HausManager

Wartung und Projekte rund ums Haus – als Web-App fürs iPhone (Home-Bildschirm), komplett offline-fähig.

- **Daten** liegen ausschließlich lokal auf dem Gerät (localStorage). Dieses Repository enthält nur die App, keine Daten.
- **Backup/Wiederherstellung** über Einstellungen → Datensicherung (.json).
- **Excel-Export** im Verlauf, **Kalender-Export (.ics)** in den Einstellungen.

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
