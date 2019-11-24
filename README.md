# WueWW Fahrplan Schema

... der Fahrplan der [Würzburg Web Week](https://wueww.de/) in maschinenlesbarer Form.

Ziel dieses Projekts ist es, den Fahrplan als *open data* zur Verfügung zu stellen.
Zunächst einfach mal so, ... natürlich verbunden mit der Hoffnung, dass andere
die Daten für kreative, eigene Projekte nutzen.

Selbstverständlich sind die Daten
[CC0](https://creativecommons.org/publicdomain/zero/1.0/deed.de) lizenziert --
du kannst also einfach alles damit machen :-)

In diesem Repository findest du lediglich die JSON-Schema Datei:
[fahrplan.schema.json](https://wueww.github.io/fahrplan-schema/fahrplan.schema.json)

Dieses Schema weicht in Details vom 2019-er Schema ab:
 * es gibt jetzt numerische Schlüssel, das Feld heißt nun `id` (statt bisher `key`)
 * unter `host.links` finden sich nun alle zum Organisator bekannten Links
 * die Zeichenfolge `location.name` enthält nun ausschließlich den Namen der Location,
   die konkrete Adresse findet sich in separaten Feldern unterhalb von `location`
 * die Angabe einer `location` ist nun Pflicht
