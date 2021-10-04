---
author: [tt434, timothy.thompson@yale.edu, tt434]
---

# Top-level group entities

Group entities extracted from both subject \(6XX\) and agent \(11X and 71X\) fields.

## Source data

```
---
name: Groups
sampleBibs:
  - 7 # 710
  - 9 # 710
  - 11 # 110
  - 19 # 111
  - 38 # 110
  - 68 # 610
  - 127 # 111
  - 162 # 610
  - 422 # 693
  - 426 # 711
  - 607 # 611
  - 947 # 711
  - 1029 # 611  
  - 9292 # 693
  - 614880 # 694
  - 838469 # 694
# Source data fields
fieldSpec:
  - 11004abcdg
  - 11104acdgjnqu
  - 61004abcdgvxyz
  - 61104acdegnquvxyz
  - 69304abcdg
  - 69404acdegnqu
  - 7100abcdg
  - 71104acdegnquvxyz       
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  Generate and store the top-level concept resources, each identified by an IRI.

    1.  Join all subfields to create a key for merging.

    2.  Normalize and merge each unique string value.

    3.  If a source data field in MARC includes a `$0` with an IRI, output an `equivalent` reference.

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → id`|Resource IRI| |
    |`root → type`|Semantic type of entity|`Group`|
    |`root → _label`|Label of Group| |
    |`root → classified_as → id`|Concept IRI used to classify the resource|[http://vocab.getty.edu/aat/300025948](http://vocab.getty.edu/aat/300025948)|
    |`root → classified_as → type`| |`Type`|
    |`root → classified_as → _label`| |`Organization`|
    |`root → identified_by → type`| |`Name`|
    |`root → identified_by → content`|Same as `root → _label`| |
    |`root → equivalent → id`|Reference to IRI from `$0`, if applicable| |
    |`root → equivalent → type`|Reference to resource type from `$0`, if applicable|`Group`|
    |`root → equivalent → classified_as → id`|Concept IRI used to classify the equivalent resource|[http://vocab.getty.edu/aat/300025948](http://vocab.getty.edu/aat/300025948)|
    |`root → equivalent → classified_as → type`| |`Type`|
    |`root → equivalent → classified_as → _label`| |`Organization`|

    `7`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/group/ffd90912-408f-4416-a5b8-b66dde22a224",
      "type": "Group",
      "_label": "University of Virginia",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300025948",
          "type": "Type",
          "_label": "Organization"
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "University of Virginia"
        }
      ],
      "equivalent": [
        {
          "id": "http://id.loc.gov/authorities/names/n79053979",
          "type": "Group",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300025948",
              "type": "Type",
              "_label": "Organization"
            }
          ]
        }  
      ]
    }
    ```


-   **[Groups as agents](../concepts/groups_as_agents.md)**  
Entities extracted from MARC 11X and 71X fields.
-   **[Groups as subjects](../concepts/groups_as_subjects.md)**  
Entities extracted from MARC 61X fields.

**Parent topic:**[Groups](../concepts/groups.md)

