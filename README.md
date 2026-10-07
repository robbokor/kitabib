# KitaBib

Prototyp einer digitalen Kita-Bibliothek: Ausleihe und Rückgabe per QR-Code,
Bucherfassung über den ISBN-Strichcode, datensparsame Kinderverwaltung.

**Zur Anwendung:** https://robbokor.github.io/kitabib/

## Was hier liegt

Eine einzige HTML-Datei (`index.html`). Kein Server, kein Build, keine
Abhängigkeiten. Alles ist darin enthalten – auch der QR- und der
EAN-13-Decoder für das Scannen mit der Tabletkamera.

## Wo die Daten liegen

**Nicht hier.** Bestand, Kinderkonten und Ausleihen entstehen ausschließlich
im Browser des Geräts, auf dem die Anwendung geöffnet wird (`localStorage`),
und verlassen es nie. Dieses Repository enthält keine personenbezogenen Daten,
sondern nur einen Beispielbestand mit erfundenen Namen.

Nach außen geht einzig die ISBN, wenn Buchdaten abgerufen werden – an die
Deutsche Nationalbibliothek (`services.dnb.de`), ersatzweise an OpenLibrary.

Weil die Daten auf dem Gerät liegen, gilt: **regelmäßig sichern.** Die
Anwendung erinnert wöchentlich daran (Mehr → Bestand übernehmen → Jetzt sichern).

## Auf dem iPad einrichten

1. Die Adresse oben in Safari öffnen.
2. Teilen-Symbol → **Zum Home-Bildschirm**.
3. Beim ersten Scan den Kamerazugriff erlauben.

Die Anwendung startet dann im Vollbild wie eine App. Ohne Kamerafreigabe
funktioniert weiterhin alles über die manuellen Wege (Kind suchen, Buch suchen,
ISBN eintippen).

## Stand

Prototyp zur Erprobung im Alltag – noch ohne Anmeldung, ohne Mandantentrennung
und ohne gemeinsamen Datenbestand über mehrere Geräte. Grundlage ist das
Gesamtkonzept V1.0 (Lastenheft, Pflichtenheft, Datenschutz, QR-System, UX/UI,
Jahreswechsel, MVP).

## Aktualisieren

**Die einzige Quelle ist `index.html` in diesem Repository** (Branch `main`).
Daraus baut GitHub Pages die Anwendung. Es gibt keine zweite Arbeitsdatei.

Wer lokal ändern will, holt sich vorher immer den aktuellen Stand und arbeitet
direkt in `index.html`:

```bash
git pull
# index.html bearbeiten
git commit -am "Beschreibung der Änderung"
git push
```

GitHub Pages baut die Seite danach in etwa einer Minute neu.

Früher gab es eine lokale Arbeitsdatei `KitaBib_Prototyp.html`, die über
`index.html` kopiert wurde. Diesen Weg nicht mehr benutzen: Eine alte Kopie
überschreibt beim Kopieren alle Änderungen, die inzwischen in `index.html`
stehen. Der Name bleibt in `.gitignore`, damit eine liegengebliebene Kopie
nicht versehentlich hochgeladen wird.
