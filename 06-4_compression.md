***

[<< zurück](02_toc.md)

***

# 4.4 Kompressionstechniken

Wie im Kapitel 4.3 beschrieben eignet die Struktur von spaltenorientierten Datenbanken gut für Kompression. Die Kompression wird immer wichtiger in der heutigen Informatik. Bei der Kompression muss besonders darauf geachtet werden, dass keine Daten beim Kompressionsvorgang und der Dekompression verloren gehen. Es dürfen nur verlustfreie Kompressionstechniken eingesetzt werden. Die Vorteile von Kompression ist die Reduzierung des Speicherplatzes und somit die Erhöhung des Datendurchsatzes, die Netto-Datenmenge pro Spalte, damit mehr Daten im Datenbankpuffer Platz haben. 

In diesem Kapitel werden wir ein paar dieser Kompressionstechniken vorstellen.



## 4.4.1 Wörterbuchkompression

Die Wörterbuchkompression ist auch unter dem englischen Namen Dictionary Encoding bekannt. Bei diesem Verfahren werden Wörtern oder Volltext kurz binäre Codes zugewiesen. Statt der Wörter werde die Codes in die Datenbank gespeichert. Für die Übersetzung der Code zurück in die Textform wird eine Art Wörterbuchdatei erstellt. Dieses Verfahren eignet sich sehr gut bei langen und mehrfach vorkommenden Werten bzw. Wörtern. Die Abbildung 4. zeigt ein Beispiel einer Wörterbuchkompression bei der Speicherung von deutschen, meist sehr langen Bundesländernamen. [He12] [MG15]

<img src="files/Woerterbuchkompression.png" alt="Beispiel einer Wörterbuchkompression" style="width:570px;height:180px;">
Abbildung 4: Beispiel einer Wörterbuchkompression

## 4.4.2 Lauflängencodierung

Die Lauflängencodierung, im englischen Run Length Encoding, ist ein häufiges Verfahren bei Werten die mit weniger Zeichen oder Länger und häufiger Nennung des gleichen Wertes. Durch eine Sortierung werden die gleichen Werte in eine Reihenfolge gebracht. Statt die gesamte Sequenz wird nur ein Datensatz mit der aufeinanderfolgender Häufigkeit ihrer Wiederholung (Anzahl des gleichen Datensatzes) gespeichert. Ein Beispiel solcher Codierung ist in der Abbildung 5. zu sehen. [OH12] [MG15]

<img src="files/Lauflangencosierung.png" alt="Beispiel einer Lauflängencodierung" style="width:570px;height:180px;">
Abbildung 5: Beispiel einer Lauflängencodierung

## 4.4.3. Differenzspeicherung

Bei Sequenzen von steigender oder fallenden ganzahligen Werte kann die Differenzspeicherung zum Einsatz kommen. Bei diesem Verfahren werden statt den Werten die Differenz vom Vorgänger abgespeichert. Damit die Differenz klein bleibt kann man die Spaltenwerte vorab sortieren. Ein guter Einsatz dieser Technik ist bei der Abspeicherung von Postleitzahlen, wie in der Abbildung 6. zusehen. [OH12] [MG15]

<img src="files/Differenzspeicherung.png" alt="Beispiel einer Differenzspeicherung" style="width:570px;height:180px;">
Abbildung 6: Beispiel einer Differenzspeicherung


***

[<< Spaltenorientierte Speicherung ](06-3_storage.md) | [Performance >>](06-5_performance.md)

***