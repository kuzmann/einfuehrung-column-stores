***

[<< zurück](02_toc.md)

***

# 5.3. Normalisierte Datenstruktur
Spaltenorientierte Datenbanken bevorzugen eine denormalisierte Datenstruktur. Wenn wir zum Beispiel in einer zeilenorientierten Datenbank ein Kundensystem abbilden wollen, haben wir eine Tabelle für alle Kunden die eine bestimmte Form von Abonnement haben. Es gibt in diesem Beipsuel die Abonnements “Premium, Student, Test”. Des Weiteren gibt es eine Tabelle mit den registrierten Kundendatensätzen, eine Tabelle mit der Auflistung welcher Kunder welches Abo seit wann hat und wie lang es läuft und dann vielleicht noch eine Tabelle, welche Einkäufe zusätzlich zum Abonnement gemacht wurden.

=> (HIER WÄRE EIN BILD MIT DEM BEIPSIEL SEHR GUT)

In einer spaltenorientierten Datenbank könnte eine einzige Tabelle die Informationen mit den Kundendaten und den Einkäufen abbilden.
Die Normalisierung der Daten macht es in zeilenorientierten Datenbanken schneller Daten zu aktualisieren, da man dann beim Aktualisieren von Kundendaten nur an einer Stelle ändern muss und alle anderen Transaktionen beziehen sich die Aktualisierung aus der einen Zelle. In der spaltenorientierten Datenbank würde man die Kundendaten zusammen mit den zusätzlichen Einkäufen speichern und müsste dann um beispielsweise die Adresse zu aktualisieren, an mehreren Stellen die Aktualisierung vornehmen.


Man kann auch in einer zeilenorientierten Datenbank Datenanalysen machen. Diese Analyse läuft im Zweifel nur langsamer, als sie in einer spaltenorientierten Datenbank brauchen.  
Wenn nur einige wenige Felder einer Wide Table Datenstruktur gebraucht werden sind Column Stores das Richtige. Sie sollten jedoch nicht für normale Online Transactional Processing (OLTP) verwendet werden. Will man etwas wie `SELECT * FROM TABLE` machen, dann ist eine spaltenorientierte Datenbank, bei der alle Tabellenspalten in separate Dateien gespeichert werden, nicht geeignet, da man auf unzählige Dateien zugreifen muss, um die Abfrage auszuführen. Für Dienste die Online Analytical Processing (OLAP) Anwendungen unterstützen sollen, bieten Column Stores in Verbindung mit den in Abschnitt 4.4 beschriebenen Kompressionsverfahren eine hohe Performancesteigerung. In (FEHLT HIER  INHALTE?) [MG15]

Zeilenorientierte Datenbanken sind in der Regel dafür gemacht schnell bestimmte Daten abzurufen und Transaktionen darauf auszuführen, also schreibend auf die Datenbank zuzugreifen. Spaltenorientierte Datenbank wurden entwickelt, um schnell analytische Statistiken zu erheben und auf einer großen Menge von spezifischen Daten zu einer Information auszuwerten.

Wenn wir beispielsweise nicht wissen wollen, welche Haustiere ein bestimmter User hat, sondern welches Haustier die Deutschen am häufigsten haben, dann fragen wir nur die Information Haustiere ab und nicht das Tupel, welches alle Informationen zu einem bestimmten User darstellt, nur um dann zu schauen was in der Zelle “Haustiere” steht.


***

[<< Datenstruktur](07-3_normalized_data-structure.md) | [Anwendungsbeispiele >>](08_use_cases.md)

***