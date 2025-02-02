---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: Assigned
---

# Complex subject/genre headings

Subject headings representing two or more entity types.

Apply these instructions when a `6XX` field includes any of the subdivision subfields `vxyz`.

**Note:** `600`, `610`, `611`, and `69X` entries--except for `695`--that include a subfield `t` should not be processed using this spec. See instead [Complex works](name_title_entries.md).

## Source data

```
---
name: ComplexSubjectHeadings
sampleBibs:
  - 9920561
  - 9564880
  - 3145537 # 630
  - 13146411
  - 15552027 # 651ag
# Source data fields
fieldSpec:
  - 60004abcdegjquvxyz
  - 61004abcdeguvxyz
  - 61104acdegjnquvxyz
  - 630014adfghklmnoprstvxyz
  - 65004abcdegvxyz
  - 651| 0|014aegvxyz
  - 65504abcvxyz
  - 69004abcdegvxyz
  - 691014aegvxyz         
  - 69204abcdegjquvxyz
  - 69304abcdeguvxyz
  - 69404acdegjnquvxyz
  - 695014adfghklmnoprstvxyz
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  For each unique source data value, generate and store a top-level resource identified by an IRI.

    1.  Ignore the following subfields when creating a key for matching and merging.

        |Fields|Subfields|
        |------|---------|
        |All|014|
        |All except X11 and 694|e|
        |X11 and 694|j|

    2.  Apply the following mapping table to create a key for matching and merging. For rows in the table with multiple subfields, join the subfields with a whitespace character.

        **Note:** `600`, `610`, `611`, and `69X` entries--except for `695`--that include a subfield `t` should not be processed using this spec. See instead [Complex works](name_title_entries.md).

        |Linked Art class|MARC tag|Subfields|
        |----------------|--------|---------|
        |Person|600|abcdgjqvxyz|
        |Group|600\|3\*\||abcdgjqvxyz|
        |Group|610|abcdgvxyz|
        |Group|611|acdegnquvxyz|
        |LinguisticObject|630|adfhklmnoprst|
        |Concept|650|abcdgvxyz|
        |Place|651\| 0\||agvxyz|
        |Type|655|avxyz|
        |Concept|690|abcdgvxyz|
        |Place|691|agvxyz|
        |Person|692|abcdgjqvxyz|
        |Group|693|abcdgvxyz|
        |Group|694|acdgnquvxyz|
        |LinguisticObject|695|adfhklmnoprst|

    3.  [Normalize](../../glossary/normalization.md) and match string values.

    4.  If a field includes a `$0` with an IRI, output an `equivalent` reference.

        **Note:** The `Type` of the `equivalent` reference should match the `Type` of the top-level resource.

2.  Within the top-level resource corresponding to the `6XX` field, model each subdivision in the heading as a facet.

3.  Generate a top-level resource for each unique facet.

    1.  Create facets by normalizing and matching the string value of each facet resource according to the facet value mapping table below.

    2.  For rows in the table with multiple subfields, join the subfields with a whitespace character.

        |MARC tag|Subfields|
        |--------|---------|
        |6XX|v|
        |6XX|x|
        |6XX|y|
        |6XX|z|
        |600|abcdgjq|
        |610|abcdg|
        |611|acdegnqu|
        |630|adfhklmnoprst|
        |650|abcdg|
        |651\|\*0\||a|
        |651\|\*0\||g|
        |655|a|
        |690|abcdg|
        |691|a|
        |691|g|
        |692|abcdgjq|
        |693|abcdg|
        |694|acdgnqu|
        |695|adfhklmnoprst|

    3.  Determine the `type` value for each facet from the tag and subfield values in MARC according to the facet type mapping table below.

        |MARC values|Type|
        |-----------|----|
        |6XXvx|Type|
        |6XXy|Period|
        |6XXz|Place|
        |600abcdgjq|Person|
        |600\|3\*\|abcdgjq|Group \[Family\]|
        |610abcdg|Group \[Organization\]|
        |611acdegnqu|Group \[Meeting\]|
        |630adfhklmnoprst|LinguisticObject|
        |650abcdg|Type|
        |651\|\*0\|a|Place|
        |651\|\*0\|g|Place|
        |655a|Type|
        |690abcdg|Type|
        |691a|Place|
        |691g|Place|
        |692abcdgjq|Person|
        |693abcdg|Group|
        |694acdegnqu|Group|
        |695adfhklmnoprst|LinguisticObject|

        **Note:** Top-level genre/form \(`655`\) resources should include a `Genre` classification, as shown in [Creators, contributors, standalone works, simple subject/genre headings, and associated places](simple_subject_headings.md).

        `9564880`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/event/92a599a2-2117-43f9-be3e-6e07f36cb2a5",
          "type": "Period",
          "_label": "2nd century",
          "identified_by": [
            {
              "type": "Name",
              "content": "2nd century",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404670",
                  "type": "Type",
                  "_label": "Primary Name"
                }
              ]
            }
          ]
        }
        ```

4.  When there are multiple geographic subdivisions \(`$z`\), apply the instructions in [Place hierarchies](hierarchical_places.md).

5.  Join the string values of the facets with space-surrounded double hyphens \(`--`\) to output the `_label` and `content` values of the full precoordinated heading.

6.  Add an embedded reference to the facet resources within the top-level resource for the full heading.

