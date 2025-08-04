---
title: "Metadata Encoding & Transmission Standard (METS)"
teaching: 15
exercises: 20
---
::: questions 

- Was ist der Metadata Encoding & Transmission Standard?
- Welches sind die wichtigsten Elemente des Standards? 

:::

::: objectives
Nach Beendigung dieser Episode sollten Teilnehmende in der Lage sein  

- die wesentlichen Konzepte des Metadata Encoding & Transmission Standards zu beschreiben,  
- die wichtigsten Elemente zur Strukturierung von Daten in METS zu benennen.  
   
:::

## METS Metadata Encoding & Transmission Standard

METS ist ein von der Library of Congress bereitgestelltes XML-Format, das über XML Schema definiert wurde, um digitale Sammlungen von Objekten mit Metadaten zu beschreiben. Der Standard legt keinen Namen oder eine Reihenfolge für die Metadatenfelder selbst fest, sondern dient dazu, diese in einer standardisierten Weise zu strukturieren. Er wird häufig für die Langzeitarchivierung verwendet und unterstützt das digitale Sammlungsmanagement. Es lassen sich Informationen über die Herkunft digitaler Objekte ebenso abbilden, wie Verwaltungs- oder Strukturinformationen zur Sammlung.    


Die Metadaten werden in eine von sieben Sektionen eingeordnet:   

1. METS Header: Metadaten, die das METS-Dokument selbst beschreiben, einschließlich Informationen wie Ersteller oder Herausgeber des METS-Dokuments usw.
2. Descriptive Metadata Section: Der Abschnitt enthält die Erschließungsdaten des Objekts. Hier kann auf beschreibende Metadaten außerhalb des METS-Dokuments verwiesen werden oder er kann intern eingebettete beschreibende Metadaten enthalten, oder beides. 
3. Administrative Metadata Section: Dieser Abschnitt enthält Informationen darüber, wie Dateien erstellt und gespeichert wurden, Urheberrechte oder auch Metadaten über das ursprüngliche Quellobjekt, von dem das digitalisierte Objekt stammt. 
4. File Section: Die Datei-Sektion listet alle Dateien auf, die zum digitalen Objekt gehören, wie etwa verschiedene Versionen von Digitalisaten. 
5. Structural Map: Sie skizziert eine hierarchische Struktur des digitalen Objekts.
6. Structural Links: Hier werden alle Hyperlinks gelistet, wie sie etwa für die Archivierung von Webseiten unbedingt notwendig sind. 
7. Behavioral Section: Diese Sektion kann verwendet werden, um ausführbare Verhaltensweisen oder Funktionalitäten mit dem Inhalt des METS-Objekts zu verknüpfen.


Die grundlegende XML-Syntax einer METS-Datei sieht folgendermaßen aus:   

```XML
<mets>
 <metsHdr/><!-- METS Header -->
 <dmdSec/><!-- Descriptive Metadata Section -->
 <amdSec/><!-- Administrative Metadata Section -->
 <fileSec/><!-- File Section -->
 <structMap/><!-- Structural Map -->
 <structLink/><!-- Structural Links -->
 <behaviorSec/><!-- Behavioral Section -->
</mets>
```   

Beispiele und Erklärungen zu den einzelnen Sektionen finden sich im [Tutorial zum Standard](https://www.loc.gov/standards/mets/METSOverview.v2.html).    

::: challenge

### Übung 1

Verwende das Beispiel aus der XML-Übung und ordne die Metadatenelemente der Struktur des METS-Standards zu.

::: solution 

### Lösung

Eine Lösung zum ersten Datensatz aus den Beispieldaten der XML-Übung kann so aussehen:    
```XML
<mets>
 <metsHdr>
  <creator>Moma</creator>
  <editor>me</editor>
  <creationdate>today</creationdate>
 </metsHdr>

 <dmdSec>
  <artwork>
    <title>Green-Blue-Red (for Parkett no. 35)</title>
    <date>1993</date>
    <medium>Multiple of oil on canvas</medium>
    <dimensions>composition: 11 7/16 × 15 3/4&quot; (29 × 40 cm); sheet: 11 3/4 × 15 3/4&quot; (29.9 × 40 cm)</dimensions>
    <department>Drawings &amp; Prints</department>
  <artist>
    <name>Gerhard Richter</name>
    <constituentID>4907</constituentID>
    <artistBio>
      <bio>German, born 1932</bio>
    </artistBio>
    <nationality>German</nationality>
    <beginDate>1932</beginDate>
    <endDate>0</endDate>
    <gender>male</gender>
  </artist>
 </dmdSec>   
    
 <amdSec>
  <creditLine>Lillie P. Bliss Collection</creditLine>
  <accessionNumber>1.1934</accessionNumber>
  <dateAcquired>1998-03-05</dateAcquired>
  <cataloged>Y</cataloged>
  <objectID>61953</objectID>
 </amdSec>

 <fileSec>
  <url>https://www.moma.org/collection/works/78296</url>
  <imageURL>https://www.moma.org/media/W1siZiIsIjQ0NjA2NyJdLFsicCIsImNvbnZlcnQiLCItcmVzaXplIDEwMjR4MTAyNFx1MDAzZSJdXQ.jpg?sha=c6bd692fa0fe0685</imageURL>
  <onView>&quot;MoMA, Floor 2, 2 South&quot;</onView>
 </fileSec>

 <structMap/>

 <structLink/>

 <behaviorSec/>
  <onView></onView>

</mets>
```
:::
:::  

::: challenge

### Übung 2

Die [Webseite der Library of Congress](https://www.loc.gov/standards/mets/mets-examples.html) listet verschiedene Beispiele für die Umsetzung des Standards. Schaue dir einige davon an. Was fällt auf?  

::: solution

### Lösung

- In vielen Beispielen wird der MODS-Standard innerhalb der METS-Struktur verwendet. Vielfach wird daher auch vom Austauschformat METS/MODS gesprochen. 
- Die letzten Abschnitte fehlen oft oder enthalten nicht viele Daten.
- Die amdSec enthält technische Informationen zu den technischen Mitteln der Digitalisierung, wie Kamera oder Scanner und deren Einstellungen.
- Die amdSec ist manchmal in weitere Abschnitte unterteilt, z. B. Rechte und technische Daten. Es wird also eine weitere Strukturierung innerhalb der Sektionen vorgenommen. 
:::
:::

::: keypoints
- METS dient als Container zur Strukturierung von Metadaten.  
- Die Metadatenfelder selber werden meist in einem spezifischen Standard erfasst und dann in die METS-Struktur integriert. Dazu gehören Standards wie Cublin Core, MODS oder MARC.
:::
