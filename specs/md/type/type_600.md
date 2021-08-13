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
|600|Personal Name Subject|0-3|0-7|q|Fuller form of name|F|
|600|Personal Name Subject|0-3|0-7|t|Title of a work|F|
|600|Personal Name Subject|0-3|0-7|u|Affiliation|F|
|600|Personal Name Subject|0-3|0-7|v|Form subdivision|T|
|600|Personal Name Subject|0-3|0-7|x|General subdivision|T|
|600|Personal Name Subject|0-3|0-7|y|Chronological subdivision|T|
|600|Personal Name Subject|0-3|0-7|z|Geographic subdivision|T|
|600|Personal Name Subject|0-3|0-7|0|Authority record control number or standard number|T|
|600|Personal Name Subject|0-3|0-7|4|Relationship|T|

```

---
examples:
  # Voyager BIB IDs for testing
  - [14, 1221849]
input:
  - 600$a
  - 600$b
  - 600$c
  - 600$d
  - 600$g
  - 600$j
  - 600$q
  - 600$v
  - 600$x
  - 600$y
  - 600$z
trim:
  - punctuation
  - whitespace                
        
```

1.  Process any `$0` values.

2.  If the `$0` contains an HTTP URI, capture the value of the URI.

3.  Capture the entity type \(Person, Place, Type, etc.\).

4.  In the top-level entity, add an array with the key `equivalent` to capture identifiers for equivalent entities in external data sources.

5.  For each `$0` that contains an HTTP URI:

    1.  Add an object to the `equivalent` array.

    2.  Indicate the entity type.

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

6.  Capture the `600` personal name subfields: `a, b, c, d, g, j, q`.

7.  Join the subfields with a whitespace character.

8.  Capture any `600` subdivision subfields: `v, x, y, z`

9.  Join subdivision subfields with double hyphens \(`--`\).

10. Join the personal name string and the subdivision string, if present, with double hyphens \(`--`\).

11. If subdivisions are present, a faceted structure is output in the top-level concept entity.

12. If no subdivisions are present, the referring resource should link directly to the referenced entity \(see second example below\).


Top-level Type \(Concept\) entity with facets \[BIB ID: 14\]:

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

1.  Embedded Type \(Concept\) entity:

    ```
    
    "about": [
      {
        "id": "https://lux.collections.yale.edu/data/concept/71e5999a-5ae3-400a-85ed-74b8bbb2e3a0",
        "type": "Type",
        "_label": "Thurber, James, 1894-1961--Bibliography"
      }
    ]       
            
    ```

2.  Embedded Person entity as subject \[BIB ID: 1221849\]:

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

