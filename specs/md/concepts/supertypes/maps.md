---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Maps

## Source data

```
{
  "name": "Maps",
  "sampleBibs": [10547059],
  "fieldSpec": "ldr[6]:008[25]:006[0]:006[8]:007[0]:007[1]:650av:655a"
}
```

## Processing steps and output

```
---
# Maps mapping
conditions:
  AND:
    - OR:
      # Cartographic material
      - - ldr[6]
        - e
      # Manuscript cartographic material
      - - ldr[6]
        - f           
    - OR:
      # Printed map
      - - - 006[0]
          - e	      
        - NOT:
          # Globe
          - - 006[8]
            - d
          # Atlas
          - - 006[8]
            - e            
      # Manuscript map
      - - - 006[0]
          - f
        - NOT:          
          # Globe
            - - 006[8]
              - d
          # Atlas
            - - 006[8]
              - e
      # Map              
      - - - 007[0]
          - a
        - NOT:
          # Atlas
          - - 007[1]
            - d
    - NOT:
      # Globe
      - - 008[25]
        - d
      # Atlas
      - - 008[25]
        - e
      # Topical subject heading
      - lower-case(650a) contains 'atlas'
      # Topical subject heading
      - lower-case(650a) contains 'globe'
      # Form subdivision
      - lower-case(650v) contains 'atlas'
      # Form subdivision
      - lower-case(650v) contains 'globe'
      # Genre heading
      - lower-case(655a) contains 'atlas'
      # Genre heading
      - lower-case(655a) contains 'globe'
```

1.  
```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300028094",
      "type": "Type",
      "_label": "Maps",
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

**Parent topic:**[CartographicFormats](../../concepts/supertypes/cartographicformats.md)

**Parent topic:**[ImageFormats](../../concepts/supertypes/imageformats.md)

