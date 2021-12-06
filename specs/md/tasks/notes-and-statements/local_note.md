---
author: timothy.thompson@yale.edu
keyword: Assigned
---

# Local note

Corresponds to the`590`Local Note field at YUL.

|Domains|Usage|
|-------|-----|
|`LinguisticObject` `HumanMadeObject`|If a local note begins with a location/call number prefix, an attempt may be made to match it to the appropriate `HumanMadeObject` \(derived from a corresponding MARC holdings records\). Otherwise, it should be attached to the main `LinguisticObject` resource.|
|`VisualItem` `HumanMadeObject`|If a local note begins with a location/call number prefix, an attempt may be made to match it to the appropriate `HumanMadeObject` \(derived from a corresponding MARC holdings records\). Otherwise, it should be attached to the main `VisualItem` resource.|
|`DigitalObject`| |

## Source data

```
---
name: LocalNote
sampleBibs:
  - 17
  - 1149734
fieldSpec:
  - 5906ab
  - 8806ab
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Check for a location/call number prefix at the start of the local note.

    “BEIN Kosinski 135:”

    -   If the local note begins with a location/call number prefix, attempt to match it against a corresponding location/call number combination in an associated holdings record.

        If a match is made, attach the local note to the `HumanMadeObject` resource corresponding to the matching holdings record.

    -   Else, attach the local note to the `LinguisticObject` resource corresponding to the bibliographic record.
2.  Process the local note values \(MARC `590ab`\).

    -   If both subfields \(`590ab`\) are present, join them with a whitespace character.
    -   Else, output the string value of `590a`.
    **Note:** These examples are meant to illustrate local notes and do not represent complete JSON-LD documents.

    **Note:** This example illustrates a case in which a location/call number prefix has been successfully matched against the location/call number in a holdings record.

    `17`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/object/e7fd991f-33bf-4332-b6e6-b966e2448a54",
      "type": "HumanMadeObject",
      "_label": "Witchcraft",
      "carries": [
        {
          "id": "https://lux.collections.yale.edu/data/text/1d4af671-316c-45c4-8a3b-d97354456de2",
          "type": "LinguisticObject",
          "_label": "Witchcraft"
        }
      ],
      "identified_by": [
        {
          "type": "Identifier",
          "content": "Kosinski 135 (Beinecke)",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311706",
              "type": "Type",
              "_label": "Call Number"
            }
          ]
        },
        {
          "type": "Name",
          "content": "Witchcraft",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "BEIN Kosinski 135: Paperbound. From the Katherina von Fraunhofer-Kosinski Collection of Jerzy Kosinski.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300027200",
              "type": "Type",
              "_label": "Note",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Local Note",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404669",
                  "type": "Type",
                  "_label": "Display Title"
                }
              ]
            }
          ]
        },
        {
          "type": "LinguisticObject",
          "content": "255 p. illus. (part col.), facsims., col. map. 20 cm",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435452",
              "type": "Type",
              "_label": "Physical Statement",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Physical Description",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404669",
                  "type": "Type",
                  "_label": "Display Title"
                }
              ]
            }
          ]
        }
      ]
    }
    ```

    **Note:** This example illustrates a case in which a location/call number prefix has**not**been matched against a location/call number in a holdings record, but rather attached to a `LinguisticObject` resource.

    `17`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/1d4af671-316c-45c4-8a3b-d97354456de2",
      "type": "LinguisticObject",
      "_label": "Witchcraft",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300028051",
          "type": "Type",
          "_label": "Books",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435443",
              "type": "Type",
              "_label": "Type of Work"
            }
          ]
        },
        {
          "id": "https://lux.collections.yale.edu/data/concept/84784fdc-22f4-42b8-9342-b0ad6329c3a2",
          "type": "Type",
          "_label": "GR530"
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "Witchcraft",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        },
        {
          "type": "Name",
          "content": "Witchcraft",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404672",
              "type": "Type",
              "_label": "Sorting Name"
            }
          ]
        }
      ],
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "BEIN Kosinski 135: Paperbound. From the Katherina von Fraunhofer-Kosinski Collection of Jerzy Kosinski.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300027200",
              "type": "Type",
              "_label": "Note",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Local Note",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404669",
                  "type": "Type",
                  "_label": "Display Title"
                }
              ]
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

