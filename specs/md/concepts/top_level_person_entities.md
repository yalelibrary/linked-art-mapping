---
author: [tt434, timothy.thompson@yale.edu, tt434]
---

# Top-level Person entities

Person entities extracted from both subject \(600\) and agent \(100 and 700\) fields.

## Source data

```
---
name: PersonEntities
sampleBibs:
  - 693 # 100, 700
# Source data fields
fieldSpec:
  - 10001abcdgjq
  - 70001abcdgjq
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Generate and store the top-level person resources, each identified by an IRI.

    1.  Join all subfields \(except for `0` or `1`\) to create a key for merging.

    2.  Normalize and merge each unique string value.

    3.  If a source data field in MARC includes a subfield `0` or `1` with an IRI, output an `equivalent` reference.

    `693`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/person/70ef44e6-621f-4edb-a13d-a7f2149229d5",
      "type": "Person",
      "_label": "Ricœur, Paul",
      "identified_by": [
        {
          "type": "Name",
          "content": "Ricœur, Paul",
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
          "id": "http://id.loc.gov/authorities/names/n79056642",
          "type": "Person"
        }
      ]
    }
    ```


-   **[People as agents](../concepts/people_as_agents.md)**  
Entities extracted from MARC 11X and 71X fields.
-   **[People as subjects](../concepts/people_as_subjects.md)**  
Entities extracted from MARC 61X fields.

**Parent topic:**[People](../concepts/people.md)