7.  Process `6XX` entries for complex subject headings.

    When `651a` is immediately followed by subfield `$z` or when two or more geographic subdivisions \(`$z`\) are present, only a single facet should be output to represent the last \(most specific\) place entity in the heading.

    Include the value of all subdivisions in the `_label` and `Primary Name` for the concept, but do not generate a facet resource for intermediate geographic subdivisions.

    `3802854`

    ```
    650 0 $a Folk songs, Romanian $z Romania $z Loviștea Region $v Texts.
    ```

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/70db3ab1-33fa-4123-8217-2d8c85576aa9",
      "type": "Type",
      "_label": "Folk songs, Romanian -- Romania -- Loviștea Region -- Texts",
      "identified_by": [
        {
          "type": "Name",
          "content": "Folk songs, Romanian -- Romania -- Loviștea Region -- Texts",
           "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/concept/75bb7d9f-2d42-4219-8790-62eacbf10f7a",
            "type": "Type",
            "_label": "Folk songs, Romanian"
          },     
          {
            "id": "https://lux.collections.yale.edu/data/place/23e3171a-f151-4c54-aee3-afb13109da61",
            "type": "Place",
            "_label": "Loviștea Region"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/f27fdcfa-e945-4a86-a623-57c418c8780d",
            "type": "Type",
            "_label": "Texts"
          }
        ]
      }
    }
    ```

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/23e3171a-f151-4c54-aee3-afb13109da61",
      "type": "Place",
      "_label": "Loviștea Region",
      "identified_by": [
        {
          "type": "Name",
          "content": "Loviștea Region",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "part_of": [
        {
          "id": "https://lux.collections.yale.edu/data/place/8659a573-f14f-4cc9-ab3d-41b56ddb9d78",
          "type": "Place",
          "_label": "Romania"
        }
      ]
    }
    ```

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/8659a573-f14f-4cc9-ab3d-41b56ddb9d78",
      "type": "Place",
      "_label": "Romania",
      "identified_by": [
        {
          "type": "Name",
          "content": "Romania",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ]
    }
    ```

    `9564880`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/24f1b754-9566-4f38-8c61-9ce4082606aa",
      "type": "Type",
      "_label": "Death -- Religious aspects -- Christianity -- History -- 2nd century",
      "identified_by": [
        {
          "type": "Name",
          "content": "Death -- Religious aspects -- Christianity -- History -- 2nd century",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/concept/c54ba0ac-c106-4afe-8007-cb4a34cf0bd7",
            "type": "Type",
            "_label": "Death"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/b273c64d-a9bb-4c2e-bb3f-5c13a6825a55",
            "type": "Type",
            "_label": "Religious aspects"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/33a05e84-57bc-4f1d-a792-0de7758bd0d8",
            "type": "Type",
            "_label": "Christianity"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/d43ab750-6e8d-4f7c-b3e2-d5a8dc134a37",
            "type": "Type",
            "_label": "History"
          },
          {
            "id": "https://lux.collections.yale.edu/data/event/92a599a2-2117-43f9-be3e-6e07f36cb2a5",
            "type": "Period",
            "_label": "2nd century"
          }
        ]
      }
    }
    ```

    `3145537`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/06eddac8-f6b9-442c-a0e5-c7a5a2c55ba1",
      "type": "Type",
      "_label": "Qurʼan -- Hermeneutics -- History",
      "identified_by": [
        {
          "type": "Name",
          "content": "Qurʼan -- Hermeneutics -- History"
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/text/1a429a8f-b77c-4956-811c-c9fc5237eb8d",
            "type": "LinguisticObject",
            "_label": "Qurʼan"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/71abaf42-a479-41bf-bd6f-2cf6aeca2060",
            "type": "Type",
            "_label": "Hermeneutics"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/d43ab750-6e8d-4f7c-b3e2-d5a8dc134a37",
            "type": "Type",
            "_label": "History"
          }
        ]
      }
    }
    ```

8.  If a `6XX` field in MARC includes a `$0` with an IRI, output an `equivalent` reference.

    `13146411`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/2dba70e6-3702-4bbc-953c-1fdee7460594",
      "type": "Type",
      "_label": "Earth (Planet) -- Maps",
      "identified_by": [
        {
          "type": "Name",
          "content": "Earth (Planet) -- Maps",
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
          "id": "http://id.loc.gov/authorities/subjects/sh2013000103",
          "type": "Type"
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/place/f0c5212e-e671-4c59-a745-581b350f191d",
            "type": "Place",
            "_label": "Earth (Planet)"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/c5974fce-ed0d-4556-a2f6-bd98965ffc50",
            "type": "Type",
            "_label": "Maps"
          }
        ]
      }
    }
    ```

9.  In each referring record-level resource \(`LinguisticObject`, `Set`, `VisualItem`\), add an embedded reference to the concept entity.

    1.  For concept \(`Type`\) entities, see [Subject and genre/form headings](subject_headings.md).

    2.  For associated places, see [Associated places](../../concepts/associated_places.md).

    3.  For places as subjects, see [Places as subjects](../../concepts/places_as_subjects.md).

    4.  For people as subjects, see [People as subjects](../../concepts/people_as_subjects.md).

    5.  For groups as subjects, see [Groups as subjects](../../concepts/groups_as_subjects.md).

    6.  For works as subjects, see [Works as subjects](../name-title/works_as_subjects.md).


**Parent topic:**[Related entities](../../tasks/related_entities.md)

