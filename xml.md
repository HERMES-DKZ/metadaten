---
title: "XML"
teaching: 25
exercises: 15
---
::: questions 

- Was ist XML?
- Welche Elemente beinhaltet XML?  
- Wie notiert man Daten in XML?

:::

::: objectives
Nach Beendigung dieser Episode sollten Teilnehmende in der Lage sein 

- das XML-Format für die Speicherung und Verarbeitung von Metadaten beschreiben,
- Syntaxregeln für eine wohlgeformte XML-Datei zu benennen,  
- die Struktur einer einfachen XML-Datei zu untersuchen, 
- extrahierte Metadaten in ein einfaches XML-Format zu schreiben.

:::

Eines der am häufigsten verwendeten Dateiformate im Kulturbereich ist XML (eXtensible Markup Language). Es wird zur Beschreibung, Strukturierung, Speicherung und Übertragung von Daten verwendet. XML bezieht sich sowohl auf das Dateiformat als auch auf die Syntax, in der die Daten aufgezeichnet werden: die Auszeichnungssprache. Durch die Markierung des Textes mit *Tags* können Daten und Metadaten in einem einzigen Dokument kombiniert werden.

## XML Elemente

Ein XML-Dokument enthält XML-Elemente zur Strukturierung der Daten. Sie werden mit Hilfe von Tags in spitzen Klammern gebildet und sind in einen öffnenden und einen schließenden Tag unterteilt. Die schließende Tag ist durch einen führenden Schrägstrich gekennzeichnet. Dazwischen befindet sich der Inhalt.  

```xml
<tag>element</tag>
```  

Die Tags erhalten einen Namen, der den Inhalt beschreibt:

```xml
<photographer>Walker Evans</photographer> 
<name>Walker Evans</name>
<artist>Walker Evans</artist>
```

Diese Struktur ist Ihnen vielleicht bekannt. Die Sprache HTML, die für Webseiten verwendet wird, hat eine ähnliche Struktur. Sie basiert ebenfalls auf SGML. HTML ermöglicht es, die typischen Elemente eines textbasierten Dokuments - wie Überschriften, Absätze, Listen oder Tabellen - als solche auf einer Webseite auszuzeichnen und die Seite semantisch zu strukturieren. Im Gegensatz zu HTML, wo es Regeln für die Benennung von Tags gibt - wie z.B. \<h1\>\</h1\> für Überschriften - können XML-Tags, vorbehaltlich einiger technischer Regeln, frei benannt werden. Dies macht es besonders interessant für die Entwicklung von Metadatenstandards und Ontologien.

#### Regeln für die Benennung von XML-Tags^[1]  

Namen:

* Müssen mit einem Buchstaben oder einem Unterstrich beginnen.
* Dürfen nicht mit den Buchstaben xml (oder XML, oder Xml, etc) beginnen. 
* Können Buchstaben, Ziffern, Bindestriche, Unterstriche und Punkte enthalten. 
* Dürfen keine Leerzeichen enthalten.


Bewährte Benennungspraktiken und was zu beachten ist:

* Verwenden Sie aussagekräftige Namen. 
* Verwenden sie kurze und einfach Namen.
* Vermeiden Sie - / . / : in den Namen, wie \<first-name\> (: ist für Namensräume reserviert, die eine besondere Funktion haben).
* In XML-Tags wird zwischen Groß- und Kleinschreibung unterschieden, sie sind *case sensitive*. Der Tag <Name> unterscheidet sich von <name>.
* XML schneidet mehrere Leerzeichen nicht ab.  

XML bietet auch die Möglichkeit, Kommentare zu verwenden, die nicht automatisch gelesen werden:

```xml
<!-- Here is the content of the comment, there is no closing tag -->
```  

In XML müssen alle Elemente ordnungsgemäß verschachtelt sein, was bedeutet, dass ein Element, das innerhalb eines anderen Elements geöffnet wird, auch innerhalb dieses Elements geschlossen werden muss:

```xml
<collection><name>MET</name><place>New York</place></collection>
```  
Eine Einrückung kann verwendet werden, um die Struktur besser lesbar zu machen, insbesondere wenn die Verschachtelung der Elemente tief ist:

```xml
<collection>
  <name>MET</name>
  <place>collection of the MET in New York</place>
  <artist>
    <name>Fullname</name>
    <dateOfBirth>
      <day>Day of Birth</day>
      <month>Month of Birth</month>
      <year>Year of Birth</year>
    </dateOfBirth>
  </artist>
</collection>
```
oder in einer Zeile: 

