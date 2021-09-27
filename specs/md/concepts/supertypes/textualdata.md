---
author: [tt434, tt434, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Textual Data

## Source data

```
{
  "name": "TextualData",
  "sampleBibs": [],
  "fieldSpec": "090a"
}
```

## Processing steps and output

```
---
# Image Data mapping
conditions:
    - 090a
    - yuldsettxt
```

1.  
```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300418050",
      "type": "Type",
      "_label": "Textual Data",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300226816",
          "type": "Type",
          "_label": "Format"
        }
      ]
    }
  ]    		
}
```

**Parent topic:**[DataAndFiles](../../concepts/supertypes/dataandfiles.md)

**Parent topic:**[TextualFormats](../../concepts/supertypes/textualformats.md)

