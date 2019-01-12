***

[<< zurück](02_toc.md)

***

# 6. Anwendungsbeispiele
Cassandra und HBase sind die zwei großen spaltenorientierte Datenbanken die ihr Spalten alle seperat speichern. Es gibt eine Vielzahl von Open Source Datenbanken, auf die dies nicht zutrifft und deren Performance im BEreich der analytischen Datenarbeit schneller ist.
Wenn man Abfargen machen möchte,bei denen man ciht alle Felder eines Datensatzes abfragen möchte, sondern nur ein paar wenige bestimmte ist ee snciht sinnvoll siche alle betr4effenen ZEilen komplett zuholen. Hier benötigt man nur die Spalten, die die relevanten Informationen bereit halten und keine Aggregat-Tabellen zu andern Tabellen, also über mehrere Tabellen hinweg um zwei Inforamtionen von jedem Datensatz zurückzu geben, dartum können spaltenorientierte Datenbanken schneller performen.


## 6.1 Cassandra

Cassandra wurde 2007 von P. Malik und A. Lakshman entwickelt um eine performante Suche mit HIlfe von Indices zu ermöglichen, hier standen Skalierbarkeit und Robustheit im Vordergrund. Das Datenmodell von Cassandra entspricht dem Wide Column Store und ermöglicht nur einfache Anfragen anhand der Schlüssel der Daten und orientiert sich an Google Big Table. Um die Robustheit sicherzustellen werden Replikate von allen Daten angelegt. Zu Skalieren ist in Cassandra einfach, da jederzeit weitere Knoten zum System hinzugefügt oder eintfernt werden können. Zu erwähnen ist dass im Gegensatz zu anderen NoSQL Datenbanken Cassandra eine Art Rückskalierung bereitstellt. Hier kann mit Hilfe eines Managementtools ein Knoten entfernt werden und die für IHne bestimmten Informationen neu auf die verbleibenden Knoten verteilt werden.
Das Konsistenzmodell von Cassandra entspricht dem “eventual consistency” und kann in fünf verschiedenen Leveln eingestellt werden. Diese richten sich nach dem CAP Theorem, bei dem immer nur zwei der drei Eigenschaften(Consistency, Availability und Partition Tolerance) vollständig erfüllt sein können. Wird auf eines mehr Wert gelegt entfernt man sich zwangsläufig von einem anderen. Die fünf zur Verfügung stehenden LEvel sind: Zero, Any, One, Quorum und All und verschieben die Wichtigkeit der Konsistenz von Null (Zero) zu sehr wichtig (All), wobei die letzte Variante sehr teuer ist und zu Lasten der Verfügbarkeit (Availability) geht.
Es gibt fünf Hauptbestandteile im Cassandra Datenmodell, die eine sehr große Freiheit in der Datenablage ermöglichen. Wir gehen im folgenden Abschnitt kurz auf die einzelnen Hauptbestandteile ein.

Der Keyspace, welcher dem aus RDMS bekannten Datenbank entspricht, üblicherweise gibt es nur einen Keyspace obwohl auch mehrere möglich sind. In ihm werden Column Families gespeichert.

Die Column Families bestehen aus Rows in denen ein Schlüssel und als Elemente Columns oder Super Columns gespeichert werden. Eine Column Family wird immer in genau einem Keyspace gespeichert und besitzen kein vorgegebenes Schema an das sie sich halten müssen, was ein deutlicher Unterschied zu relationalen Datenbanken darstellt. Diese Struktur fordert das die Interpretation der Daten auf Applikationsebene ablaufen muss. Gespeichert werden sie meistens als Bytes unendlicher Größe und interpretiert als UTF-8 Zeichenketten oder 64bit Integerwerte.

Eine Row in einer Column Family setzt sich zusammen aus Columns und Super Column un stellt eine eindeutig identifizierbare Dateneinheit dar.

Um komplexere Datenstrukturen abbilden zu können gibt es die Super Columns, dies sind Columns deren Werte wieder Columns beinhalten.

Der Fünfte Bestandteil in Cassandra ist die kleinste Informationseinheit, die Column. Sie besteht meistens aus dem Tupel: Name, Wert und Timestamp.

Cassandra wird von Netflix, Twitter und Digg genutzt, sowie bis 2010 von Facebook, die nun zu HBase gewechselt sind, eine Technologie die im nächsten Abschnitt vorgestellt wird.

## 6.2 HBase


Innerhalb eines Hadoop-Clusters kann man mit HBase sehr große Datenmengen verwalten. Sie basiert, ähnlich wie Cassandra, auf einer freien Implementierung von Google BigTable und ist eine skalierbare Datenbank. Als 2010 Facebook das Nachrichtensystem geändert hat, war HBase passend, da es gut ist für Daten die zwar oft ergänzt werden, aber nicht oft verändert.

In HBase werden Suchindices, Textinhalte und Metadaten gespeichert und verwaltet, da HBAse MEtadaten auf dem NameNode specihert und Datenblöcke auf dem DataNode gab es aus Sicht von Facebook den Nachteil dass bei Ausfall des NameNodes der Cluster nciht mehr erreichbar wäre. Facebook hat hier viele Weiterentwicklungen vorangetrieben.


## 6.3 Weitere Beispiele

C-Store / Vertica

C-Store, und dessen Erweiterung Vertica, ist eine der wenigen echten physischen Column Stores, da die meisten Implementierungen dies nur im Arbeitsspeicher realisieren.
Es gibt eine vorgelagerte schreiboptimierte Datenbank in der Änderungen gespeichert werden und diese werden dann in regelmäßigen Abständen in den komprimierten Datenbestand synchronisiert.






Text wird hier einfach so geschreiben.
[Linktext](Link z.B. 01_toc.md).



***

[<< Datenstruktur >>](07-3_normalized_data_structure.md) | [Nutzen für Datawarehaus und BI >>](09_data_warehouse_BI.md)

***