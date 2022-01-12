---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Digital object link to asset

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`Set`|Do not repeat on nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: DigitalObjectAsset
sampleBibs:
  - 358058
fieldSpec:  
  - 856|4*|uy
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Output a `DigitalObject` link to a related digital asset using the URI recorded in `856u`.

2.  If `856y` is present, add it to the embedded reference using `identified_by`.

3.  If `865|40|` or `865|41|` and the record-level resource is a `LinguisticObject`:

    `358058`

    ```
    {
      "digitally_carried_by": [
        {
          "id": "http://hdl.handle.net/example2",
          "type": "DigitalObject",
          "identified_by": [
            {
              "type": "Name",
              "content": "Full text",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404669",
                  "type": "Type",
                  "_label": "Display Title"
                }
              ]
            }
          ]
        }
      ]
    }
    ```

4.  If `865|40|` and the record-level resource is a `DigitalObject`:

    ```
    {
      "access_point": [
        {
          "id": "http://hdl.handle.net/example1",
          "type": "DigitalObject"
        }
      ]
    }
    ```

5.  If `865|40|` or `865|41|` and the record-level resource is a `VisualItem`:

    ```
    {
      "digitally_shown_by": [
        {
          "id": "http://hdl.handle.net/example3",
          "type": "DigitalObject"
        }
      ]
    }
    ```

6.  If `865|40|` or `865|41|` and the record-level resource is a `LinguisticObject`:

    ```
    {
      "digitally_carried_by": [
        {
          "id": "http://hdl.handle.net/example4",
          "type": "DigitalObject"
        }
      ]
    }
    ```

7.  If `865|40|` or `865|41|` and the record-level resource is a `Set`:

    ```
    {
      "representation": [
        {      
          "type": "VisualItem",
          "digitally_shown_by": [
            {
              "id": "http://hdl.handle.net/example5",
              "type": "DigitalObject"
            }
          ]
        }
      ]
    }
    ```

8.  Else, if `865|42|`:

    ```
    {
      "attributed_by": [
        {
          "type": "AttributeAssignment",
          "_label": "associated resource",
          "assigned": {
            "id": "http://hdl.handle.net/example6",
            "type": "DigitalObject"
          }
        }
      ]
    }
    ```


**Parent topic:**[Embedded entities](../concepts/lux_embedded_entities.md)

