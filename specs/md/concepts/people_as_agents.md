---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: 
---

# People as agents

Entities extracted from MARC 100 and 700 fields.

## Source data

```
---
name: PeopleAsAgents
sampleBibs:
  - 907221
# Source data fields
fieldSpec:
  - 110014abcdeg
  - 111014acdegjnqu
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Add an embedded reference to the Person entity within the top-level resource.

    `907221`

    ```
    {
      "created_by": {
        "type": "Creation",
        "part": [
          {
            "type": "Creation",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/72f4b237-12f8-4854-bd96-e1094ee56bb2",
                "type": "Person",
                "_label": "Meijer, Th. J."
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

    `693`

    ```
    {
      "created_by": {
        "type": "Creation",
        "part": [
          {
            "type": "Creation",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/70ef44e6-621f-4edb-a13d-a7f2149229d5",
                "type": "Person",
                "_label": "Ricœur, Paul"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/81b7e2c2-b7bb-4bcb-a806-9bfc1838e317",
                "type": "Type",
                "_label": "author"
              }
            ]
          },
          {
            "type": "Creation",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/9011fee1-8916-4117-a07b-1519667f121d",
                "type": "Person",
                "_label": "Savage, Denis"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/271d291f-0d42-4abf-bf43-070b241edc98",
                "type": "Type",
                "_label": "translator"
              }
            ]
          },
          {
            "type": "Creation",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/group/cdbe8c98-a3a6-4f7e-a20d-698cbe87dcc2",
                "type": "Group",
                "_label": "Samuel R. Delany Library (Beinecke Rare Book and Manuscript Library). Working Library"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/e7e0a406-3b6c-4a89-b6c7-96536c08553c",
                "type": "Type",
                "_label": "contributor"
              }
            ]
          }
        ]
      }
    }
    ```


**Parent topic:**[Top-level Person entities](../concepts/top_level_person_entities.md)

