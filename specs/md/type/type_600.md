# 600 \(Personal Name Subject\)

Subject added entry in which the entry element is a personal name.



|Tag|Tag Label|First Indicator|Second Indicator|Subfield|Subfield Label|Repeatable|
|---|---------|---------------|----------------|--------|--------------|----------|
|600|Personal Name Subject|0-3|0-7|a|Personal name|F|
|600|Personal Name Subject|0-3|0-7|b|Numeration|F|
|600|Personal Name Subject|0-3|0-7|c|Titles and other words associated with a name|T|
|600|Personal Name Subject|0-3|0-7|d|Dates associated with a name|F|
|600|Personal Name Subject|0-3|0-7|e|Relator term|T|
|600|Personal Name Subject|0-3|0-7|g|Miscellaneous information|T|
|600|Personal Name Subject|0-3|0-7|j|Attribution qualifier|T|
|600|Personal Name Subject|0-3|0-7|k|Form subheading|T|
|600|Personal Name Subject|0-3|0-7|l|Language of a work|F|
|600|Personal Name Subject|0-3|0-7|m|Medium of performance for music|T|
|600|Personal Name Subject|0-3|0-7|n|Number of part/section of a work|T|
|600|Personal Name Subject|0-3|0-7|o|Arranged statement for music|F|
|600|Personal Name Subject|0-3|0-7|p|Name of part/section of a work|T|
|600|Personal Name Subject|0-3|0-7|q|Fuller form of name|F|
|600|Personal Name Subject|0-3|0-7|r|Key for music|F|
|600|Personal Name Subject|0-3|0-7|s|Version|T|
|600|Personal Name Subject|0-3|0-7|t|Title of a work|F|
|600|Personal Name Subject|0-3|0-7|u|Affiliation|F|
|600|Personal Name Subject|0-3|0-7|v|Form subdivision|T|
|600|Personal Name Subject|0-3|0-7|x|General subdivision|T|
|600|Personal Name Subject|0-3|0-7|y|Chronological subdivision|T|
|600|Personal Name Subject|0-3|0-7|z|Geographic subdivision|T|
|600|Personal Name Subject|0-3|0-7|0|Authority record control number or standard number|T|
|600|Personal Name Subject|0-3|0-7|1|Real World Object URI|T|
|600|Personal Name Subject|0-3|0-7|2|Source of heading or term|F|
|600|Personal Name Subject|0-3|0-7|3|Materials specified|F|
|600|Personal Name Subject|0-3|0-7|4|Relationship|T|

```

---
examples:
  # Voyager BIB IDs for testing
  - [14, 1200196, 1221849]
input:
  - 600$0
  - 600$a
  - 600$b
  - 600$c
  - 600$d
  - 600$f
  - 600$g
  - 600$h
  - 600$j
  - 600$k
  - 600$l
  - 600$m
  - 600$n
  - 600$o
  - 600$p
  - 600$q
  - 600$r
  - 600$s
  - 600$t
  - 600$v
  - 600$x
  - 600$y
  - 600$z
skip:
  - 2nd indicator 6
  - 2nd indicator 7
trim:
  - punctuation
  - whitespace                
        
```

1.  Test YAML:

2.  Skip `600` fields with 2nd indicator `6` or `7`.

3.  Process any `$0` values.

4.  If the `$0` contains an HTTP URI, capture the value of the URI.

5.  Capture the entity type \(Person, Place, Type, etc.\).

6.  In the top-level entity, add an array with the key `equivalent` to capture identifiers for equivalent entities in external data sources.

7.  For each `$0` that contains a HTTP URI:

    1.  **If the URI is not already present**:

    2.  Add an object to the `equivalent` array.

    3.  Indicate the entity type.

    Example \(derived from BIB ID 1200196\):

    ```
    
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/person/4660f0b7-984e-46a1-8f2b-ba0f0781c8e2",
      "type": "Person",
      "_label": "Thurber, James, 1894-1961",
      "identified_by": [
        {
          "type": "Name",
          "content": "Thurber, James, 1894-1961"
        }
      ],
      "equivalent": [
        {
          "id": "http://id.loc.gov/authorities/names/n80036584",
          "type": "Person"
        }
      ]
    }                        
                
    ```

8.  Capture the `600` personal name subfields: `a, b, c, d, g, j, q`.

9.  Join the personal name subfields with a whitespace character.

10. Check for additional subfields.

    1.  **Title** subfields follow `$t` and should be concatenated.

    2.  **Subdivision** subfields qualify a subject by form, topic, period, or place and should be concatenated.

    |Subfields|Actions|
    |---------|-------|
    |**Title subfields: f, h, k, l, m, n, o, p, r, s, t**|Join the title subfields with a whitespace character. Join the person name string and the title string with a whitespace character.|
    |**Subdivision subfields: v, x, y, z**|Join the personal name string \(and any title string\) and subdivision subfields with double hyphens \(`--`\).|

11. If subdivisions are present, a faceted structure is output in the top-level concept entity.

12. If no subdivisions are present, the referring resource should link directly to the referenced entity \(see second example below\).


Top-level Type \(Concept\) entity with facets \[e.g., BIB ID 14\]:

```

{
  "@context": "https://linked.art/ns/v1/linked-art.json",
  "id": "https://lux.collections.yale.edu/data/concept/71e5999a-5ae3-400a-85ed-74b8bbb2e3a0",
  "type": "Type",
  "_label": "Thurber, James, 1894-1961--Bibliography",
  "identified_by": [
    {
      "type": "Name",
      "content": "Thurber, James, 1894-1961--Bibliography"
    }
  ],
  "created_by": {
    "type": "Creation",
    "influenced_by": [
      {
        "id": "https://lux.collections.yale.edu/data/person/4660f0b7-984e-46a1-8f2b-ba0f0781c8e2",
        "type": "Person",
        "_label": "Thurber, James, 1894-1961"
      },
      {
        "id": "https://lux.collections.yale.edu/data/concept/8a1ac57a-cba5-469a-bebd-36ce159abf04",
        "type": "Type",
        "_label": "Bibliography"
      }
    ]
  }
}                
        
```

1.  Embedded Type \(Concept\) entity \[BIB ID 14\]:

    ```
    
    "about": [
      {
        "id": "https://lux.collections.yale.edu/data/concept/71e5999a-5ae3-400a-85ed-74b8bbb2e3a0",
        "type": "Type",
        "_label": "Thurber, James, 1894-1961--Bibliography"
      }
    ]       
            
    ```

2.  Embedded Person entity as subject \[BIB ID 1221849\]:

    ```
    
    "about": [
      {
        "id": "https://lux.collections.yale.edu/data/person/20fd7e07-e33a-48b3-ab6b-f896ff4f3f9b",
        "type": "Person",
        "_label": "Bembo, Pietro, 1470-1547"
      }
    ]       
            
    ```


**Parent topic:**[Subject Headings](../type/type_subject.md)

