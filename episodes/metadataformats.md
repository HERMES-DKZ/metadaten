---
title: "Speichern und Verarbeiten von Metadaten"
teaching: 20
exercises: 10
---
::: questions 

- In welchen Formaten können Daten und Metadaten strukturiert gespeichert werden?
- Was ist eine CSV-Datei und wie ist ihr Inhalt aufgebaut?

:::

::: objectives  

Nach Beendigung dieser Episode sollten die Teilnehmende in der Lage sein

- die Grundstruktur eines CSV-Formats zur Speicherung und Verarbeitung von Metadaten zu beschreiben, 
- eine einfache CSV-Datei zu öffnen und zu untersuchen,
- die wichtigsten Unterschiede zwischen einer CSV-Datei und einer Excel-Datei zu bennen.  
:::


## Einführung in Dateiformate für Metadatenspeicherung und -verarbeitung

::: challenge

### Frage 
Kennen Sie Formate, in denen man Daten strukturiert speichern kann? 

::: solution

### Antwort
Eine einfache Möglichkeit stellen die Tabellenblätter in einem Tabellenkalkulationsprogramm dar. 

:::
:::

Um Metadaten zu speichern und sie in anderen Kontexten nutzbar zu machen, sind geeignete Formate erforderlich. Die gängigsten Dateiformate für die Speicherung von Metadaten sind XML und JSON. Viele Daten werden auch in dem bekannteren CSV-Format gespeichert, wie ein Beispiel aus der Praxis später zeigen wird.

#### Interoperabilität


Der Vorteil der Verwendung eines solchen Formats ist die Interoperabilität der Daten. Das bedeutet, dass die Daten von einer Person erfasst und gespeichert werden, aber an anderer Stelle geöffnet, verarbeitet oder mit anderen Daten zusammengeführt werden können.

::: challenge

### Aufgabe

