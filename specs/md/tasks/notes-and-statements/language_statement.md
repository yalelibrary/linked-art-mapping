---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Language statement

Textual information on the language or notation system used to convey the content of the described materials.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: LanguageStatement
sampleBibs:
  - 1001852
fieldSpec:
  - 546ab
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the language statement values \(MARC `546ab`\).

2.  For top-level resources with a base class of `LinguisticObject`:

    -   If both subfields \(`546ab`\) are present, join them with a whitespace character.
    -   Else, output the string value of `546a`.
    **Note:** This example is meant to illustrate a language statement and does not represent a complete JSON-LD document.

    `1001852`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Syriac; Hebrew alphabet.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435433",
              "type": "Type",
              "_label": "Language Statement",
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
              "content": "Language Note",
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

3.  For top-level resources with a base class of `Set` \(archival records or kits\), language information should be attached to the embedded `HumanMadeObject` resource using the `carries` property.

    -   If both subfields \(`546ab`\) are present, join them with a whitespace character.
    -   Else, output the string value of `546a`.
    `11167038`

    ```
    {
      "members_exemplified_by": [
        {
          "type": "HumanMadeObject",
          "_label": "Cipher manuscript",
          "carries": [
            {
              "type": "LinguisticObject",
              "referred_to_by": [
                {
                  "type": "LinguisticObject",
                  "content": "Syriac; Hebrew alphabet.",
                  "classified_as": [
                    {
                      "id": "http://vocab.getty.edu/aat/300435433",
                      "type": "Type",
                      "_label": "Language Statement",
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
                      "content": "Language Note",
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
          ]
        }
      ]
    }
    ```


**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

