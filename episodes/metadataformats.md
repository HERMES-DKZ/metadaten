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

:: challenge

### Frage 
Kennen Sie Formate in denen man Daten strukturiert speichern kann? 

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

Öffnen Sie die Dateien [artworksShort.csv file](https://github.com/HERMES-DKZ/metadata_lesson/blob/main/episodes/data/artworksShort.csv) und [artworksShort.xslx file](https://github.com/HERMES-DKZ/metadata_lesson/blob/main/episodes/data/artworksShort.xlsx) in einem Tabellenkalkulationsprogramm Ihrer Wahl. 

- Was fällt Ihnen auf?    
- In welcher Form liegen die Daten vor?    
- Welche Vorteile hat diese Art der Erfassung von Daten?   
- Warum sind diese Daten interoperabel?
    
::: solution

### Lösung

- Beim Öffnen der CSV-Datei werden mehrere Parameter abgefragt. 
- Einige Daten in der XSLX-Datei sind mit Farben sowie fett- und kursivgedrucktem Text formatiert. Dies ist in der CSV-Datei nicht zu finden. 
- Die Daten liegen in tabellarischer Form vor.    
- Die Daten sind in einzelnen Feldern erfasst.     
- Die Inhalte sind durch Überschriften in der ersten Zeile benannt.   
- Die Daten liegen in einem digitalen Dateiformat vor, das bearbeitet und weitergegeben werden kann.
    
:::
:::

::: instructor
Eine mögliche Quelle für Fehler und Probleme, die auftreten können und diskutiert werden sollten, sind die Trennzeichen. Es wurde bewusst ein Titel mit Komma in die Datei aufgenommen, damit dieser Titel über mehrere Felder hinweg angezeigt werden kann, wenn unterschiedliche Trennzeichen gewählt werden.
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

Die Daten in dieser speziellen CSV-Datei sind durch Semikolons – die so genannten Trennzeichen oder *delimiter* – getrennt. Die meisten Dateien, die Trennzeichen jeglicher Art nutzen, erhalten oft die Erweiterung *.csv*, auch wenn das Trennzeichen kein Komma ist, wie das vorliegende Beispiel zeigt. In vielen Dateien finden Sie den Inhalt der Datenfelder in Anführungszeichen eingeschlossen, wenn Sie die Datei in einem Editor öffnen. Dies sieht man in einem Tabellenprogramm nicht. Die einzelenen Datensätze stehen meist in einer Zeile und werden durch einen Zeilenumbruch getrennt. Oft definiert die erste Zeile die Spaltenüberschriften. Werden diese Parameter beim Öffnen der Datei korrekt eingegeben, werden die Daten in die entsprechenden Felder der Tabellenkalkulation übertragen.

## Unterschied zioschen CSV- und XSLX-Dateien



An XSLS format allows you to store, format and apply formulas to data in multiple spreadsheets that are stored in a single file. Data is organised into cells, which are arranged in rows and columns. Both the cells and the data values within them can be formatted, including fonts, colours and borders. The data can be manipulated using built-in functions, e.g. for calculation or analysis. It is also possible to visualise the analysed data in spreadsheet software such as Excel. 

One of the disadvantages is the limited number of rows and columns - for example 1,048,576 rows and 16,385 columns per worksheet depending on your software version. Other features can depend on the software version as well. Older tables may not always display correctly with the latest version due to a lack of feature compatibility.  

The CSV (comma-separated values) format stores tabular data in plain text that can be opened in spreadsheet software. It is therefore readable by both humans and machines. There is always only one table stored in a single file. However, the plain text format allows more data to be stored in a file, making it particularly efficient as it does not store superfluous data such as formatting data. It is therefore suitable for storing and exchanging data between applications or databases.  

One of its disadvantages is that it can only store simple tabular data, and not data with more complex structures.


#### Data Organization



When entering data into spreadsheets, there are a number of issues that need to be considered to ensure that the data can be processed correctly. In addition to the comma-separated fields mentioned above, which can cause problems, there are many other issues. Dates or names are a major source of error. Different spellings can lead to misinterpretation. For example, how do you interpret the date 25-01-11 if it is written in a single field? Or: Which part of a person's name is the first name and which part is the surname?

::: callout

### Find out more on Data Organization

For further reading see [Data Organization in Spreadsheets for Social Scientists](https://datacarpentry.github.io/spreadsheets-socialsci/)

:::


An important part of recording metadata is annotating the data. Take *Walker Evans* as an example: Annotating - i.e. tagging - him as "artist" or "photographer" allows users to understand the role of this entry in the context of the dataset. In the spreadsheet example, "artist" is one of the column headings. 

If you are using a spreadsheet to annotate dates, it may be worth splitting the year, month and day into separate fields to avoid the problem described above. Later you will learn about other ways to display dates correctly.   

There are certain data formats that solve some of the problems mentioned here - for example data created with a markup language. Markup languages are used to structure and format text and data in a machine-readable way. They are based on a meta-language called SGML. SGML is a standard for markup languages. It specifies how to define the syntax (rules) for elements, attributes, and document structure in a markup language. 

::: keypoints

* If you need to format the data and spreadsheet, use the XSLX format to store and analyse the data.  
* If you don't need to analyse or visualise the data, use an interoperable format such as CSV to store or share the data.  
* It is helpful to annotate the data - for example with headers.  
* Be aware of the problems that can occur when annotating data and metadata with, for example, dates or names.
