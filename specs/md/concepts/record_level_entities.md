---
author: [timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Record-level entities

Entities that correspond to resources held by the library \(books, journals, databases, archival collections, etc.\).

The base class for record-level entities is determined by the supertype mapping. When a record-level entity is mapped to more than one supertype format, and the formats have different base classes, the following order of priority is applied:

1.  `Set`

2.  `LinguisticObject`

3.  `VisualItem`

4.  `DigitalObject`

5.  `HumanMadeObject`


YUL supertypes with a base class of `HumanMadeObject` must follow the concept/carrier model and point to a `VisualItem` where the supertype and any subjects are assigned.

1.  [LUX supertype taxonomy](../concepts/supertypes/supertypes.md)  


**Parent topic:**[LUX top-level entities](../concepts/lux_top-level_entities.md)

**Next topic:**[Work-level entities](../concepts/work_level_entities.md)

