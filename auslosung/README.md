# Zimmerauslosung

Zimmer auf einer Gruppenfahrt verlosen – mit echten Kugeln auf dem Tisch.
Das Programm zieht nicht, es **zählt mit, prüft und schreibt auf**.

Eine einzige HTML-Datei. Kein Server, kein Build, keine Abhängigkeiten,
keine externen Schriften – funktioniert offline im Hotelflur.

## Wie es gedacht ist

**Ein Bett = eine Kugel.** Ein Vierbettzimmer mit der Nummer 3 heißt: viermal
die Kugel „3“ in der Trommel. Wer zieht, kann kein volles Zimmer erwischen,
weil die passenden Kugeln gar nicht mehr drin liegen.

1. **Zimmer** anlegen: Kugelnummer und Bettenzahl. Für Serien gibt es
   „Mehrere auf einmal“ (Zimmer 1–8, je 4 Betten).
2. **Teilnehmer** eintragen – einzeln oder als Liste aus Excel/Mail einfügen.
   Wer eine **feste Vorbelegung** bekommt (Betreuer, Geschwister), zieht nicht
   mit und nimmt sein Bett aus der Losung.
3. **Packliste drucken.** Sie sagt, welche Kugeln in die Trommel gehören –
   nach Abzug der Vorbelegungen. Das ist der Schritt, an dem eine Auslosung
   sonst kaputtgeht.
4. **Auslosung:** Person antippen, gezogene Kugelnummer antippen, fertig.
   Volle Zimmer sind gesperrt. Der letzte Zug lässt sich zurücknehmen.
   Die Trommelanzeige zeigt jederzeit, was noch drin sein müsste – nachzählen.
5. **Ergebnis:** Die echte Hotelzimmernummer nachtragen, sobald sie an der
   Rezeption bekannt ist. Kugel 3 bleibt Kugel 3, zeigt aber überall
   „Hotel 214“. Zwei Personen tauschen geht protokolliert.
6. **Drucken:** Belegungsliste (nach Zimmer und nach Name) und Türschilder.

Das **Protokoll** hält fest, wer wann was gezogen hat, jede Vorbelegung und
jeden Tausch – falls hinterher jemand fragt.

## Wenn die Trommel fehlt

Unter „Ersatzweise digital ziehen“ zieht das Programm selbst eine der
verbleibenden Kugeln (`crypto.getRandomValues`). Solche Züge werden im
Ergebnis und im Protokoll als *digital* gekennzeichnet – die Gruppe soll
sehen, welche Züge nicht am Tisch passiert sind.

## Wo die Daten liegen

**Nur in diesem Browser** (`localStorage`). Nichts wird übertragen, es gibt
keinen Server und keine Netzwerkverbindung. Das heißt aber auch: Wer die
Websitedaten löscht oder das Gerät verliert, verliert die Auslosung.

**Vor der Fahrt sichern** – „Sichern“ oben rechts legt eine JSON-Datei ab,
„Sicherung einlesen“ holt sie zurück, auch auf einem anderen Gerät.

## Auf dem Tablet einrichten

Seite in Safari/Chrome öffnen → Teilen → **Zum Home-Bildschirm**.
Läuft dann im Vollbild wie eine App, auch ohne Netz.

## Stand

Erprobungsstand. Bewusst nicht enthalten: getrennte Ziehungen (z. B. Jungen
und Mädchen in einem Durchgang), Ausschlussregeln („diese beiden nicht
zusammen“), mehrere Geräte gleichzeitig.
