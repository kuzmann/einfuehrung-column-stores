***

[<< zurück](02_toc.md)

***

# 7. Nutzen im Data Warehousing
Eine zentrales Datenbanksystem in dem themenorientierte Daten aus verschiedenen Datenquellen gesammelt und langfristig gesichert werden nennt man Datawarehouse oder auch Datenlager. Die Daten werden in Zeitintervallen periodisch ergänzt um aktuelle Daten, jedoch werden die bestehenden Daten nicht verändert.
Die Datenquellen bilden meiste operative Systeme, deren Daten für die spätere Entscheidungsfindung in Unternehmen gespeichert werden. [ADW-BI 05 , S.3 ff]

Data Warehouses bieten den Vorteil das es möglich ist eine Aggregation aus den Daten verschiedener Datenquellen zu bilden und so einen Gesamtblick zu erhalten. Dabei können die Daten auch aus einem operativen zeilenorientierten DBMS eines Unternehmens kommen, welche in die Kategorie Online Transaction Processing (OLTP) fallen. In den zeilenorientierten DBMS werden die Tupel einer Tabelle nacheinander gespeichert, und nicht denormalisiert und komprimiert wie in Abschnitt 4.1 Datenmodell beschrieben.

Die hier vorliegenden heterogenen Daten werden von nachgelagerten Analysesystemen genutzt, die dann wiederum spezifische erstellte Auszüge aus den Daten (Data Marts), bieten um beispielsweise betriebliche Kennzahlen zu ermitteln. Das Data Warehousing bezeichnet alle Prozesse zur Datenbeschaffung, Verwaltung, Sicherung und Bereitstellung von Daten.[BDI 18]
Ein Data Warehouse basiert zwar in der Regel auf relationalen Datenbanken, bei großen Datenmengen nutzt man zur hierarchischen Strukturierung der Daten eine OLAP-Datenbank (Online Analytical Processing).
Heutzutage spielt In vielen Unternehmen Online Analytical Processing (OLAP) eine wachsende Rolle und durch die Art der Datenspeicherung als Tupel einer Tabelle der traditionellen zeilenorientierten Datenbanken werden komplexe analytische Anfragen immer schwerer bewältigt. In

Durch die Spaltenweise Speicherung kann schneller lesend gezielt auf große, bestimmte Datenmengen zugegriffen werden, ohne irrelevante Informationen mit abrufen zu müssen. In OLAP Query Performance in Column-Orieted Databases wird erwähnt:
“ In contrast to row oriented databases, which use “once-a-tuple” pipeline processing, column-oriented databases use “once-a-column” style processing, which is aimed at better I/O and cache efficiency”

Es gibt vier Arten von OLAP Servern, die hier nur genannt werden sollen: Relational OLAP, multidimensional OLAP, Hybrid OLAP and specialized SQL Servers.
Der HOLAP stellt eine Verbindung von ROLAP und MOLAP dar, er skaliert besser als der ROLAP und er ist schneller als der MOLAP, damit erlaubt er es viele detailierte Informationen zu speichern, wobei die Aggregationen hier in einem separaten MOLAP liegen.


## 7.1 Nutzung in Business Intelligence
Die erwähnten Vorteile für eine spaltenoreitnierte Datenspeicherung im Datawarehousing Umfeld wirken sich auch auf die statistischen Analysen der Business Intelligence aus.
Der Analyst Howard Gardner definiert Business Intelligence als einen Prozess, der Daten in Informationen transformiert und diese wiederum durch die Anwendung von Erfahrungen in Wissen. Dieser klassische Ansatz umfasst folglich alle Prozesse und Systeme, mit denen sich Markt-, Wettbewerbs- und Unternehmensdaten systematisch analysieren lassen.

In [BDI-BI 18] wird eine weitere Definition aus IT-basierten und unternehmensspezifischen Sicht beschrieben, nach der Business Intelligence das entscheidungsorientierte Sammeln, Aufbereiten und Darstellen von geschäftsrelevanten Informationen umfasst. Die gesammelten Daten werden über eine Dashboard visualisiert. Nach dieser Definition ist das Data Warehouse ein Teil des Gebiets der Business Intelligence.




***

[<< Anwendungsbeispiele >>](08_use_cases.md) | [Nutzen für Datawarehaus und BI >>](09_data_warehouse.md)

***