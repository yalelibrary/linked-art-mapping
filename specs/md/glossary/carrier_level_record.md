---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
source: 
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: MARC to Linked Art mapping glossary
---

# Carrier-level record

In MARC-based systems, the content/carrier model corresponds roughly to the distinction between bibliographic records and holdings plus item records.

If the resource to be processed includes one or more item records, then process each item plus holdings record as a carrier-level record.

However, not all resources are linked to an item record in Voyager. If there is no item record, then process each holdings record as a carrier-level record. If the holdings record \(e.g., for a journal\) includes one or more `866`, `867`, or `868` \(“textual holdings”\) fields, then each of those fields should be broken out into a *separate* carrier-level resource.

**Note:** See [Content and carriers](../tasks/content_and_carriers.md) for more information.

**Parent topic:**[MARC to Linked Art glossary](../glossary/marc_to_linked_art_glossary.md)

**Previous topic:**[Functional Requirements for Bibliographic Records \(FRBR\)](../glossary/frbr.md)

**Next topic:**[Content-level record](../glossary/content_level_record.md)