```xml
<collection><name></name><place></place><artist><name></name><dateOfBirth><day></day><month></month><year></year></dateOfBirth></artist></collection>
```  

Wie dieses Beispiel zeigt, haben XML-Dokumente eine Baumstruktur. Sie beginnen mit dem Wurzelelement und verzweigen sich dann immer tiefer. Das Tag \<artist\> wird als übergeordnetes Element bezeichnet und die untergeordneten Elemente \<name\> und \<dateOfBirth\> sind untergeordnete Elemente. Auf der tieferen Ebene ist \<dateOfBirth\> das übergeordnete Element für die Tags Tag, Monat und Jahr als untergeordnete Elemente.

Die in der Struktur der XML-Syntax verwendeten Zeichen müssen bestimmte Regeln einhalten. Bestimmte Zeichen, wie z. B. „<“ für „ist kleiner als“, müssen durch eine spezielle Zeichenfolge ersetzt werden, damit sie keine Probleme verursachen. Wenn Sie einfach nur „<“ verwenden, versteht XML es als ein öffnendes Tag und erwartet, dass es irgendwann geschlossen wird. Um Fehler in diesem und ähnlichen Fällen zu vermeiden, wird das Zeichen durch eine Entitätsreferenz ersetzt:
  
| String | Zeichen | Bedeutung | 
| ---- | ---- | ---- | ----|
| \&lt; | < | kleiner als |
| \&gt; | > | größer als |
| \&amp; | & | und |
| \&apos; | ' | Apostroph |
| \&quot; | " | Anführungszeichen |  
  
```xml
<photographer>Bernd &amp; Hilla Becher</photographer>
```  

## Attribute   

In XML wie auch in HTML können Tags auch Attribute haben, die den Inhalt der Tags genauer definieren. Diese Attribute liefern Metadaten für das Element, auf das sie sich beziehen. Sie werden benannt, der Inhalt wird ihnen mit einem = zugewiesen, und sie werden in Anführungszeichen gesetzt:

```xml
<title lang="author's original language">Geben Sie den Titel immer in der Sprache des Autors an.</title>

<commonTitle lang="title as commonly known">Geben Sie den Titel immer so an, wie er gemeinhin bekannt ist</commonTitle>
```      
Attribute werden häufig in einer Hierarchie verwendet, um Informationen zu erfassen, die für alle zugrunde liegenden Daten gelten:  

```xml
<collection name="Modern Art" place="New York">
  <item1/>
  <item2/>
</collection>
```
Der Schrägstrich hier am Ende des Tags (selbstschließender Tag) bedeutet, dass das Element leer und in sich geschlossen ist. Es ist nicht notwendig, ein öffnendes und schließendes Tag zu schreiben, wenn keine anderen Elemente dazwischen liegen oder keine Inhalte vorhanden sind. Sie sehen dies oft in der XML-Ausgabe, wenn das Metadatenfeld leer ist. 

Am Anfang eines XML-Dokuments steht oft ein so genannter Prolog oder eine Deklaration (*declaration):

```xml
<?xml version="1.0" encoding="UTF-8"?>
```
Es ist optional, liefert aber Informationen über die verwendete Version und Kodierung^[2]. Wenn es enthalten ist, muss es am Anfang des Dokuments über dem Root-Element platziert werden. Der XML-Prolog oder die Deklaration hat keinen schließenden Tag.

::: callout
XML-Dokumente, die alle diese Regeln erfüllen, werden als „wohlgeformte“ XML-Dokumente bezeichnet.
:::  


::: challenge

### Übung

Öffnen Sie die Datei "moma_artworks.csv". Wählen Sie den Datensatz eines Werkes aus und schreiben Sie die Daten in XML. 

::: hint

* Erkennen Sie eine Struktur in den Daten? Können Teile der Daten zum Beispiel unter einer Kategorie gesammelt werden?
* Verwenden Sie Einrückungen zur Strukturisierung und Hierarchisierung.
   
:::
  
::: solution

