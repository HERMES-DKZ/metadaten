---
title: "Dublin Core Metadaten Standard"
teaching: 15
exercises: 10
---
::: questions 

- Was ist das Dublin Core Metadata Element Set (DC)?
- Was ist der Unterschied zwischen einfachem und qualifiziertem Dublin Core? 

:::

::: objectives  

Nach Beendigung dieser Episode sollten Teilnehmende in der Lage sein  

- die wichtigsten Elemente des Dublin Core Metadata Element Set zu identifizieren,   
- zwischen einfachem und qualifiziertem Dublin Core zu unterscheiden,
- einfach Metadaten im Dublin Core Standard zu erfassen. 
:::

## Dublin Core Metadata Element Set

Der Dublin Core ist ein einfacher Metadatenstandard. Er wurde 1998 erstmals von der Dublin Core Metadata Initiative veröffentlicht.
Die einfache Version des Standards besteht aus den folgenden 15 Kernelementen zur Beschreibung einer Ressource:

* Contributor
* Coverage
* Creator
* Date
* Description
* Format
* Identifier
* Language
* Publisher
* Relation
* Rights
* Subject
* Title
* Type

Im Gegensatz zu anderen Metadatenstandards oder Schemata können die Felder der Kernelemente in beliebiger Reihenfolge und mehrfach erscheinen. Zudem sind sie alle optional.
Dublin Core definiert die Metadatenfelder selbst, jedoch nicht deren Struktur, weshalb es oft mit Strukturierungsstandards wie METS kombiniert wird.

::: challenge 

### Übung

Sie haben ein Foto von Johan Hagemeyer. Es trägt den Titel „Albert Einstein, Pasadena“. Darauf ist Albert Einstein zu sehen.
Es wurde im Jahr 1931 aufgenommen und im Jahr 1962 an das Museum ausgeliehen. Das Foto stammt aus dem Nachlass des Fotografen. Albert Einstein lebte von 1879 bis 1955 und war zum Zeitpunkt der Aufnahme 52 Jahre alt. Der Fotograf Johan Hagemeyer lebte von 1884 bis 1962 und das Foto wurde in Pasadena aufgenommen. Der Aufnahmeort ist New York. Das Foto misst 24,6 × 18,7 cm. Das Passepartout hat die Maße 45,6 × 35,4 cm. 

