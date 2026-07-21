# QWIC Händler-Tools (Web-App)

HEK-Kalkulation + Partnervertrag-2027-Generator als installierbare Web-App (PWA).

## In 3 Schritten online stellen (GitHub Pages)

0. Einmalig vorab (Terminal in diesem Ordner) - Git-Sperrdateien aus der
   Erstellung entfernen und README committen:

```bash
rm -f .git/index.lock .git/HEAD.lock .git/objects/maintenance.lock
git add -A && git commit -m "README"
```

1. Neues Repository anlegen: https://github.com/new (z. B. `qwic-tools`).
   Hinweis: GitHub Pages ist im Free-Plan nur bei **öffentlichen** Repos verfügbar.

2. Im Terminal, in diesem Ordner (`qwic-app`):

```bash
git remote add origin https://github.com/DEIN-USERNAME/qwic-tools.git
git push -u origin main
```

3. Auf GitHub: Settings -> Pages -> Branch `main` / (root) -> Save

Nach 1-2 Minuten läuft die App unter:
`https://DEIN-USERNAME.github.io/qwic-tools/`

## App installieren

- Desktop (Chrome/Edge): Installations-Symbol in der Adressleiste -> "Installieren"
- iPhone/iPad (Safari): Teilen -> "Zum Home-Bildschirm"
- Android (Chrome): Menü -> "App installieren"

Nach dem ersten Aufruf funktioniert die App auch offline (Service Worker Cache).

## Updates veröffentlichen

Änderungen an `index.html` committen und pushen - fertig. Damit Nutzer die neue
Version offline erhalten, in `sw.js` die Version hochzählen
(`qwic-tools-v1` -> `qwic-tools-v2`).

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Die komplette App (Kalkulation + Vertragsgenerator) |
| `manifest.webmanifest` | App-Name, Icons, Installationsverhalten |
| `sw.js` | Offline-Cache (Service Worker) |
| `icons/` | App-Icons aus dem CI-Logo (QWIC Huisstijl) |

## MACAN-Font einbinden

Die Fontdateien (`MACAN-Regular.woff2`, `MACAN-Bold.woff2`) in diesen Ordner
legen und in `index.html` den auskommentierten `@font-face`-Block aktivieren.
