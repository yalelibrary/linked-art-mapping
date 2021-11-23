---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Top-level Place entities

Place entities extracted from 008, 034, 651, 751, 6XXz.

## Source data

```
---
name: PlaceEntities
sampleBibs:
  - 3906934 # 008, 034
  - 2803263 # 651
  - 1066178 # 751
# Source data fields
fieldSpec:
  - 008[15-17]
  - 040e
  - 034defg
  - 651014aegvxyz
  - 691014aegvxyz
  - 751014aeg
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

Processing of place entities depends on the data source in MARC:

1.  `008[15-17]`: three-letter code representing a country- or state-level place entity \(place of publication or production\)
2.  `034`: latitude/longitude coordinates
3.  `651`, `691`, or `751`: geographic subjects and subdivisions or other associated places
4.  `26Xa`: place of publication; this is not currently modeled as a place entity, but as a string value in the [Production Statement](../tasks/notes-and-statements/production_statement.md)

See individual specifications for processing steps corresponding to 1-3.

-   **[Places as agents](../concepts/places_as_agents.md)**  
Places as jurisdictions \(for example, United States as a political entity\).
-   **[Places as subjects \[draft\]](../concepts/places_as_subjects.md)**  

-   **[Places from fixed field 008 \[draft\]](../concepts/places_from_fixed_field_008.md)**  

-   **[Places with geographic coordinates](../concepts/places_with_geographic_coordinates.md)**  
Place entities derived from `MARC 034`.

**Parent topic:**[Places \[draft\]](../concepts/places.md)

