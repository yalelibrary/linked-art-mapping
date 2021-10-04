---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
---

# International Standard Serial Number \(ISSN\)

The International Standard Serial Number is a unique identification number assigned to a continuing resource.

## Source data

```

{
  "name": "Issn",
  "sampleBibs": [4, 3802861, 15589896],
  "fieldSpec": "022ayz",
  "trimPunctuation": false,
  "scriptInclusion": "NONE"
}        		        		
        		
```

## Processing steps and output

1.  Skip `022` if `022y` \(incorrect ISSN\) or `022z` \(cancelled ISSN\).

2.  Get value of `022a`.

3.  Output JSON-LD with the ISSN:


`464630`

```
{
  "identified_by": [
    {
      "type": "Identifier",
      "content": "0161-4223",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300417430",
          "type": "Type",
          "_label": "ISSN Identifier"
        }
      ]
    }
  ]
}
```

**Parent topic:**[Identifiers](../../concepts/identifiers.md)

**Related information**  


[022 \(International Standard Serial Number\)](../../tables/022_bib_table.md)