```xml
<?xml version="1.0" encoding="UTF-8"?>
<artworks>
  <artwork>
    <title>Green-Blue-Red (for Parkett no. 35)</title>
    <artist>
      <name>Gerhard Richter</name>
    </artist>
    <constituentID>4907</constituentID>
    <artistBio>
      <bio>German, born 1932</bio>
    </artistBio>
    <nationality>German</nationality>
    <beginDate>1932</beginDate>
    <endDate>0</endDate>
    <gender>male</gender>
    <date>1993</date>
    <medium>Multiple of oil on canvas</medium>
    <dimensions>composition: 11 7/16 × 15 3/4&quot; (29 × 40 cm); sheet: 11 3/4 × 15 3/4&quot; (29.9 × 40 cm)</dimensions>
    <creditLine>Riva Castleman Endowment Fund, Lily Auchincloss Fund, and Gift of Parkett</creditLine>
    <accessionNumber>110.1998.1</accessionNumber>
    <classification>Multiple</classification>
    <department>Drawings &amp; Prints</department>
    <dateAcquired>1998-03-05</dateAcquired>
    <cataloged>Y</cataloged>
    <objectID>61953</objectID>
    <url>https://www.moma.org/collection/works/61953</url>
    <imageURL></imageURL>
    <onView></onView>
    <height>29.0</height>
    <width>40.0</width>
  </artwork>  

  <artwork>
    <title>Untitled</title>
    <artist>
      <name>Blinky Palermo</name>
    </artist>
    <constituentID>4474</constituentID>
    <artistBio>
      <bio>German, 1943–1977</bio>
    </artistBio>
    <nationality>German</nationality>
    <beginDate>1943</beginDate>
    <endDate>1977</endDate>
    <gender>male</gender>
    <date>1970</date>
    <medium>Dyed cotton mounted on muslin</medium>
    <dimensions>6' 6 3/4\" x 6' 6 3/4\" (200 x 200 cm)</dimensions>
    <creditLine>Gift of Jo Carole and Ronald S. Lauder</creditLine>
    <accessionNumber>650.1997</accessionNumber>
    <classification>Painting</classification>
    <department>Painting &amp; Sculpture</department>
    <dateAcquired>1997-06-02</dateAcquired>
    <cataloged>Y</cataloged>
    <objectID>78283</objectID>
    <url>https://www.moma.org/collection/works/78283</url>
    <imageURL>https://www.moma.org/media/W1siZiIsIjE1MTQ0MCJdLFsicCIsImNvbnZlcnQiLCItcmVzaXplIDEwMjR4MTAyNFx1MDAzZSJdXQ.jpg?sha=c54d00f27ed284be</imageURL>
    <onView></onView>
    <height>200.0</height>
    <width>200.0</width>
  </artwork>  

  <artwork>
    <title>Daylight Savings Time</title>
    <artist>
      <name>Pierre Roy</name>
    </artist>
    <constituentID>5065</constituentID>
    <artistBio>
      <bio>French, 1880–1950</bio>
    </artistBio>
    <nationality>French</nationality>
    <beginDate>1880</beginDate>
    <endDate>1950</endDate>
    <gender>male</gender>
    <date>1929</date>
    <medium>Oil on canvas</medium>
    <dimensions>21 1/2 x 15&quot; (54.6 x 38.1 cm)</dimensions>
    <creditLine>Gift of Mrs. Ray Slater Murphy</creditLine>
    <accessionNumber>1.1931</accessionNumber>
    <classification>Painting</classification>
    <department>Painting &amp; Sculpture</department>
    <dateAcquired>1931-01-19</dateAcquired>
    <cataloged>Y</cataloged>
    <objectID>78294</objectID>
    <url>https://www.moma.org/collection/works/78294</url>
    <imageURL>https://www.moma.org/media/W1siZiIsIjIzMzkzNyJdLFsicCIsImNvbnZlcnQiLCItcmVzaXplIDEwMjR4MTAyNFx1MDAzZSJdXQ.jpg?sha=74825d4c62cd5a8a</imageURL>
    <onView></onView>
    <height>54.6</height>
    <width>38.1</width>
  </artwork>  

  <artwork>
    <title>The Bather</title>
    <artist>
      <name>Paul Cézanne</name>
    </artist>
    <constituentID>1053</constituentID>
    <artistBio>
      <bio>French, 1839–1906</bio>
    </artistBio>
    <nationality>French</nationality>
    <beginDate>1839</beginDate>
    <endDate>1906</endDate>
    <gender>male</gender>
    <date>c. 1885</date>
    <medium>Oil on canvas</medium>
    <dimensions>50 x 38 1/8&quot; (127 x 96.8 cm)</dimensions>
    <creditLine>Lillie P. Bliss Collection</creditLine>
    <accessionNumber>1.1934</accessionNumber>
    <classification>Painting</classification>
    <department>Painting &amp; Sculpture</department>
    <dateAcquired>1934-09-23</dateAcquired>
    <cataloged>Y</cataloged>
    <objectID>78296</objectID>
    <url>https://www.moma.org/collection/works/78296</url>
    <imageURL>https://www.moma.org/media/W1siZiIsIjQ0NjA2NyJdLFsicCIsImNvbnZlcnQiLCItcmVzaXplIDEwMjR4MTAyNFx1MDAzZSJdXQ.jpg?sha=c6bd692fa0fe0685</imageURL>
    <onView>&quot;MoMA, Floor 2, 2 South&quot;</onView>
    <height>127.0</height>
    <width>96.8</width>
  </artwork>  

  <artwork>
    <title>Syntheses of Naples</title>
    <artist>
      <name>Enrico Prampolini</name>
    </artist>
    <constituentID>4720</constituentID>
    <artistBio>
      <bio>Italian, 1894–1956</bio>
    </artistBio>
    <nationality>Italian</nationality>
    <beginDate>1894</beginDate>
    <endDate>1956</endDate>
    <gender>male</gender>
    <date>before 1930</date>
    <medium>Oil on canvas</medium>
    <dimensions>39 3/8 x 39 1/2&quot; (100 x 100.3 cm)</dimensions>
    <creditLine>Gift of Dr. Julius Spitzer</creditLine>
    <accessionNumber>1.1942</accessionNumber>
    <classification>Painting</classification>
    <department>Painting &amp; Sculpture</department>
    <dateAcquired>1941-12-10</dateAcquired>
    <cataloged>Y</cataloged>
    <objectID>78299</objectID>
    <url>https://www.moma.org/collection/works/78299</url>
    <imageURL>https://www.moma.org/media/W1siZiIsIjE4NjgzNSJdLFsicCIsImNvbnZlcnQiLCItcmVzaXplIDEwMjR4MTAyNFx1MDAzZSJdXQ.jpg?sha=9740d0c731c867c2</imageURL>
    <onView></onView>
    <height>100.0</height>
    <width>100.3</width>
  </artwork>
</artworks>
```
Dies ist eine mögliche Lösung. Sie können auch andere Wege wählen, um die Daten zu strukturieren, indem Sie Elemente wie "artistBio“ oder "gender" innerhalb eines übergeordneten Elements wie "artist“ verschachteln:

