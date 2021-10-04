---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu, tt434]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Chronological facets

Resources extracted from MARC 6XXy.

## Source data

```
---
name: ChronologicalFacets
sampleBibs:
  - 9564880
  - 12164046
# Source data fields
fieldSpec:
  - 600y
  - 610y
  - 611y
  - 630y
  - 650y
  - 651y
  - 655y
  - 690y
  - 691y
  - 692y
  - 693y
  - 694y
  - 695y
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  Generate and store the top-level chronological facets, each identified by an IRI.

    1.  Create a key for merging.

    2.  Normalize and merge each unique string value.

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → id`|Resource IRI| |
    |`root → type`|Semantic type of entity|`Period`|
    |`root → _label`|Label of facet| |
    |`root → identified_by → type`| |`Name`|
    |`root → identified_by → content`|Same as `root → _label`| |

    `12164046`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/event/73c0ba3c-e469-4969-be1c-0479c856add3",
      "type": "Period",
      "_label": "World War, 1914-1918",
      "identified_by": [
        {
          "type": "Name",
          "content": "World War, 1914-1918"
        }
      ]
    }
    ```

2.  Add an embedded reference to the facet resource within the top-level resource for each referring subject heading.

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → created_by → influenced_by → id`|Must match the `id` of the top-level resource| |
    |`root → type`|Must match the `type` of the top-level resource|`Period`|
    |`root → _label`|Must match the `_label` of the top-level resource| |

    `12164046`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/003c6a29-8b30-4e90-9664-ea7d65f8e4ec",
      "type": "Type",
      "_label": "Russia. Voennyĭ flot--History--World War, 1914-1918",
      "identified_by": [
        {
          "type": "Name",
          "content": "Russia. Voennyĭ flot--History--World War, 1914-1918"
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/group/9110fd4b-6992-4e75-89f9-cae80221d79c",
            "type": "Group",
            "_label": "Russia. Voennyĭ flot"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/d43ab750-6e8d-4f7c-b3e2-d5a8dc134a37",
            "type": "Type",
            "_label": "History"
          },
          {
            "id": "https://lux.collections.yale.edu/data/event/73c0ba3c-e469-4969-be1c-0479c856add3",
            "type": "Period",
            "_label": "World War, 1914-1918"
          }
        ]
      }
    }
    ```


**Parent topic:**[Events](../../concepts/events.md)

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

