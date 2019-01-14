**

[<< zurück](02_toc.md)

***

# 8. Fazit

Zusammenfassend kann man sagen, dass die Entscheidung ob spaltenorientierte Datenbank ode rzeilenorientierte Datenbank je nach UNternehmensumfeld entschieden werden kann.
Grundsätzlich lässt sich sagen, dass zeilenorientierte Datenbanken in der Regel dafür gemacht sind schnell bestimmte Daten abzurufen und Transaktionen darauf auszuführen, also schreibend auf die Datenbank zuzugreifen.
Spaltenorientierte Datenbanken wurden entwickelt, um schnell und gezielt benötigte Daten für Analysen und Statistiken zu erheben und so aus einer großen Menge von Datensätzen schnell Informationen zu gewinnen.

Wenn wir beispielsweise nicht wissen wollen, welche Haustiere ein bestimmter User hat, sondern welches Haustier die Deutschen am häufigsten haben, dann fragen wir nur die Information Haustiere ab und nicht das Tupel, welches alle Informationen zu einem bestimmten User darstellt, nur um dann zu schauen was in der Zelle “Haustiere” steht. Der nächste Schritt könnte sein spaltenorientierte Datenbanken so zu optimieren, dass sie auch bei Schreiboperationen mit den zeilenorientierten Datenbanken in der Performanz mithalten können.




***

[<< Data Warehousing und Business Intelligence](09_data_warehouse.md) | [Literaturverzeichnis >>](references.md)

***