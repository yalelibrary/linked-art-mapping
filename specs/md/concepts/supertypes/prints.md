---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Prints

## Source data

```
{
  "name": "Prints",
  "sampleBibs": [8902194],
  "fieldSpec": "007[0]:007[1]:300a:655a"
}
```

## Processing steps and output

```
---
# Prints mapping
conditions:
  OR:
    - AND:    
      # Nonprojected graphic
      - - 007[0]
        - k
      - OR:
        # Print
        - - 007[1]
          - j
        # Study print
        - - 007[1]
          - s
    - lower-case(300a) contains 'print'
    - lower-case(655a) contains 'lithograph'
    - - lower-case(655a) contains 'posters'
      - NOT:
        - lower-case(655a) contains 'photo'
```

1.  
```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300041273",
      "type": "Type",
      "_label": "Prints",
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

