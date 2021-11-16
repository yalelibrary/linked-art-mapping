---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu, tt434]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Record-level entities

Entities that correspond to resources held by the library \(books, journals, databases, archival collections, etc.\).

The Linked Art profile of the [CIDOC Conceptual Reference Model \(CRM\)](http://www.cidoc-crm.org/html/5.0.4/cidoc-crm.html) includes a limited number of core or base classes. These can be refined by referencing terms from a taxonomy or classification scheme. Because record-level entities can be of many types, a *supertype* scheme has been developed for use in LUX.

The LUX supertype scheme is divided into two levels: *types* and *formats*. Types represent the mode of expression of a resource \(textual, visual, audible, etc.\), whereas formats can be thought of as specific instances of a type: for example, a *Book* is an instance or format of *Textual Works*. Some formats, such as *Geospatial Data* are instances of two different types: *Datasets* and *Cartography*.

The base class for record-level entities is determined by the supertype mapping. When a record-level entity is mapped to more than one supertype format, and the formats have different base classes, the following order of priority is applied:

1.  `Set`

2.  `LinguisticObject`

3.  `VisualItem`

4.  `DigitalObject`

5.  `HumanMadeObject`


1.  [Content and carriers](../tasks/content_and_carriers.md)  

2.  [LUX supertype taxonomy](../concepts/supertypes/supertypes.md)  
Taxonomy of content types and related formats for classifying record-level resources in LUX.
3.  [Related title entities](../tasks/names-and-labels/related_title_entities.md)  


**Parent topic:**[LUX top-level entities](../concepts/lux_top-level_entities.md)

**Next topic:**[Work-level entities \[draft\]](../concepts/work_level_entities.md)

