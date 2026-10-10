# LF5 Lernwerkstatt

Lern-App für die LF5-Klausur am 4. November 2026. Acht Module, 32 Karteikarten, 20 Rechenaufgaben, 32 Theoriefragen, gemischte Probetests, Fehlerliste und Tagesplan. Deutsch, mobil nutzbar, ohne Build oder Anmeldung.

## Direkt starten

`dist/index.html` im Browser öffnen. Die App benötigt keine Installation und keine externen Bibliotheken. Für verlässliche Fortschrittsspeicherung empfiehlt sich GitHub Pages oder ein lokaler HTTP-Server (`python3 -m http.server 8000 --directory dist`).

## Über GitHub benutzen

1. ZIP entpacken. Ein neues GitHub-Repository anlegen, z. B. `lf5-lernapp`.
2. Alle Dateien und Ordner aus dem entpackten Projekt in das Repository hochladen und auf `main` committen. Wichtig: `dist/index.html` und `.github/workflows/pages.yml` müssen enthalten sein. Ein entpackter übergeordneter Ordner darf nicht als zusätzliche Ebene ins Repository.
3. Im Repository unter **Settings → Pages → Build and deployment → Source** die Option **GitHub Actions** wählen.
4. Unter **Actions** den Workflow **Lern-App auf GitHub Pages** starten (Run workflow) oder einen neuen Commit auf `main` erstellen. Nach dem erfolgreichen Lauf steht der Link unter **Settings → Pages**.
5. Typische Adresse: `https://DEIN-BENUTZERNAME.github.io/lf5-lernapp/`.

Alternative ohne Workflow: den Inhalt des `dist`-Ordners direkt ins Repository-Hauptverzeichnis hochladen. Dann Pages auf **Deploy from a branch → main → / (root)** stellen. Den `.github`-Ordner bei dieser Variante weglassen.

GitHub muss Pages für dein Konto und das gewählte Repository unterstützen. In diesem Chat wurde kein Repository in deinem GitHub-Konto angelegt.

## Lernablauf

Mit Modul 1 anfangen. Erklärung lesen, Karten aktiv beantworten, passende Aufgaben selbst rechnen. Module und Lerntage separat abhaken. Probetests geben Rückmeldung und sammeln falsche Antworten. Sichere Karten werden nach drei Tagen, unsichere nach einem Tag wieder fällig.

Fortschritt wird in `localStorage` dieses Browsers gespeichert, nicht in GitHub. In den Einstellungen als JSON exportieren und auf einem anderen Gerät importieren. Löschen von Browserdaten löscht auch den Lernstand. Es gibt keine automatische Synchronisation.

## Inhalt und Quellen

Die Unterrichtsdateien `LF 5(2).pdf` und `LF 5 1 Festpunkte.pdf` bilden den Stoffumfang. In der zweiten Datei stehen hauptsächlich Zwischenblickaufgaben. Quellenstellen werden in jedem Modul genannt. Die Original-PDFs sind nicht enthalten. Trainingsfragen und Beispiele sind neu erstellt; sie sind keine echte Klausur. Originalaufgaben auf Papier sind im Lernplan vorgesehen.

Die Fehlergrenzen entsprechen dem Arbeitsblatt auf PDF-Seite 50: 3. Ordnung `±(2 + 5√s) mm`, s in km. Verbesserungskonvention: `f = Soll − Ist`. Ergänzende fachliche Prüfung zur Höhenumrechnung: https://www.bkg.bund.de/DE/Themen/Referenzsysteme/Referenzsysteme-National/Hoehenbezugsflaeche-Deutschland/hoehenbezug_cont.html

## Technisch

Statische Dateien in `dist`, relative Dateipfade für GitHub-Projektseiten. Keine Analytik, externen Schriftarten, API-Schlüssel oder Framework-Abhängigkeiten. `node --check dist/app.js` und `node --check dist/content.js` prüfen JavaScript-Syntax.
