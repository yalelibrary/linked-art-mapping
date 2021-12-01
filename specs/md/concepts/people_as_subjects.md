---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: 
---

# People as subjects

Entities extracted from MARC 600 fields.

## Source data

```
---
name: PeopleAsSubjects
sampleBibs:
  - 7 # 692
  - 14 # 600
# Source data fields
fieldSpec:
  - 600014abcdgjqvxyz
  - 692014abcdgjqvxyz
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Add an embedded reference to the person entity within the record-level resource.

    **Note:** If a MARC `600` or `692` entry includes subdivision subfields \(`vxyz`\), then the heading should be treated as a concept \(`Type`\) entity: see [Subject headings](subject_headings.md).

    1.  Process concept/person references.

        `7`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/46c465f1-3c49-4a5d-bd4c-01e2146cba44",
              "type": "Type",
              "_label": "Colvert, James B.--Autograph"
            },
            {
              "id": "https://lux.collections.yale.edu/data/concept/7925767c-c120-49b6-977d-bce3d34750db",
              "type": "Type",
              "_label": "Bowers, Fredson--Autograph"
            }
          ]
        }
        ```

    2.  Process direct person references.

        `907221`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/person/25ae094b-ee19-465b-aaf1-2ec08ce28bfd",
              "type": "Person",
              "_label": "Perizonius, Jacobus, 1651-1715"
            }
          ]
        }
        ```


**Parent topic:**[Top-level Person entities](../concepts/top_level_person_entities.md)

