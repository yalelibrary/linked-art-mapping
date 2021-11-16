---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu, tt434]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Groups as agents

Entities extracted from MARC 11X and 71X fields.

## Source data

```
---
name: GroupsAsAgents
sampleBibs:
  - 7 # 710
  - 9 # 710
  - 11 # 110
  - 19 # 111
  - 38 # 110
  - 127 # 111
  - 426 # 711
  - 947 # 711
# Source data fields
fieldSpec:
  - 11001abcdeg
  - 11101acdegjnqu
  - 71001abcdeg
  - 71101acdegjnqu
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  Add an embedded reference to the Group entity within the top-level resource.

    **Note:** The role of the Group entity is derived from `$e` for MARC 110 and 710 and from `$j` for MARC 111 and 711. When those subfields are absent, a generic role of `creator` is assigned when 11X is the source or `contributor` when 71X is the source.

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → created_by → type`|Type of the related activity|`Creation`|
    |`root → created_by → part → type`| |`Creation`|
    |`root → created_by → part → carried_out_by → id`|IRI of the Group entity| |
    |`root → created_by → part → carried_out_by → type`| |`Group`|
    |`root → created_by → part → carried_out_by → _label`|Must match the label of the top-level Group entity| |
    |`root → created_by → part → classified_as → id`|Concept IRI used to classify the role of the Group in the record-level resource| |
    |`root → created_by → part → classified_as → type`| |`Type`|
    |`root → created_by → part → classified_as → _label`|Label of the concept used to classify the role of the Group in the record-level resource| |

    `12164046`

    ```
    {
      "created_by": {
        "type": "Creation",
        "part": [
          {
            "type": "Creation",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/group/1bd89c27-47b9-40f0-8023-568af073edbd",
                "type": "Group",
                "_label": "International Congress for Logic, Methodology, and Philosophy of Science (3d : 1967 : Amsterdam)"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/9d2c734e-afd3-44bd-972d-8cf441423edc",
                "type": "Type",
                "_label": "creator"
              }
            ]
          }
        ]
      }
    }
    ```


**Parent topic:**[Top-level Group entities](../concepts/top_level_group_entities.md)

