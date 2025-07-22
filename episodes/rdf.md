---
title: "Resource Description Framework (RDF)"
teaching: 20
exercises: 10
---
::: questions 

- Was ist Resource Description Framework (RDF)?
- Wie können Informationen durch Triples und URI miteinander verlinkt werden?  
:::

::: objectives
Nach Beendigung dieser Episode sollten Teilnehmende in der Lage sein

- das Konzept des Resource Description Framework (RDF) zu beschreiben,
- die Elemente eines Triples zu benennen,
- URI für RDF-Triple zu finden und RDF-Statements zu kreieren. 
:::  

RDF wurde ursprünglich vom World Wide Web Consortium (W3C) als Standard für die Beschreibung von Metadaten konzipiert. 
Es gilt heute als ein grundlegender Baustein des Semantic Web und ähnelt den klassischen Methoden 
zur Modellierung von Konzepten, wie dem in der Einleitung erwähnten Entity-Relationship-Modell.

Daten in RDF sind Aussagen über Ressourcen. Diese Aussagen werden als Tripel modelliert. Die Menge der Tripel bildet einen 
(mathematischen) Graphen und wird RDF-Modell genannt.

```xml
<subject/><predicate/><object/>
<artist>Frida Kahlo></artist><creator>is creator of</creator><artwork>The two fridas</artwork>
```  

Das Subjekt und das Prädikat sind immer Ressourcen. Das bedeutet, dass es sich um Entitäten mit einem erweiterten Satz an Informationen handelt. Das Objekt kann entweder eine Ressource oder ein Literal sein. Literale sind Zeichenketten, die anhand eines bestimmten Datentyps wie boolesche Werte, Zahlen oder Daten interpretiert werden können. Eindeutige Bezeichner (z.B. URI) werden zur Identifizierung von Ressourcen verwendet.  

Ein Uniform Resource Identifier (URI) ist ein Bezeichner, der aus einer Zeichenfolge besteht, die zur Identifizierung einer abstrakten oder physischen Ressource verwendet wird. Sie sind ähnlich aufgebaut wie eine Webadresse (URL). Die bereits erwähnten GND- oder Wikidata-IDs sind Beispiele dafür. Mit Hilfe der URI können verschiedene Quellen miteinander verknüpft werden. Erinnern Sie sich an die Grafik in der Einleitung. 

Das Prädikat wird ebenfalls durch einen URI definiert. Dies ist z.B. möglich, wenn die Beziehung durch einen Metadatenstandard definiert ist. Die Metadatenfelder der Standards haben ihren eigenen URI. Die Beziehung zwischen einer Künstlerin und ihrem Kunstwerk kann unter mit dem Dublin Core-Element "creator" modelliert werden.

```
<https://www.wikidata.org/wiki/Q5588><http://purl.org/dc/terms/creator><https://www.wikidata.org/wiki/Q3232010>
```   

Dieses Beispiel drückt dasselbe aus, wie das vorherige Beispiel: Frida Kahlo ist die Schöpferin von "Die zwei Fridas". Dazu werden die Identifikatoren von Wikidata und Dublin Core verwendet. 

Technisch gesehen kann RDF in mehreren Formaten implementiert werden, darunter JSON-LD und RDF/XML - zwei spezielle Formate von JSON und XML für RDF.  

:: challenge

### Übung

Schauen Sie sich den [Wikidata-Eintrag von Frida Kahlos Gemälde "Die zwei Fridas"](https://www.wikidata.org/wiki/Q3232010) genauer an. Finden Sie einen alternativen Weg das Prädikat zu beschreiben anstelle der Nutzung von Dublin Core?

::: solution

### Lösung

[creator property](https://www.wikidata.org/wiki/Property:P170):  
Die in Wikidata für eine Entität aufgeführten Informationen sind alle mit Eigenschaften wie Ort, Genre, Ersteller usw. versehen. Diese Eigenschaften haben selbst einen Bezeichner und sind daher standardisiert. Alle Bilder können auf einheitliche Weise modelliert werden. Die Eigenschaft „creator“ kann ähnlich wie das Dublin Core-Element „creator“ verwendet werden.
:::
:::

::: challenge

### Exercise

Nutzen Sie Wikidata, um die folgenden Aussagen zu modellieren:   
1) Michelangelo hat die Pietà geschaffen.  
2) Michelangelo wurde in Caprese Michelangelo geboren.  
3) Die Pietá befindet sich im Petersdom.   

::: solution

### Lösung

```
<https://www.wikidata.org/wiki/Q5592><https://www.wikidata.org/wiki/Property:P170><https://www.wikidata.org/wiki/Q235242>
<https://www.wikidata.org/wiki/Q5592><https://www.wikidata.org/wiki/Property:P19><https://www.wikidata.org/wiki/Q52069>
<https://www.wikidata.org/wiki/Q235242><https://www.wikidata.org/wiki/Property:P276h><ttps://www.wikidata.org/wiki/Q12512>
```
:::
:::
   


::: keypoints
- RDF ist ein Standardmodell für den Datenaustausch im Web.  
- Aussagen werden als Tripel modelliert. Mithilfe von URI verknüpfen diese Tripel Daten (und damit alle dahinter stehenden Informationen) und bilden einen (mathematischen) Graphen.
:::
