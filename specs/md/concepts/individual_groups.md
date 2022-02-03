---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Entities for specific groups

## Processing steps and output

1.  Create a top-level resource for the following group entities:

    1.  Yale University Library

    2.  Yale Center for British Art

    3.  Yale University Art Gallery

    4.  OCLC

    5.  Library of Congress

    1.  ```
{
  "@context": "https://linked.art/ns/v1/linked-art.json",
  "id": "https://lux.collections.yale.edu/data/group/b96ea2c4-b196-4152-b696-d5b831bfaf07",
  "type": "Group",
  "_label": "Yale University Library",
  "equivalent": [
    {
      "id": "http://id.loc.gov/authorities/names/n80008747",
      "type": "Group",
      "_label": "Yale University Library"
    },
    {
      "id": "http://vocab.getty.edu/ulan/500303563",
      "type": "Group",
      "_label": "Yale University Library"
    },
    {
      "id": "http://www.wikidata.org/entity/Q2583293",
      "type": "Group",
      "_label": "Yale University Library"
    }
  ]
}
```

    2.  ```
{
  "@context": "https://linked.art/ns/v1/linked-art.json",
  "id": "https://lux.collections.yale.edu/data/group/ycba-as-entity",
  "type": "Group",
  "_label": "Yale Center for British Art",
  "equivalent": [
    {
      "id": "http://id.loc.gov/authorities/names/n77005277",
      "type": "Group",
      "_label": "Yale Center for British Art"
    },
    {
      "id": "http://vocab.getty.edu/ulan/500303557",
      "type": "Group",
      "_label": "Yale Center for British Art"
    },
    {
      "id": "http://www.wikidata.org/entity/Q6352575",
      "type": "Group",
      "_label": "Yale Center for British Art"
    }
    
  ]
}
```

    3.  ```
{
  "@context": "https://linked.art/ns/v1/linked-art.json",
  "id": "https://lux.collections.yale.edu/data/group/yuag-as-entity",
  "type": "Group",
  "_label": "Yale University Art Gallery",
  "equivalent": [
    {
      "id": "http://id.loc.gov/authorities/names/n79129213",
      "type": "Group",
      "_label": "Yale University Art Gallery"
    },
    {
      "id": "http://vocab.getty.edu/ulan/500303559",
      "type": "Group",
      "_label": "Yale University Art Gallery"
    },
    {
      "id": "http://www.wikidata.org/entity/Q1568434",
      "type": "Group",
      "_label": "Yale University Art Gallery"
    }
  ]
}
```

    4.  ```
{
  "@context": "https://linked.art/ns/v1/linked-art.json",
  "id": "https://lux.collections.yale.edu/data/group/oclc-as-entity",
  "type": "Group",
  "_label": "OCLC",
  "equivalent": [
    {
      "id": "http://www.wikidata.org/entity/Q190593",
      "type": "Group",
      "_label": "OCLC"
    }
  ]
}
```

    5.  ```
{
  "@context": "https://linked.art/ns/v1/linked-art.json",
  "id": "https://lux.collections.yale.edu/data/group/lc-as-entity",
  "type": "Group",
  "_label": "OCLC",
  "equivalent": [
    {
      "id": "https://www.wikidata.org/entity/Q131454",
      "type": "Group",
      "_label": "OCLC"
    }
  ]
}
```

2.  Include an embedded reference to the group entity in the appropriate context.

    1.  YUL, YCBA, and YUAG as defined in [Repository collections](library_collections.md).

    2.  OCLC and Library of Congress within `AttributeAssignment` entities for OCLC numbers and LCCNs, \([System Control Numbers \(OCLC Numbers\)](../tasks/identifiers/oclc_numbers.md) and [Library of Congress Control Number \(LCCN\)](../tasks/identifiers/library_of_congress_control_number_lccn.md)\), respectively.


**Parent topic:**[Groups](../concepts/groups.md)

