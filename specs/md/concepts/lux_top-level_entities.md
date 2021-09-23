---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# LUX top-level entities

A set of 11 top-level entities are required for use in *LUX*.

In LUX, top-level entities can be divided into *record-level* entities, which correspond to resources held by the library \(books, journals, databases, archival collections, etc.\), and *related* entities, which correspond to the people, places, concepts, etc., connected to those resources in some way.

In Linked Art, record-level entities are further divided into two categories:

-   Conceptual entities, which represent the intellectual content of a resource

-   Physical objects, which carry that content in a tangible form


Digital objects are a special case because they can function as either conceptual entities or content carriers, depending on the context.

The Linked Art profile of the [CIDOC Conceptual Reference Model \(CRM\)](http://www.cidoc-crm.org/html/5.0.4/cidoc-crm.html) includes a limited number of core classes; these can easily be refined by referencing terms from a taxonomy or classification scheme. Because record-level entities can be of many types, a *supertype* scheme has been developed for use in LUX.

The LUX supertype scheme is divided into two levels: *types* and *formats*. Types represent the mode of expression of a resource \(textual, visual, audible, etc.\), whereas formats can be thought of as specific instances of a type: for example, a *book* is an instance or format of *textual work*. Some formats, such as *GIS* are instances of two different types: *Datasets* and *Cartography*.

MARC to Linked Art mappings are done at the level of the most specific format, with type and broader format relations inferred from the hierarchy.

![LUX supertypes](/Users/tt434/Dropbox/YUL/ccd/data-transform/dita/resources/img/supertypes.svg)

|Linked Art core class|LUX entity type|LUX format \(level one\)|LUX format \(level two\)|LUX format \(level three\)|
|---------------------|---------------|------------------------|------------------------|--------------------------|
|DigitalObject|Datasets| | | |
|HumanMadeObject| | | | |
|LinguisticObject| | | | |
|VisualItem| | | | |

1.  [Record-level entities](../concepts/record_level_entities.md)  

2.  [LUX supertype taxonomy](../concepts/supertypes/supertypes.md)  


**Previous topic:**[Entity extraction](../concepts/entity_extraction.md)

**Linked Art documentation**  


[Concept](https://linked.art/api/1.0/shared/type/)

[Digital Object](https://linked.art/api/1.0/endpoint/digital_object/)

[Event](https://linked.art/api/1.0/endpoint/event/)

[Group](https://linked.art/api/1.0/endpoint/group/)

[Person](https://linked.art/api/1.0/endpoint/person/)

[Physical Object](https://linked.art/api/1.0/endpoint/physical_object/)

[Place](https://linked.art/api/1.0/endpoint/place/)

[Provenance Activity](https://linked.art/api/1.0/endpoint/provenance_activity/)

[Set](https://linked.art/api/1.0/endpoint/set/)

[Textual Work](https://linked.art/api/1.0/endpoint/textual_work/)

[Visual Work](https://linked.art/api/1.0/endpoint/visual_work/)

