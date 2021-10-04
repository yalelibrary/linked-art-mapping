---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu, tt434]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Related entities

Entities that represent the people, places, concepts, etc., that are connected to record-level resources.

## Source data

```
---
name: RelatedEntities
fieldSpec:
  - 10004abcdegjq
  - 11004abcdeg
  - 11104acdegjnqu
  - 1300adfhklmnoprst
  - 2400adfghklmnoprs
  - 440a
  - 60004abcdegjqvxyz
  - 61004abcdegvxyz
  - 61104acdegjnquvxyz
  - 6300adfhklmnoprstvxyz
  - 65004abcdegvxyz
  - 65104abcdfghvxyz 
  - 65504abcvxyz
  - 69004abcdegvxyz
  - 69104abcdfgh
  - 69204abcdegjq
  - 69304abcdeg
  - 69404acdegjnqu
  - 6950adfhklmnoprst
  - 7000abcdgjq
  - 7100abcdg
  - 71104acdegjnquvxyz
  - 7300adfhklmnoprst
  - 75104abcdfgh
  - 75204abcdfghvxyz
  - 760ait
  - 762ait
  - 765at
  - 767at
  - 770at
  - 772at
  - 773at
  - 774at
  - 775at
  - 776at
  - 777at
  - 780at
  - 785at
  - 786at
  - 787at8000abcdgjq
  - 8100abcdg
  - 81104acdegjnquvxyz
  - 8300adfhklmnoprst

```

## Processing information

1.  Extract related entities from MARC bibliographic records and assign an IRI to each distinct entity.

    1.  Create top-level related entities by normalizing and merging the string value of the source data subfields.

    2.  Apply specific processing steps for each related entity type \(Concepts, Events, etc.\).

2.  Add embedded references to related entities within corresponding record-level resources \(`DigitalObject`, `HumanMadeObject`, `LinguisticObject`, `Set`, `VisualItem`\).


-   **[Concepts](../concepts/concepts.md)**  
Entities that represent what a resource is about.
-   **[Events](../concepts/events.md)**  
Entities that represent time periods and/or discrete events related to a record-level resource.
-   **[Groups](../concepts/groups.md)**  

-   **[People](../concepts/people.md)**  

-   **[Places](../concepts/places.md)**  

-   **[Provenance Activities](../concepts/provenance_activities.md)**  

-   **[Digital Objects](../concepts/related_digital_objects.md)**  

-   **[Sets](../concepts/related_sets.md)**  


**Parent topic:**[LUX top-level entities](../concepts/lux_top-level_entities.md)

**Previous topic:**[Record-level entities](../concepts/record_level_entities.md)

