---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
---

# System Control Numbers \(OCLC Numbers\)

System number used by OCLC to manage records in the WorldCat system.

## Source data

```
---
name: OclcNumber
sampleBibs:
  - 4
  - 2395
  - 3802861
  - 907208
  - 15589896
fieldSpec: 
  - 035az
  - 079az
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Skip if the source data field contains a `$z` \(canceled/invalid control number\).

2.  Get value of `$a`.

    1.  Normalize `$a` \(lower case and remove punctuation characters\) to test the value.

    2.  If the normalized value of `$a` starts with "oc", return the original value.

    3.  Else, skip the source data field.


`2395`

```
{
  "identified_by": [
    {
      "type": "Identifier",
      "content": "(OCoLC)ocm00213132",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300404621",
          "type": "Type",
          "_label": "Owner-Assigned Number"
        }
      ],
      "attributed_by": [
        {
          "type": "AttributeAssignment",
          "carried_out_by": [
            {
              "type": "Group",
              "_label": "OCLC"
            }
          ]
        }
      ]
    },
    {
      "type": "Identifier",
      "content": "(OCoLC)ocn687654227",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300404621",
          "type": "Type",
          "_label": "Owner-Assigned Number"
        }
      ],
      "attributed_by": [
        {
          "type": "AttributeAssignment",
          "carried_out_by": [
            {
              "type": "Group",
              "_label": "OCLC"
            }
          ]
        }
      ]
    },
    {
      "type": "Identifier",
      "content": "(OCoLC)213132",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300404621",
          "type": "Type",
          "_label": "Owner-Assigned Number"
        }
      ],
      "attributed_by": [
        {
          "type": "AttributeAssignment",
          "carried_out_by": [
            {
              "type": "Group",
              "_label": "OCLC"
            }
          ]
        }
      ]
    }
  ]
}
```

**Parent topic:**[Identifiers](../../concepts/identifiers.md)

**Related information**  


[035 \(System Control Number\)](../../tables/035_bib_table.md)

[079](../../tables/079_bib_table.md)

