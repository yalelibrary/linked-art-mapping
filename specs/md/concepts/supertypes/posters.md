---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Posters

## Source data

```
{
  "name": "Posters",
  "sampleBibs": [11221175],
  "fieldSpec": "007[0]:007[1]:300a:650v:655a"
}
```

## Processing steps and output

```
---
# Posters mapping
conditions:
  OR:
    - AND:    
      # Nonprojected graphic
      - - 007[0]
        - k
      # Poster
      - - 007[1]
        - k
    - lower-case(300a) contains 'poster'
    - lower-case(650v) contains 'posters'
    - lower-case(655a) contains 'posters'
```

1.  
```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300033973",
      "type": "Type",
      "_label": "Posters",
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

**Parent topic:**[ImageFormats](../../concepts/supertypes/imageformats.md)

