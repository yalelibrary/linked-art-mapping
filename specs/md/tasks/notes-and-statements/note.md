---
author: timothy.thompson@yale.edu
keyword: Assigned
---

# Note

|Domains|Usage|
|-------|-----|
|`LinguisticObject` `HumanMadeObject`|If a note field contains a`5005`subfield, an attempt may be made to match it to the appropriate`HumanMadeObject`\(derived from a corresponding MARC holdings records\). Otherwise, it should be attached to the main`LinguisticObject`resource.|
|`VisualItem` `HumanMadeObject`|If a note field contains a`5005`subfield, an attempt may be made to match it to the appropriate`HumanMadeObject`\(derived from a corresponding MARC holdings records\). Otherwise, it should be attached to the main`VisualItem`resource.|
|`DigitalObject`| |

## Source data

```
---
name: Note
sampleBibs:
  - 2
  - 2814209
fieldSpec:
  - 5005a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Check to see whether the`500`note contains subfield`5`.

    `$a A contribution by T.S. Eliot titled "The class and the elite" appears in v.11, no. 6 (Oct. 1945). $5 CtY-BR`

    -   If the`500`note contains subfield`5`, attempt to match it against a corresponding location in an associated holdings record.

        If a match is made, attach the local note to the`HumanMadeObject`resource corresponding to the matching holdings record.

    -   Else, attach the local note to the`LinguisticObject`resource corresponding to the bibliographic record.
    **Note:** These examples are meant to illustrate general notes and do not represent complete JSON-LD documents.

    **Note:** This example illustrates a case in which a`500`note contains subfield`5`has been successfully matched against the location/call number in a holdings record.

    `2814209`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/object/3e566042-e136-4e60-bd0e-8b5759d5ade1",
      "type": "HumanMadeObject",
      "_label": "The New English review",
      "carries": [
        {
          "id": "https://lux.collections.yale.edu/data/text/9a3265ba-0caa-484b-b19a-bd33e5a96691",
          "type": "LinguisticObject",
          "_label": "The New English review"
        }
      ],
      "identified_by": [
        {
          "type": "Identifier",
          "content": "2007 +S32 (Beinecke)",
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
          "content": "The New English review",
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
          "content": "A contribution by T.S. Eliot titled \"The class and the elite\" appears in v.11, no. 6 (Oct. 1945).",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300027200",
              "type": "Type",
              "_label": "Note"
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Note",
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

    **Note:** This example illustrates a case in which a`500`note does**not**contain a subfield`5`.

    `2`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/968652fc-4e7b-479b-a5b9-f8c0cd68bcb8",
      "type": "LinguisticObject",
      "_label": "Die Streitkräfte der NATO auf dem Territorium der BRD",
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
          "id": "https://lux.collections.yale.edu/data/concept/61d2655b-095d-4864-9d62-e04e55042baf",
          "type": "Type",
          "_label": "UA646.5.G4"
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "Die Streitkräfte der NATO auf dem Territorium der BRD",
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
          "content": "Streitkräfte der NATO auf dem Territorium der BRD",
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
          "content": "Includes index.",
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
              "content": "Note",
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