Öffnen Sie die Dateien [artworksShort.csv](https://github.com/HERMES-DKZ/metadata_lesson/blob/main/episodes/data/artworksShort.csv) und [artworksShort.xslx](https://github.com/HERMES-DKZ/metadata_lesson/blob/main/episodes/data/artworksShort.xlsx) in einem Tabellenkalkulationsprogramm Ihrer Wahl. 

- Was fällt Ihnen auf?    
- In welcher Form liegen die Daten vor?    
- Welche Vorteile hat diese Art der Erfassung von Daten?   
- Warum sind diese Daten interoperabel?
    
::: solution

### Lösung

- Beim Öffnen der CSV-Datei werden mehrere Parameter abgefragt. 
- Einige Daten in der XSLX-Datei sind mit Farben sowie fett- und kursivgedrucktem Text formatiert. Dies ist in der CSV-Datei nicht zu finden. 
- Die Daten liegen in tabellarischer Form vor.    
- Die Daten sind in einzelnen Zellen erfasst.     
- Die Inhalte sind durch Überschriften in der ersten Zeile kategorisiert.   
- Die Daten liegen in einem digitalen Dateiformat vor, das bearbeitet und weitergegeben werden kann.
    
:::
:::


::: instructor

Eine mögliche Quelle für Fehler und Probleme, die auftreten können und diskutiert werden sollten, sind die Trennzeichen. Es wurde bewusst ein Titel mit Komma in die Datei aufgenommen, damit dieser Titel über mehrere Felder hinweg angezeigt werden kann, wenn unterschiedliche Trennzeichen beim Öffnen der Datei gewählt werden.
:::


## Das CSV-Format  

Das CSV-Format (comma-separated values) in diesem Beispiel wird normalerweise als Tabelle in einem Tabellenkalkulationsprogramm wie Excel geöffnet, damit es von Menschen strukturiert gelesen werden kann. Wenn Sie das Format in einem Texteditor öffnen, erkennen Sie die Struktur der Datei:  

```
ID;artist;title;date
1;Salvador Dalí;The persistence of memory;1931
2;Walker Evans;Allie Mae Burroughs, Wife of a Cotton Sharecropper, Hale County, Alabama;1936
3;Frida Kahlo;Roots;1943
4;Käthe Kollwitz;Mother with Child over her Shoulder;Before 1917
5;Berthe Morisot;The psyche mirror;1876
1;Georgia O’Keeffe;Sky above clouds IV;1965
3;Banksy;Girl with Ballon;2002
```

In dem Moment, in dem Sie die CSV-Datei in einem Tabellenkalkulationsprogramm geöffnet haben, wurden einige Parameter abgefragt, bevor Sie die Inhalte angezeigt bekommen haben. Hier ist der Grund dafür:  

Die Daten in dieser speziellen CSV-Datei sind durch Semikolons – die so genannten Trennzeichen oder *delimiter* – getrennt. Die meisten Dateien, die Trennzeichen jeglicher Art nutzen, erhalten oft die Erweiterung *.csv*, auch wenn das Trennzeichen kein Komma ist, wie das vorliegende Beispiel zeigt. In vielen Dateien finden Sie den Inhalt der Datenfelder in Anführungszeichen eingeschlossen, wenn Sie die Datei in einem Editor öffnen. Dies sieht man in einem Tabellenprogramm nicht. Die einzelenen Datensätze stehen meist in einer Zeile und werden durch einen Zeilenumbruch getrennt. Oft definiert die erste Zeile die Spaltenüberschriften. Werden diese Parameter beim Öffnen der Datei korrekt eingegeben, werden die Daten in die entsprechenden Felder des Tabellenkalkulationspogramms übertragen.  

## Unterschied zwischen CSV- und XSLX-Dateien


Mit einem XSLX-Format können Sie Daten in mehreren Tabellenblättern, die in einer einzigen Datei gespeichert sind, speichern. Die Daten sind in Zellen organisiert, die in Zeilen und Spalten angeordnet sind. Sowohl die Zellen als auch die darin enthaltenen Datenwerte können formatiert werden, einschließlich Schriftarten, Farben und Rahmen. Die Daten können mit integrierten Funktionen bearbeitet werden, z. B. für Berechnungen oder Analysen. Es ist auch möglich, die analysierten Daten in Tabellenkalkulationsprogrammen wie Excel zu visualisieren.

Einer der Nachteile ist die begrenzte Anzahl von Zeilen und Spalten - zum Beispiel 1.048.576 Zeilen und 16.385 Spalten pro Arbeitsblatt, abhängig von der Softwareversion. Auch andere Funktionen können von der Softwareversion abhängen. Ältere Tabellen werden in der neuesten Version aufgrund mangelnder Kompatibilität der Funktionen möglicherweise nicht immer korrekt angezeigt.

Das CSV-Format (comma-separated values) speichert tabellarische Daten in einfachem Text, der in Tabellenkalkulationsprogrammen geöffnet werden kann. Es ist daher sowohl von Menschen als auch von Maschinen lesbar. Es wird immer nur eine Tabelle in einer einzigen Datei gespeichert. In diesem Textformat können jedoch mehr Daten in einer Datei gespeichert werden, was es besonders effizient macht. Zudem werden keine überflüssigen Daten wie Formatierungsdaten gespeichert. Daher eignet es sich für die Speicherung und den Austausch von größeren Datenmengen zwischen Anwendungen oder Datenbanken.

Einer der Nachteile ist, dass in diesem Format nur einfache tabellarische Daten gespeichert werden können, nicht aber Daten mit komplexeren Strukturen.


#### Datenorganisation

Bei der Erfassung von Daten in Tabellen gibt es eine Reihe von Aspekten zu beachten, damit die Daten korrekt verarbeitet werden können. Neben den oben erwähnten kommagetrennten Feldern, die Probleme verursachen können, gibt es noch viele andere Probleme. Datumsangaben oder Namen sind eine große Fehlerquelle. Unterschiedliche Schreibweisen können zu Fehlinterpretationen führen. Wie interpretieren Sie zum Beispiel das Datum 25-01-11, wenn es in einem einzigen Feld steht? Oder: Welcher Teil des Namens einer Person ist der Vorname und welcher Teil ist der Nachname?

Daher ist ein wichtiger Teil bei der Erfassung von Metadaten die Annotierung, d.g. die korrekte Auszeichung der Daten. Nehmen Sie *Walker Evans* als Beispiel: Wenn Sie ihn als „Künstler“ oder „Fotograf“ kennzeichnen, können die Benutzer die Rolle im Kontext des Datensatzes verstehen. 

Wenn Sie Datumsangaben in einer Tabelle erfassen, kann es sich lohnen, Jahr, Monat und Tag in separate Felder aufzuteilen, um das oben beschriebene Problem zu vermeiden. 

::: callout

Sie finden weitere Informationen zur Organisation von Daten in der Lektion [Data Organization in Spreadsheets for Social Scientists](https://datacarpentry.github.io/spreadsheets-socialsci/)

:::  

Es gibt bestimmte Datenformate, die einige der hier genannten Probleme lösen. So zum Beispiel durch die Nutzung einer Auszeichnungssprache (Markup Language). Auszeichnungssprachen werden zur Strukturierung und Formatierung von Text und Daten in maschinenlesbarer Form verwendet. Sie beruhen auf einer Metasprache namens SGML (Standard Generalized Markup Language). SGML ist ein Standard für Auszeichnungssprachen. Sie legt fest, wie die Syntax (Regeln) für Elemente, Attribute und die Dokumentstruktur in einer Auszeichnungssprache zu definieren ist. In der Episode zu XML erfahren Sie mehr dazu. 

::: keypoints

* Wenn Sie die Daten und die Tabelle formatieren oder Daten mit der Software analysieren wollen, verwenden Sie das XSLX-Format zum Speichern, Formatieren und Analysieren der Daten.    
* Wenn Sie die Daten nicht analysieren oder visualisieren müssen oder sehr große Datenmengen haben, verwenden Sie ein Format wie CSV, um die Daten zu speichern oder weiterzugeben.    
* Es ist hilfreich die Daten bei der Erfassung zu annotieren, zum Beispiel durch Überschriften zu kennzeichnen.   
* Seien Sie sich der Probleme bewusst, die entstehen können, wenn Sie zum Beispiel Datums- oder Namensangaben erfassen und machen Sie sich vorab Gedanken, welche Form für Ihre Zwecke geeignet sein könnte.
:::
