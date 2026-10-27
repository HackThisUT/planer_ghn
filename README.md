# Lehrerplaner

Eine mobile-first, offline-fähige Planungs-App für Lehrkräfte. Sie benötigt keine externen Bibliotheken, Schriftarten oder Dienste.

## Öffnen
- **Lokal:** `index.html` im Browser öffnen. Die App funktioniert; aus Sicherheitsgründen kann der Service Worker bei `file://` nicht aktiviert werden. Für Offline-Cache lokal kann ein kleiner HTTP-Server verwendet werden (z. B. `python3 -m http.server 8000` im Ordner, dann `http://localhost:8000`).
- **Webserver:** Den gesamten Inhalt dieses Ordners unverändert auf einen HTTPS-Webserver legen. Nach dem ersten Aufruf wird die App-Shell für Offline-Nutzung zwischengespeichert.
- **GitHub Pages:** Ordnerinhalt ins veröffentlichte Repository (oder Unterverzeichnis) legen und GitHub Pages aktivieren. Die relativen Pfade funktionieren auch in einem Projekt-Unterordner.
- **iPhone (Safari, auch iPhone 17):** App über ihre HTTPS-Adresse in Safari öffnen → Teilen → **Zum Home-Bildschirm** → Hinzufügen. Danach startet sie im eigenständigen App-Fenster. Für Offline-Nutzung einmal online laden, damit der Cache angelegt werden kann.

## Daten
Unterrichts- und Planungsdaten werden lokal im `localStorage` des verwendeten Browsers gespeichert und nicht an einen Server übertragen. Über **Einstellungen → JSON exportieren** regelmäßig eine Sicherung speichern. Mit **JSON importieren** kann sie wiederhergestellt werden. Beim Löschen von Browserdaten oder Geräte-/Browserwechsel gehen lokale Daten verloren, sofern sie nicht exportiert wurden.

Die App-Oberfläche ist deutschsprachig; der Wochenplan basiert auf einer Standardvorlage, einzelne konkrete Wochen können separat abweichend eingetragen werden.

## A-/B-Wochenrhythmus
Der Wochenplan verwendet zwei getrennte Vorlagen. Die bisherige Standardvorlage bleibt erhalten und wird als A-Wochenvorlage genutzt; die B-Wochenvorlage startet leer. Unter **Einstellungen** kann das Datum des Rhythmusankers und dessen Typ (A oder B) festgelegt werden. Der Typ wechselt danach kalenderwochenweise automatisch. Im Wochenplan und in der Tagesübersicht wird die aktuelle Zuordnung angezeigt; über **A/B wechseln** lässt sich eine einzelne Woche manuell zuordnen, mit **Automatisch** wieder auf den Anker-Rhythmus zurücksetzen. Bei der Bearbeitung einer Stunde kann festgelegt werden, ob Klasse und Raum in die A- oder B-Wochenvorlage übernommen werden.
