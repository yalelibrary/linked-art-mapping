---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: [Assigned, Completed]
---

# Table of contents

Corresponds to the`505`note field in MARC.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject`.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: TableOfContents
sampleBibs:
  - 18
fieldSpec:
  - 505agrt
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  If `505a` and no other subfields, output the value of `505a`.

2.  Else, join all `505` subfields with a whitespace character.

3.  If there is more than one `505` field, join the string value of all `505` fields with a whitespace character and store the string as a single `content` value.


**Note:** This example is meant to illustrate an table of contents note and does not represent a complete JSON-LD document.

`2733`

```
{
  "referred_to_by": [
    {
      "type": "LinguisticObject",
      "content": "The letter -- Taller to-day -- The journey -- No change of place -- The question -- This lunar beauty -- This one -- Chorus -- The watchers -- Ode -- The decoys -- The three companions -- In legend -- The quarry -- Seascape -- A dream -- Song -- Autumn song -- One evening -- Lullaby -- Underneath the abject willow -- Madrigal -- Able at times to cry -- Two songs for Hedli Anderson -- Miss Gee : a ballad -- Roman wall blues -- Victor : a ballad -- The dead echo -- Ganymede -- A new age -- Surgical ward -- Embassy -- The sphinx -- Macao -- The bard -- Mus©♭e des Beaux Arts -- Gare du Midi -- Rimbaud -- The capital -- Epitaph on a tyrant -- In memory of W.B. Yeats -- In memory of Sigmund Freud -- The quest -- Law like love -- Another time -- Our bias -- Hell -- Song -- Lady, weeping at the crossroads -- If I could tell you -- The model -- Atlantis -- Doomsday song -- Song of the old soldier -- Mundus et infans -- The lesson -- Invocation to Ariel -- Stephano's song
(Cont.) Trinculo's song -- Alonso to Ferdinand -- Song of the master and boatswain -- Miranda's song -- Caliban to the audience -- Three dreams -- In praise of limestone -- One circumlocution -- Their lonely betters -- Song -- Pleasure island -- The fall of Rome -- The managers -- Barbed wire -- Under Sirius -- Numbers and faces -- A household -- Precious five -- The shield of Achilles -- Fleet visit -- The willow-wren and the stare -- The proof -- A permanent way -- Nocturne -- In memoriam L.K.A., 1950-52 -- Bucolics. Winds -- Woods -- Mountains -- Lakes -- Islands -- Plains -- Streams -- Horae canonicae. Prime -- Terce -- Sext -- Nones -- Vespers -- Compline -- Lauds -- Metalogue to The magic flute -- The song -- Good-bye to the mezzogiorno -- Prologue : the birth of architecture -- Thanksgiving for a habitat -- The cave of making -- Down there -- Up there -- The geography of the house -- Encomium Balnei -- Grub first, then ethics -- For friends only
(Cont.) Tonight at seven-thirty -- The cave of nakedness -- The common life -- You -- On the circuit -- After reading a child's guide to modern physics -- Whitsunday in Kirchstetten -- Joseph Weinheber -- The Horatians -- Since -- In due season -- August 1968 -- River profile -- Prologue at sixty.",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300195187",
          "type": "Type",
          "_label": "Table of Contents",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300418049",
              "type": "Type",
              "_label": "Brief Text"
            }
          ]
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "Table of Contents Note",
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

**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

