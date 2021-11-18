---
author: timothy.thompson@yale.edu
---

# Dimension statement

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: DimensionStatement
sampleBibs:
  - 25079
  - 3811379
fieldSpec:
  - 3003acef
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the physical statement values \(MARC`3003acef`\).

    1.  Create separate dimension statements for`3003af`and`3003e`\(identified as`Extent`statements\), and for`3003c`\(identified as a`Dimensions`statement.

    2.  Join fields`3003af`,`3003e`, or`3003c`with a whitespace character.

    3.  If subfield`3`is present, but does not appear first in the subfield sequence, prefix the statement with the value of subfield`3`.

    4.  Test the value of`3`to see whether it ends with a colon.

    5.  If no colon is present, concatenate the value with a colon \(`:`\).

    6.  Else, output the value of subfield`3`.

        ```
        300  $3 Copy 1: $a 1 album (32 photographic prints) : $b b & w ; $c 13.4 x 20.6 cm.
        300  $3 Copy 2: $a 1 album (39 photographic prints) : $b b & w ; $c 13.4 x 20.6 cm.
        ```

        **Note:** This example is meant to illustrate dimension statements and does not represent a complete JSON-LD document.

        `3811379`

        ```
        {
          "referred_to_by": [
            {
              "type": "LinguisticObject",
              "content": "Copy 1: 1 album (32 photographic prints)",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300435430",
                  "type": "Type",
                  "_label": "Dimension Statement",
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
                  "content": "Extent",
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
              "content": "Copy 1: 13.4 x 20.6 cm",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300435430",
                  "type": "Type",
                  "_label": "Dimension Statement"
                }
              ],
              "identified_by": [
                {
                  "type": "Name",
                  "content": "Dimensions",
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
              "content": "Copy 2: 1 album (39 photographic prints)",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300435430",
                  "type": "Type",
                  "_label": "Dimension Statement"
                }
              ],
              "identified_by": [
                {
                  "type": "Name",
                  "content": "Extent",
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
              "content": "Copy 2: 13.4 x 20.6 cm",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300435430",
                  "type": "Type",
                  "_label": "Dimension Statement"
                }
              ],
              "identified_by": [
                {
                  "type": "Name",
                  "content": "Dimensions",
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

