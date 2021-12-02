---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Places as subjects

## Source data

```
---
name: PlacesAsSubjects
sampleBibs:
  - 105 # 651, 651z
  - 2792 # 651$0
  - 6017172 # direct
  - 2820839 # 691
# Source data fields
fieldSpec:
  - 651| 0|014aegvxyz
  - 691014aegvxyz         
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Add an embedded reference to the place entity within the record-level resource.

    **Note:** If a MARC `6XX` entry includes subdivision subfields \(`vxyz`\), then the heading should be treated as a concept \(`Type`\) entity: see [Subject headings](subject_headings.md).

    1.  Process concept/place references.

        `105`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/a87f49e0-9834-4eb6-9d92-b80b36370d16",
              "type": "Type",
              "_label": "Dissertations, Academic--United States--Bibliography"
            },
            {
              "id": "https://lux.collections.yale.edu/data/concept/ee403f31-4429-4808-8c18-a6cc677eb89a",
              "type": "Type",
              "_label": "Asia--Study and teaching--United States--Bibliography"
            },
            {
              "id": "https://lux.collections.yale.edu/data/concept/90c1b0c3-a264-4117-8da5-9847c74fbf92",
              "type": "Type",
              "_label": "Asia--Study and teaching--United States"
            }
          ]
        }
        ```

    2.  Process direct place references.

        `6017172`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/place/ff9095c9-db47-423d-938b-5c2e3fe9e177",
              "type": "Place",
              "_label": "Aleppo (Syria)"
            }
          ]
        }
        ```


**Parent topic:**[Top-level Place entities](../concepts/top_level_place_entities.md)

