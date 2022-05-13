---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Primary name

Main title of a record-level entity.

|Domains|Usage|
|-------|-----|
|`LinguisticObject` `HumanMadeObject` `DigitalObject`|Repeat on both JSON-LD documents.|
|`VisualItem` `HumanMadeObject` `DigitalObject`|Repeat on both JSON-LD documents.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|

**Note:** The primary name is mirrored in parallel non-Latin script titles, when present.

## Source data

```
---
name: PrimaryName
sampleBibs:
  - 3
  - 9447
fieldSpec:
  - 2456abfghknps
  - 8806abfghknps
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Process the main title values \(MARC `245` and parallel `880`, if applicable\).

    1.  Join the string value of MARC `245` subfields `abfghknps` \(excluding `$6`\) with a whitespace character.

    2.  If applicable, join the string value of parallel MARC `880` subfields `abfghknps` \(excluding `$6`\) with a whitespace character.

    3.  Save the values as `primary_name` or `parallel_primary_name` \(if applicable\).

2.  Assign the `primary_name` and `parallel_primary_name` values to the [content-level record](../../glossary/content_level_record.md).

    `9447`

    ```
    
      "id": "https://lux.collections.yale.edu/data/text/c0fd4d84-4b50-496d-a56e-ebf952f8dcf2",
      "type": "LinguisticObject",
      "_label": "韓國 의 선비 文化",
      "identified_by": [
        {
          "type": "Name",
          "content": "Hanʼguk ŭi sŏnbi munhwa",
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
          "content": "韓國 의 선비 文化",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ],
          "language": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/70cb6397-2b2f-400c-b887-70fd80969c8b",
              "type": "Language",
              "_label": "und"
            }
          ]
        }
      ]
    }
    ```

3.  Assign the `primary_name` and `parallel_primary_name` values to each [carrier-level record](../../glossary/carrier_level_record.md).

4.  If the carrier-level record represents a [bound-with resource](../../glossary/bound-with_resource.md), use the call number as the `primary_name` of the carrier-level record.

5.  Concatenate the call number with the following phrase in square brackets using a whitespace character: `[multiple objects bound in a single volume]`.

    `7001117`

    ```
    {
      "identified_by": [
        {
          "type": "Name",
          "content": "Ip Si578 1 [Sterling Memorial Library] [multiple objects bound in a single volume]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ]
    }
    ```

6.  If the carrier-level record is an item record, inspect the `Enum` and `Chron` fields.

7.  If there is textual content in both the `Enum` and `Chron` fields, extract the values as `enum_val` and `chron_val`.

    1.  Concatenate `enum_val` and `chron_val` with a comma and whitespace character.

    2.  Surround the concatenated value with square brackets.

    3.  Save the value as `enum_chron_val`.

    4.  Concatenate `primary_name`/`parallel_primary_name` and `enum_chron_val` with a whitespace character.

    `12104059 [item]`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/object/c0fd4d84-4b50-496d-a56e-ebf952f8dcf2",
      "type": "HumanMadeObject",
      "_label": "Transactions [v.6, 1812]",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300028051",
          "type": "Type",
          "_label": "Journals and Periodicals",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300215390",
              "type": "Type",
              "_label": "Type of Object"
            }
          ]
        }
      ],  
      "identified_by": [
        {
          "type": "Name",
          "content": "Transactions [v.6, 1812]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "ils:yul:mfhd:13867637",
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "carried_out_by": [
                {
                  "id": "https://lux.collections.yale.edu/data/group/yale-university-library",
                  "type": "Group",
                  "_label": "Yale University Library"
                }
              ]
            }
          ],
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435704",
              "type": "Type",
              "_label": "System-Assigned Number"
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "ils:yul:item:12104059",
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "carried_out_by": [
                {
                  "id": "https://lux.collections.yale.edu/data/group/yale-university-library",
                  "type": "Group",
                  "_label": "Yale University Library"
                }
              ]
            }
          ],
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435704",
              "type": "Type",
              "_label": "System-Assigned Number"
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "A48 020 [v.6, 1812] [Library Shelving Facility (LSF)]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311706",
              "type": "Type",
              "_label": "Call Number"
            }
          ]
        }
      ],
      "carries": [
        {
          "id": "https://lux.collections.yale.edu/data/text/416165c2-1108-4acd-b7ab-008f773a2ba3xyz",
          "type": "LinguisticObject",
          "_label": "Transactions"
        }
      ]
    }
    ```

8.  If there is textual content in only one of the `Enum` and `Chron` fields, extract the value.

    1.  Surround the extracted value with square brackets.

    2.  Save the value as `enum_val` or `chron_val`.

    3.  Concatenate `primary_name`/`parallel_primary_name` and `enum_val` or `chron_val` with a whitespace character.

    `10962371 [item]`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/digital/0283cba8-169b-4950-bb88-5ba3cdd4ca1d",
      "type": "DigitalObject",
      "_label": "弘前藩庁日記ひろひよみ : 気象・災害等の記述を中心に. Vol.2, (1741年-1868年) [CD]",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300028566",
          "type": "Type",
          "_label": "Software Applications",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435443",
              "type": "Type",
              "_label": "Type of Object"
            }
          ]
        }
      ],
      "identified_by": [
        {
          "type": "Identifier",
          "content": "QC990.J32 H576 2014 CD [CD] [Library Shelving Facility (LSF)]",
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
          "content": "Hirosaki hanchō nikki hiroiyomi : kishō saigai nado no kijutsu o chūshin ni. Vol.2, (1741-nen-1868-nen) [CD]",
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
          "content": "弘前藩庁日記ひろひよみ : 気象・災害等の記述を中心に. Vol.2, (1741年-1868年) [CD]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ],
          "language": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/70cb6397-2b2f-400c-b887-70fd80969c8b",
              "type": "Language",
              "_label": "und"
            }
          ]
        }
      ],
      "digitally_carries": [
        {
          "id": "https://lux.collections.yale.edu/data/text/example-content1",
          "type": "LinguisticObject",
          "_label": "Hirosaki hanchō nikki hiroiyomi : kishō saigai nado no kijutsu o chūshin ni. Vol.2, (1741-nen-1868-nen)"
        }
      ]
    }
    ```

9.  If the carrier-level record is a holdings record \(i.e., there are no attached item records\), look for `866`, `867`, or `868` fields in the holdings record.

10. Process each `866`, `867`, or `868` as a *separate* carrier-level resource.

    1.  For each `866`, `867`, or `868` \(“textual holdings”\) field, extract the value as `holdings_val`.

    2.  If the `holdings_val` each with a comma, trim the comma from the end of `holdings_val`.

    3.  Surround `holdings_val` with square brackets.

    4.  Concatenate `primary_name`/`parallel_primary_name` and `holdings_val` with a whitespace character.

    `4082244 [MFHD]`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://linked-art.library.yale.edu/node/a436dbcb-fbd0-4364-a27f-1f9a6e79f475",
      "type": "HumanMadeObject",
      "_label": "The Massachusetts gazette, and the Boston post-boy and advertiser [no.229(1762:Jan.4)]",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300026656",
          "type": "Type",
          "_label": "Newspapers",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435443",
              "type": "Type",
              "_label": "Type of Object"
            }
          ]
        }
      ],
      "identified_by": [
        {
          "type": "Identifier",
          "content": "ils:yul:mfhd:4082244",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435704",
              "type": "Type",
              "_label": "System-Assigned Number"
            }
          ],
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "carried_out_by": [
                {
                  "id": "https://linked-art.library.yale.edu/node/0ed3ecaa-4483-4e4e-a015-a6d5ca448106",
                  "type": "Group",
                  "_label": "Yale University Library"
                }
              ]
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "Folio AN22 B7 M383 [no.229(1762:Jan.4)] [Beinecke Library]",
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
          "content": "The Massachusetts gazette, and the Boston post-boy and advertiser [no.229(1762:Jan.4)]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "member_of": [
        {
          "id": "https://linked-art.library.yale.edu/node/9d83b3ef-e184-4a46-a2b3-db895d9948bcxyz",
          "type": "Set",
          "_label": "Beinecke Library"
        }
      ],
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "In the Library",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300133046",
              "type": "Type",
              "_label": "Access Statement",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ]
        }
      ],
      "carries": [
        {
          "id": "https://linked-art.library.yale.edu/node/f74f5b5c-a8fd-4c24-85bf-8f09f7ee37eb",
          "type": "LinguisticObject",
          "_label": "The Massachusetts gazette, and the Boston post-boy and advertiser"
        }
      ]
    }
    ```


**Parent topic:**[Names](../../tasks/names-and-labels/names.md)

