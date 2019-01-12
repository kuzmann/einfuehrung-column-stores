***

[<< zurück](02_toc.md)

***

## 5.1 Schreibende Datenbankzugriffe

Es gibt verschiedene Arten von Intentionen schreibend auf eine Datenbank zu zugreifen. Neben dem Einfügen komplett neuer Daten, kann es auch nötig sein einzelne Werte zu aktualisieren oder gar die Tabellenstruktur zu verändern.

### 5.1.1. Einfügen eines neuen Datensatzes
Einen neuen Datensatz einzufügen Ist im Row Store einfacher, da hier nur ein neues Tupel an die Tabelle an gehangen werden muss, in einer spaltenorientierten Datenbank muss man wahrscheinlich viele Dateien öffnen und schreiben. Hier werden ind er Realität oft ganze Stapel (Bulk Loads) auf einmal verarbeitet.

### 5.1.2. Update eines Wertes
Um einen Wert zu aktualisieren muss man in einer zeilenorientierten Datenbank nur den Wert an einer Stelle ändern. In einer spaltenorientierten Datenbank muss man die verschiedenen Dateien öffnen, suchen und dann den entsprechenden Wert überschreiben. Dies lässt sich ebenfalls durch eine Stapelverarbeitung eines UPDATE optimieren.

### 5.1.3. Update einer Spalte
Um in einer zeilenorientierten Datenbank eine Spalte zu ändern muss man diese Suchen und in jedem Tupel der Tabelle ändern, hier bietet die spaltenorientierte Datenbank den Vorteil das nur die einzelne Datei der betroffenen Spalte aktualisiert werden muss.

### 5.1.4. Änderung der Tabellenstruktur
In Row Store ist dies nur aufwendig möglich, in der spaltenorientierten Datenbank wird einfach eine neue Datei für die hinzukommende Spalte angelegt, wobei diese auch nicht an eine feste Objektart gebunden ist.


## 5.2. Lesender Zugriff
Um transaktionale Operationen auszuführen oder einzelne komplette Datensatzes zu lesen sind spaltenorientierte Datenbanken nicht geeignet, da hier in jeder Datei gesucht werden muss. Hier bietet die zeilenorientierte Datenbank den Vorteil, dass mit einem Zugriff das gesamte Tupel ausgelesen werden kann, wenn ein Index vorhanden ist. Sollte der Index nicht vorhanden sein muss hier die gesamte Tabelle durchsucht werden. Auch die Anzahl an Raw Bytes, die benötigt werden sind im Vergleich zur zeilenorientierten Datenbanken ziemlich hoch, daher liegen die Daten, wie in “Kapitel 4 Datenmodell” bereits erwähnt komprimiert auf Platte vor.

Beim Auslesen vieler Datensätze(Aggregation), wobei nur wenig Spalten relevant sind werden in einer spaltenorientierten Datenbank nur die entsprechenden Dateien gelesen, wobei in zeilen orientierten Datenbanken die gesamte Tabelle gelesen werden muss.



***

[<< Row Store vs Column Store >>](07-1_row-colum-store.md) | [Datenstruktur >>](07-3_normalized_data_structure.md)

***