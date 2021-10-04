---
author: [tt434, timothy.thompson@yale.edu, tt434]
---

# Record-level entities

Entities that correspond to resources held by the library \(books, journals, databases, archival collections, etc.\).

The base class for record-level entities is determined by the supertype mapping. When a record-level entity is mapped to more than one supertype format, and the formats have different base classes, the following order of priority is applied:

1.  `Set`

2.  `DigitalObject`

3.  `LinguisticObject`

4.  `VisualItem`

5.  `HumanMadeObject`


YUL supertypes with a base class of `HumanMadeObject` must follow the concept/carrier model and point to a `VisualItem` where the supertype and any subjects are assigned.

1.  [LUX supertype taxonomy](../concepts/supertypes/supertypes.md)  

2.  [Name-title entries](../concepts/name_title_entries.md)  

3.  [Title entries](../concepts/title_entries.md)  


**Parent topic:**[LUX top-level entities](../concepts/lux_top-level_entities.md)

**Next topic:**[Related entities](../tasks/related_entities.md)