Sie finden das Objekt in der [MET collection](https://www.metmuseum.org/art/collection/search/270713). Schauen Sie sich die Spezifikationen auf der [Webseite](https://www.dublincore.org/specifications/dublin-core/dces/) an, wenn Sie sich unsicher sind, wie Sie die Daten erfassen können. 

Welche Information würden Sie in den Felder der 15 Kernelemente wie erfassen? Machen Sie sich ebenso Gedanken, warum Sie Felder auswählen oder nicht. 
Fehlen Ihnen Informationen um alle Felder auszufüllen? Wenn ja, welche und warum? 

Diskutieren Sie in kleinen Gruppen. 

::: solution

### Lösung

* contributor: MET (als verwahrende und verwaltende Institution)
* coverage: New York (als Ort der verwahrenden und verwaltenden Institution)
* creator: Johan Hagemeyer (als Fotograf)
* date: 1931 (als Einreichungsdatum beim MET)
* description: portrait of Albert Einstein
* format: 24.6 × 18.7 cm (Foto) oder 45.6 × 35.4 cm (Gesamtgröße)
* identifier: ?
* language: en (RFC 4646 standard)
* publisher: MET
* relation: andere Fotografien von Johan Hagemeyer oder andere Bilder mit ähnlichem Inhalt
* rights: © 2013 Jeanne Hagemeyer – All Rights Reserved
* source: ?
* subject: portrait, Albert Einstein
* title:  Albert Einstein, Pasadena
* type: Gelatinesilberdruck

Dies ist eine von mehreren möglichen Lösungen. 
:::
:::

::: discussion

### Diskussion

Was haben Sie diskutiert? Was waren die Herausforderungen bei der Zuordnung? 
:::

Haben Sie darüber diskutiert, welches Datum in das *date*-Feld gehört? Woher wissen wir nun, welches Datum genau gemeint ist? Das Datum der Erstellung des Objekts, das der Digitalisierung, der Veröffentlichung oder das der Übermittlung an die Institution?   

Die ursprünglichen Kernelemente von Dublin Core wurden erweitert, um solche und andere Informationen über die Daten zu präzisieren. 

## Qualified Dublin Core 

Zunächst wurden Qualifier eingeführt. Ein Qualifier erweitert ein einfaches Element. 

Ein einfaches Dublin-Core-Element sieht folgendermaßen aus:

dc.date

*dc* beschreibt den so genannten Namespace. Ein Namespace identifiert einen Standard, wie in diesem Fall *dc* für Dublin Core und wird Ihnen im Bereich der Metadaten und XML immer wieder begegnen. *date* beschreibt das Element. Beide können nun um einen Qualifier erweitert werden, der das Element spezifiziert, z.B.:

dc.relation.hasversion oder dc.relation.isversionof

Mit diesen Erweiterungen wird das Feld *relation* für die Versionierung eines Objekts oder eine Datei verwendet. Dies kann der Fall sein, wenn es mehrere Digitalisierungen eines analogen Objekts gibt oder auch grundlegend, wenn zwischen der Erfassung des analogen Objekts und der digitalisierten Version unterschieden wird. 

::: challenge 

### Übung

Schauen Sie sich das *date*-Element genauer an. Eine Liste aller authorisierten Qualifier finden Sie auf der [Dublin Core Webseite](https://www.dublincore.org/specifications/dublin-core/usageguide/qualifiers/). Welchen Qualifier würden Sie für welche Datumsangabe der Fotografie Hagemeyers verwenden?  

::: solution

### Beispiele

* dc.date.created: 1931
* dc.date.submitted: 1962
* dc.date.copyrighted: 2013
* dc.date.issued: Datum, an dem das Bild digital in der Websammlung veröffentlicht wurde

:::
:::    

### DCMI Metadata Terms      

2022 publizierte die Dublin Core Metadata Initiative ein erweitertes Set von Elementen:

> Included are the fifteen terms of the Dublin Core™ Metadata Element Set (also known as "the Dublin Core") plus several dozen properties, classes, datatypes, and vocabulary encoding schemes. The "Dublin Core" plus these extension vocabularies are collectively referred to as "DCMI metadata terms" ("Dublin Core terms" for short). These terms are intended to be used in combination with metadata terms from other, compatible vocabularies in the context of application profiles.^[1]

In diesem Set werden alle vorhandenen Kernelemente zusammengefasst und durch ergänzende Felder erweitert und präzisiert, zum Beispiel durch *dateAccepted* oder zusätzliche Felder wie *abstract*. 

Die [Terms](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/):  
  
|      |      |      |      |      |  
|:----:|:----:|:----:|:----:|:----:|  
|abstract|accessRights|accrualMethod|accrualPeriodicity|accrualPolicy|  
|alternative|audience|available|bibliographicCitation|conformsTo|  
|contributor|coverage|created|creator|date|  
|dateAccepted|dateCopyrighted|dateSubmitted|description|educationLevel|  
|extent|format|hasFormat|hasPart|hasVersion|  
|identifier|instructionalMethod|isFormatOf|isPartOf|isReferencedBy|  
|isReplacedBy|isRequiredBy|issued|isVersionOf|language|  
|license|mediator|medium|modified|provenance|  
|publisher|references|relation|replaces|requires|  
|rights|rightsHolder|source|spatial|subject|  
|tableOfContents|temporal|title|type|valid|      

::: discussion

### Diskussion

Wie ist Ihre Meinung zu dem erweiterten Metatdatenset? Fehlen Ihnen aus Ihrem Fachgebiet zum Beispiel noch spezielle Felder? Können Sie sich vorstellen für ein in Ihrem Fachgebiet relevantes Objekt alle Felder auszufüllen? 
:::   

::: callout

Sehr wahrscheinlich werden Sie feststellen, dass mit den im Dublin-Core-Standard vorgegebenen Metadatenfeldern nicht alle Objekte erfasst werden können. Auch können Sie nicht alle Felder immer ausfüllen. Daher gibt es viele weitere Standards oder Schemata, die für das jeweilige Fachgebiet oder spezielle Objekte des kulturellen Erbes erstellt worden sind. Es wird Ihnen eventuell auch auffallen, wenn Sie andere Standards oder Schemata betrachten, dass einige wiederum Elemente von Dublin Core nachnutzen.  
:::   

  
::: keypoints
- Der Dublin-Core-Standard umfasst einen einfachen Satz von 15 Elementen sowie einen erweiterten Satz mit zusätzlichen Eigenschaften, Klassen, Datentypen und Kodierungsschemata.  
- Alle Felder sind optional, nicht obligatorisch, können mehrfach und in beliebiger Reihenfolge erscheinen. Dublin Core definiert die Metadatenfelder selbst, aber nicht die Struktur für sie. 
:::

_____________________________________________________  

[1]: [DCMI Metadata Terms](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/)

