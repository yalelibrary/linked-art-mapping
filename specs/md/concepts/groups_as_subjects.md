---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Groups as subjects

Entities extracted from MARC 61X fields.

## Source data

```
---
name: GroupsAsSubjects
sampleBibs:
  - 68 # 610
  - 162 # 610
  - 422 # 693
  - 607 # 611
  - 947 # 711
  - 1029 # 611          
  - 9292 # 693
  - 614880 # 694
  - 838469 # 694
# Source data fields
fieldSpec:
  - 610014abcdegvxyz
  - 611014acdegjnquvxyz
  - 693014abcdegvxyz
  - 694014acdegjnquvxyz  
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Add an embedded reference to the group entity within the top-level resource.

    **Note:** If a MARC `6XX` entry includes subdivision subfields \(`vxyz`\), then the heading should be treated as a concept \(`Type`\) entity: see [Subject headings](subject_headings.md).

    1.  Process concept/group references.

        `7731`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/54f5b059-a062-426a-a554-fe123c479779",
              "type": "Type",
              "_label": "Lebanon. Majlis al-Nūwāb--Elections--1968"
            }
          ]
        }
        ```

    2.  Process direct group references.

        `68`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/group/a3d54906-5375-46a0-b0df-d6be7d6ecb7f",
              "type": "Group",
              "_label": "United States. National Archives and Records Service"
            }
          ]
        }
        ```


**Parent topic:**[Top-level Group entities](../concepts/top_level_group_entities.md)

