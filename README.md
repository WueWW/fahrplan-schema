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


## Fahrplan Feed 2020

Der aktuelle Fahrplan Feed (für das Jahr 2020) kann jederzeit unter der Adresse
https://backend.timetable.wueww.de/export/session.json abgerufen werden.

Über das Ende der Wuerzburg Web Week 2020 hinaus wird nicht gewährleistet, dass
unter der angegebenen Adresse die Fahrplandaten 2020 weiter abrufbar sind.


## Errata

Hinweise zum Feld `host.links.host`:

* es ist (dieses Jahr, leider) nicht garantiert, welches Format die Zeichenfolge hat
* vereinzelt beginnt der Inhalt _nicht_ mit "http://" oder "https://" (hier wird der API-Consumer angehalten die URL nicht z.B. fälschlicherweise als relative URL anzunehmen)
* vereinzelt werden mehrere URLs aufgelistet, diese sind durch mind. (!) ein Leerzeichen voneinander getrennt


Hinweise zum Feld `links.event`:

* vgl. Hinweise zum Feld `host.links.host`
* vereinzelt finden sich hier Freitexte a la "Anmeldung bei ..."
* teilweise werden E-Mail-Adressen angegeben, diese werden _nicht_ mit einem Protokoll-Prefix `mailto:` ausgegeben
