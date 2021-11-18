---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Classification numbers

Resources extracted from MARC 050 and 090 entries.

## Source data

```
---
name: ClassificationNumbers
sampleBibs:
  - 4
  - 236
  - 907498
  - 4824458
  - 15589961
# Source data fields
fieldSpec:
  - 050a
  - 090a
trimPunctuation: true
stripPunctuation:
  - true
  - preserve:
    - period
scriptInclusion: NONE
```

1.  Generate and store the top-level concept resources, each identified by an IRI.

    1.  Create a key for merging.

    2.  Replace any punctuation characters that are*not*a period \(`.`\) with a whitespace character.

    3.  Normalize and merge each unique string value.

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → id`|Concept IRI| |
    |`root → type`| |`Type`|
    |`root → _label`|Label of classification number| |
    |`root → identified_by → type`| |`Identifier`|
    |`root → identified_by → content`|Same as`root → _label`| |

    `907498`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/f0c0c4d0-532d-4438-a26f-15c261fb4f6c",
      "type": "Type",
      "_label": "PT3818",
      "identified_by": [
        {
          "type": "Identifier",
          "content": "PT3818"
        }
      ]
    }
    ```

2.  In each referring record-level resource \(`LinguisticObject`,`VisualItem`, or`DigitalObject`\), add an embedded reference to the Concept entity.

    1.  The embedded reference should follow theclassification of the resource in the same`classified_as`array.

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → classified_as → id`|Must match the`id`of the top-level resource| |
    |`root → classified_as → type`| |`Type`|
    |`root → classified_as → _label`|Must match the`_label`of the top-level resource| |

    `907498`

    ```
    {
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300028051",
          "type": "Type",
          "_label": "Books",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300226816",
              "type": "Type",
              "_label": "Form"
            }
          ]
        },
        {
          "id": "https://lux.collections.yale.edu/data/concept/f0c0c4d0-532d-4438-a26f-15c261fb4f6c",
          "type": "Type",
          "_label": "PT3818"
        }
      ]      
    }
    ```


**Parent topic:**[Concepts](../../concepts/concepts.md)

**Related information**  


[050 \(Library of Congress Call Number\)](../../tables/050_bib_table.md)

[090](../../tables/090_bib_table.md)

