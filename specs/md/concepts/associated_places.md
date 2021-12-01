---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Associated places

MARC fields `751` and `752` are both used to record associated places that are “related to a particular attribute of the described item, e.g., the place of publication for a rare book, place of distribution, place of a university to which a dissertation is submitted, place of an event such as a conference, etc.”

Field `752`, however, represents a “hierarchical place name.” Therefore, top-level place resources derived from `752` entries should be constructed using `created_by → influenced_by` facets, following the same pattern presented in the [subject headings specification](subject_headings.md).

## Source data

```
---
name: AssociatedPlaces
sampleBibs:
  - 693 # 752
  - 35599 # 752
  - 1066178 # 751
  - 4692408 # 752
# Source data fields
fieldSpec:  
  - 751014ae
  - 752014abcdefgh    
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Generate and store the top-level place resources, each identified by an IRI.

    1.  For `751`, select the value of `a`.

    2.  For `752`, join all subfields **except** for those listed below to create a key for matching and merging.

        |Fields|Subfields|
        |------|---------|
        |All|014e|

    3.  [Normalize](../glossary/normalization.md) and match string values.

    4.  If a source data field in MARC includes a subfield `0` or `1` with an IRI, output an `equivalent` reference.

    5.  For `752`, within the top-level resource for the full place entry, model each subfield in the heading as a facet.

    6.  Generate a top-level place resource for each unique facet.

    `35599`

    **Note:** IRIs in the example below are for illustration only and should be replaced with system-generated UUIDs.

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/752-place",
      "type": "Place",
      "_label": "United States--New York (State)--New York--Brooklyn",
      "identified_by": [
        {
          "type": "Name",
          "content": "United States--New York (State)--New York--Brooklyn"
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/place/752-place-1",
            "type": "Place",
            "_label": "United States"
          },
          {
            "id": "https://lux.collections.yale.edu/data/place/752-place-2",
            "type": "Place",
            "_label": "New York (State)"
          },
          {
            "id": "https://lux.collections.yale.edu/data/place/752-place-3",
            "type": "Place",
            "_label": "New York"
          },
          {
            "id": "https://lux.collections.yale.edu/data/place/752-place-4",
            "type": "Place",
            "_label": "Brooklyn"
          }
        ]
      }
    }
    
    ```

2.  Add an embedded reference to the place entity within the record-level resource.

    1.  The `_label` of the `attributed_by` structure should always be `associated place`.

    2.  As the `_label` of the nested place entity, take the value of the top-level entity label.

        `1066178`

        ```
        {
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "_label": "associated place",
              "assigned": {
                "id": "https://lux.collections.yale.edu/data/place/d6997bff-a0d4-4394-93b6-fb9e6402bc13",
                "type": "Place",
                "_label": "Gateshead, England"
              }
            }
          ]
        }
        ```


**Parent topic:**[Top-level Place entities](../concepts/top_level_place_entities.md)

