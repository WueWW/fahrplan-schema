# WueWW Fahrplan Schema

... der Fahrplan der [Würzburg Web Week](https://wueww.de/) in maschinenlesbarer Form.

Ziel dieses Projekts ist es, den Fahrplan als _open data_ zur Verfügung zu stellen.
Zunächst einfach mal so, ... natürlich verbunden mit der Hoffnung, dass andere
die Daten für kreative, eigene Projekte nutzen.

Selbstverständlich sind die Daten
[CC0](https://creativecommons.org/publicdomain/zero/1.0/deed.de) lizenziert.
Du kannst also einfach alles damit machen :-)


## Aktuelles JSON Schema

In diesem Repository findest du lediglich die JSON-Schema Datei:
[fahrplan.schema.json](https://raw.githubusercontent.com/WueWW/fahrplan-schema/master/fahrplan.schema.json)

Dieses Schema weicht in Details vom 2019-er Schema ab:

 * es gibt jetzt numerische Schlüssel, das Feld heißt nun `id` (statt bisher `key`)
 * unter `host.links` finden sich nun alle zum Organisator bekannten Links
 * die Zeichenfolge `location.name` enthält nun ausschließlich den Namen der Location,
   die konkrete Adresse findet sich in separaten Feldern unterhalb von `location`
 * die Angabe einer `location` ist nun Pflicht

Für das Jahr 2021 wurde bei den Sessions unter `links` ein neuer Knoten `jobs` geschaffen, der (optional) auf eine Seite mit Stellenangeboten bzw. die Karriere-Seite des Veranstalters verweist.

## Fahrplan Feed 2021

Der aktuelle Fahrplan Feed (für das Jahr 2021) kann jederzeit unter der Adresse
https://backend.timetable.wueww.de/export/session.json abgerufen werden.

Über das Ende der Wuerzburg Web Week 2021 hinaus wird nicht gewährleistet, dass
unter der angegebenen Adresse die Fahrplandaten 2021 weiter abrufbar sind.


## Errata

Seit 2021 werden alle Links im Backend bei Erfassung validiert.  Da die Veranstalterkonten jedoch aus 2020 übernommen wurden, kann es sein, dass noch "unzulässige" Eingaben vorliegen, sofern der Veranstalter die Eingaben nicht aktiv selbst korrigiert.

Hinweise zum Feld `host.links.host`:

* es ist (dieses Jahr, leider) nicht garantiert, welches Format die Zeichenfolge hat
* vereinzelt beginnt der Inhalt _nicht_ mit "http://" oder "https://" (hier wird der API-Consumer angehalten die URL nicht z.B. fälschlicherweise als relative URL anzunehmen)
* vereinzelt werden mehrere URLs aufgelistet, diese sind durch mind. (!) ein Leerzeichen voneinander getrennt

Hinweise zum Feld `links.event`:

* vgl. Hinweise zum Feld `host.links.host`, seit 2021 wird das Feld jedoch als (absolute) URL oder E-Mail-Adresse validiert
* teilweise werden E-Mail-Adressen angegeben, diese werden _nicht_ mit einem Protokoll-Prefix `mailto:` ausgegeben
