***

[<< zurück](02_toc.md)

***

# 5. Row Store vs Column Store

In diesem Abschnitt sollen einige Unterschiede von zeilenorientierten Datenbanken und spaltenorientierten Datenbanken
aufgezeigt werden. Dafür betrachten wir die verschiedenen Anwendungsfälle von schreibenden und lesenden Datenbankzugriffen und die Datenstrukturen von beiden Modellen.

Im Allgemeinen eignen sich Row Stores,oder auch zeilenorientierte Datenbanken gut zum Speichern von Transaktionen,
wobei spaltenorientierte Datenbanken eher geeignet sind wenn man große Datenmengen schnell lesen möchte, dies liegt daran,
dass Festplatten die Informationen nacheinander schreiben beim Speichern. So werden beim Speichern von zeilenbasierten
Datenbanken immer erst das gesamte Tupel geschrieben und dann die nächste Zeile.
Beim spaltenorientierten Speichern stehend ie auf der Platte beieinander, so können für Analysen zusammengehöroge Daten schneller
gelesen werden.

Im Folgenden sind die typischen Arten von Datenbankzugriffen näher betrachten in Hinblick auf die Performance.



Text wird hier einfach so geschreiben.
[Linktext](Link z.B. 01_toc.md).



***

[<< Performance >>](06-5_performance.md) | [Datenbankzugriffe >>](07-2_db-access.md)

***