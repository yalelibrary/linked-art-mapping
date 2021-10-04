---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Groups as subjects

Entities extracted from MARC 61X fields.

## Source data

```
---
name: GroupsAsAgents
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
  - 61004abcdeg
  - 61104acdegjnqu
  - 69304abcdeg
  - 69404acdegjnqu  
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  Add an embedded reference to the Group entity within the top-level resource.

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → about → id`|Must match the `id` of the top-level resource| |
    |`root → about → type`| |`Group`|
    |`root → about → _label`| |Must match the `label` of the top-level resource|

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


**Parent topic:**[Top-level group entities](../concepts/top_level_group_entities.md)

