***

[<< zurück](02_toc.md)

***

# 4. Funktionsweise

In diesem Kapitel wird die Funktionsweise von spaltenorientierten Datenbanken erklärt. Dabei wird auf das Datenmodell, die technische Aspekte, die Methoden der Kompression und der Performance eingegangen.


# 4.1 Datenmodell

Das Datenmodell basiert auf dem Schema des Keyspace. Ein Keyspace beinhaltet alle Column Families, wie in der Abbildung 1. zu sehen ist. Die Menge an Keyspaces bildet das spaltenorientierte Datenbanksystem. Ein Keyspace lässt sich mit einer Tabelle in einer relationalen Datenbank vergleichen.

Eine Column Family besteht wiederum aus mehreren Zeilen. Je nach System wird dieses Konstrukt aus mehreren Zeilen anders benannt. Bei Googles Bigtable werden diese als Tablets bezeichnet. 


.............


***

[<< Grundlagen und Begriffe](05_basics.md) | [Technischen Aspekte >>](06-2_technical_aspects.md)

***