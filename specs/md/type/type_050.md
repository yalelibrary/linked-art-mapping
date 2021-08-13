# 050 \(Library of Congress Call Number\)

Classification or call number that is taken from Library of Congress Classification or LC Classification Additions and Changes.

Usage: ~11.5 million values

|Tag|Tag Label|First Indicator|Second Indicator|Subfield|Subfield Label|Repeatable|
|---|---------|---------------|----------------|--------|--------------|----------|
|050|Library of Congress Call Number|\#-1|0-4|a|Classification number|T|
|050|Library of Congress Call Number|\#-1|0-4|b|Item number|F|

```

---
examples:
  # Voyager BIB IDs for testing
  - [4, 236, 907498]
input:
  - 050$a
trim:
  - punctuation
  - whitespace
strip:
  - punctuation
  - preserve:
    - period

```

1.  Process any `050$a` values.

2.  For each `050$a`:

    1.  Trim whitespace and punctuation.

    2.  Replace any punctuation characters that are *not* a period \(`.`\) with a whitespace character.

3.  Dedupe processed `050$a` values.


BIB ID: 907498

Top-level Type \(Concept\) entity:

```

{
  "@context": "https://linked.art/ns/v1/linked-art.json",
  "id": "https://lux.collections.yale.edu/data/concept/f0c0c4d0-532d-4438-a26f-15c261fb4f6c",
  "type": "Type",
  "_label": "PT3818",
  "identified_by": [
    {
      "type": "Identifier",
      "content": "PT3818"
    }
  ]
}                
        
```

Embedded Type \(Concept\) entity:

```

"classified_as": [
  {
    "id": "http://vocab.getty.edu/aat/300028051",
    "type": "Type",
    "_label": "Books",
    "classified_as": [
      {
        "id": "http://vocab.getty.edu/aat/300226816",
        "type": "Type",
        "_label": "Form"
      }
    ]
  },
  {
    "id": "https://lux.collections.yale.edu/data/concept/f0c0c4d0-532d-4438-a26f-15c261fb4f6c",
    "type": "Type",
    "_label": "PT3818"
  }
]                
        
```

**Parent topic:**[Call Numbers \(050 and 090\)](../type/type_call_numbers.md)