```xml
<artist>
  <artistBio/>
  <gender/>
</artist>
```  
:::
:::  
  
::: instructor
Es ist wahrscheinlich, dass nicht alle Teilnehmer die Übung in der vorgesehenen Zeit abschließen werden, da die XML-Notation sehr komplex ist. Dies ist Teil des Lernprozesses und kann anschließend besprochen werden. Alternativ kann mehr Zeit für die Übung eingeplant werden oder die Teilnehmenden müssen nur ausgewählte Elemente in XML schreiben.
:::   
  
::: discussion

### Diskussion

Vergleichen Sie Ihr Ergebnis mit denen anderer Teilnehmenden. Was fällt Ihnen auf?

:::

::: instructor
Die Übung kann in Gruppen durchgeführt werden, wenn es viele Teilnehmende gibt. Andernfalls kann jemand seine Lösung am Ende vorstellen und es wird gemeinsam diskutiert. Diskussionsthemen sollten die beiden Möglichkeiten sein, leere Elemente zu schreiben und sicherzustellen, dass Sonderzeichen wie z.B. *&* erfasst werden. Es kann auch eine allgemeine Diskussion über die Überschriften oder die Benennung der Tags geführt werden, oder darüber, was bestimmte Tags bedeuten, z.B. onView bedeutet „in der aktuellen Ausstellung zu sehen“.
:::  

::: keypoints
- XML ist eines der am weitesten verbreiteten Dateiformate für Metadaten.
- Ein XML-Dokument enthält XML-Elemente zur Strukturierung der Daten.
- Attribute liefern zusätzliche Informationen über Elemente oder Gruppen von Elementen.
:::
______________________________________________
[1]: [w3school XML elements](https://www.w3schools.com/xml/xml_elements.asp>)  
[2]: Siehe auch Begriffserläuterung im Glossar. 

  