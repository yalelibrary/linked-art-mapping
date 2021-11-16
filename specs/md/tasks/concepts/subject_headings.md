---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu, tt434]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Subject headings

Resources extracted from MARC 6XX entries.

## Source data

```
---
name: SubjectHeadings
sampleBibs:
  - 9564880
  - 13146411
# Source data fields
fieldSpec:
  - 60004abcdegjqvxyz
  - 61004abcdegvxyz
  - 61104acdegjnquvxyz
  - 6300adfhklmnoprstvxyz
  - 65004abcdegvxyz
  - 65104abcdfghvxyz
  - 65504abcvxyz
  - 69004abcdegvxyz
  - 69104abcdfghvxyz
  - 69204abcdegjqvxyz
  - 69304abcdegvxyz
  - 69404acdegjnquvxyz
  - 6950adfhklmnoprstvxyz  
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Generate and store the top-level chronological facets, each identified by an IRI.

    1.  Join all subfields \(except for `0`\) to create a key for merging.

    2.  Normalize and merge each unique string value.

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → id`|Concept IRI| |
    |`root → type`|Semantic type of concept|`Type`|
    |`root → _label`|Label of precoordinated subject heading, joined with double hyphens| |
    |`root → equivalent → id`|Reference to IRI from `$0`, if applicable| |
    |`root → equivalent → type`|Reference to resource type from `$0`, if applicable| |
    |`root → identified_by → type`| |`Name`|
    |`root → identified_by → content`|Same as `root → _label`| |
    |`root → identified_by → classified_as → id`| |[http://vocab.getty.edu/aat/300404670](http://vocab.getty.edu/aat/300404670)|
    |`root → identified_by → classified_as → type`| |`Type`|
    |`root → identified_by → classified_as → _label`| |`Primary Name`|
    |`root → created_by → influenced_by → id`|Concept IRI for facet concept| |
    |`root → created_by → influenced_by → type`|Semantic type of concept facet. See the [facet type mapping](../../concepts/subject_headings.md#facet_types_table) below.| |
    |`root → created_by → influenced_by → _label`|Facet label| |

2.  Within the top-level resource for the full subject heading, model each subdivision in the heading as a facet.

3.  Generate a top-level resource for each unique facet.

    1.  Create facets by normalizing and merging the string value \(label\) of each facet resource according to the facet value mapping table below.

    2.  For rows with multiple subfields, join the subfields with a whitespace character.

        |MARC tag|Subfields|
        |--------|---------|
        |6XX|v|
        |6XX|x|
        |6XX|y|
        |6XX|z|
        |600|abcdgjq|
        |610|abcdg|
        |611|acdegnqu|
        |630|adfhklmnoprst|
        |650|abcdg|
        |651|abcdfgh|
        |690|abcdg|
        |691|abcdfgh|
        |692|abcdgjq|
        |693|abcdg|
        |694|acdgnqu|
        |695|adfhklmnoprst|

    3.  Determine the `type` value for each facet from the tag and subfield values in MARC according to the facet type mapping table below.

        |MARC values|Type|
        |-----------|----|
        |6XXvx|Type|
        |6XXy|Period|
        |6XXz|Place|
        |600abcdgjq|Person|
        |610abcdg|Group|
        |611acdegnqu|Group|
        |630adfhklmnoprst|LinguisticObject|
        |650abcdg|Type|
        |651abcdfgh|Place|
        |690abcdg|Type|
        |691abcdfgh|Place|
        |692abcdgjq|Person|
        |693abcdg|Group|
        |694acdegnqu|Group|
        |695adfhklmnoprst|LinguisticObject|

    `9564880`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/event/92a599a2-2117-43f9-be3e-6e07f36cb2a5",
      "type": "Period",
      "_label": "2nd century",
      "identified_by": [
        {
          "type": "Name",
          "content": "2nd century"
        }
      ]
    }
    ```

4.  Join the string values of the facets with double hyphens \(`--`\) to output the `_label` and `content` values of the full precoordinated heading.

5.  Add an embedded reference to the facet resources within the top-level resource for the full heading.

    `9564880`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/24f1b754-9566-4f38-8c61-9ce4082606aa",
      "type": "Type",
      "_label": "Death--Religious aspects--Christianity--History--2nd century",
      "identified_by": [
        {
          "type": "Name",
          "content": "Death--Religious aspects--Christianity--History--2nd century"
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/concept/c54ba0ac-c106-4afe-8007-cb4a34cf0bd7",
            "type": "Type",
            "_label": "Death"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/b273c64d-a9bb-4c2e-bb3f-5c13a6825a55",
            "type": "Type",
            "_label": "Religious aspects"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/33a05e84-57bc-4f1d-a792-0de7758bd0d8",
            "type": "Type",
            "_label": "Christianity"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/d43ab750-6e8d-4f7c-b3e2-d5a8dc134a37",
            "type": "Type",
            "_label": "History"
          },
          {
            "id": "https://lux.collections.yale.edu/data/event/92a599a2-2117-43f9-be3e-6e07f36cb2a5",
            "type": "Period",
            "_label": "2nd century"
          }
        ]
      }
    }
    ```

6.  If a 6XX field in MARC includes a `$0` with an IRI, output an `equivalent` reference.

    `13146411`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/2dba70e6-3702-4bbc-953c-1fdee7460594",
      "type": "Type",
      "_label": "Earth (Planet)--Maps",
      "identified_by": [
        {
          "type": "Name",
          "content": "Earth (Planet)--Maps",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "equivalent": [
        {
          "id": "http://id.loc.gov/authorities/subjects/sh2013000103",
          "type": "Type"
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/place/f0c5212e-e671-4c59-a745-581b350f191d",
            "type": "Place",
            "_label": "Earth (Planet)"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/c5974fce-ed0d-4556-a2f6-bd98965ffc50",
            "type": "Type",
            "_label": "Maps"
          }
        ]
      }
    }
    ```

7.  In each referring record-level resource \(`LinguisticObject`, `VisualItem`, or `DigitalObject`\), add an embedded reference to the Concept entity.

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → about → id`|Must match the `id` of the top-level resource| |
    |`root → about → type`|Must match the `type` of the top-level resource| |
    |`root → about → _label`|Must match the `_label` of the top-level resource| |

    `9564880`

    ```
    {
      "about": [
        {
          "id": "https://lux.collections.yale.edu/data/concept/c5ba671b-c41d-40f5-983f-beb38b75b5b2",
          "type": "Type",
          "_label": "Death--Religious aspects--Christianity"
        },
        {
          "id": "https://lux.collections.yale.edu/data/concept/24f1b754-9566-4f38-8c61-9ce4082606aa",
          "type": "Type",
          "_label": "Death--Religious aspects--Christianity--History--2nd century"
        }
      ]
    }
    ```


**Parent topic:**[Concepts](../../concepts/concepts.md)

**Related information**  


[600 \(Subject Added Entry-Personal Name\)](../../tables/600_bib_table.md)

[610 \(Subject Added Entry-Corporate Name\)](../../tables/610_bib_table.md)

[611 \(Subject Added Entry-Meeting Name\)](../../tables/611_bib_table.md)

[630 \(Subject Added Entry-Uniform Title\)](../../tables/630_bib_table.md)

[650 \(Subject Added Entry-Topical Term\)](../../tables/650_bib_table.md)

[651 \(Subject Added Entry-Geographic Name\)](../../tables/651_bib_table.md)

[653 \(Index Term-Uncontrolled\)](../../tables/653_bib_table.md)

[655 \(Index Term-Genre/Form\)](../../tables/655_bib_table.md)

[656 \(Index Term-Occupation\)](../../tables/656_bib_table.md)

[657 \(Index Term-Function\)](../../tables/657_bib_table.md)

[662 \(Subject Added Entry-Hierarchical Place Name\)](../../tables/662_bib_table.md)

[688 \(Subject Added Entry-Type of Entity Unspecified\)](../../tables/688_bib_table.md)

[690](../../tables/690_bib_table.md)

[691](../../tables/691_bib_table.md)

[692](../../tables/692_bib_table.md)

[693](../../tables/693_bib_table.md)

[694](../../tables/694_bib_table.md)

[695](../../tables/695_bib_table.md)

