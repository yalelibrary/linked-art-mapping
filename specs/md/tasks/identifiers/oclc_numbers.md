---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
---

# System Control Numbers \(OCLC Numbers\)

System number used by OCLC to manage records in the WorldCat system.

## Source data

```

{
  "name": "OclcNumber",
  "sampleBibs": [4, 3802861, 907208, 15589896],
  "fieldSpec": "035az:079az",
  "trimPunctuation": false,
  "scriptInclusion": "NONE"
}        		
        		
```

## Processing steps and output

1.  Apply processing steps for [System Control Number \(OCLC Number\)](oclc_number.md) and [Local System Control Number \(OCLC Number\)](local_oclc_number.md).

2.  Dedupe values.

3.  Output JSON-LD with the OCLC Number:


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

-   **[System Control Number \(OCLC Number\)](../../tasks/identifiers/oclc_number.md)**  
System number used by OCLC to manage records in the WorldCat system.
-   **[Local System Control Number \(OCLC Number\)](../../tasks/identifiers/local_oclc_number.md)**  
System number used by OCLC to manage records in the WorldCat system.

**Parent topic:**[Identifiers](../../concepts/identifiers.md)

