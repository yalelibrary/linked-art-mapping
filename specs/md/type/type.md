# Type Entity \(Concept\)

## Overview of MARC data sources

|Tag|Label|Repeatable|Mapped|Label|URI|
|---|-----|----------|------|-----|---|
|050|Library of Congress Call Number|T|T|content|system-generated|
|060|National Library of Medicine Call Number|T|F|content|system-generated|
|090|Locally Assigned LC-Type Call Number|T|T|content|system-generated|
|600|Personal Name Subject|T|T|content|system-generated|
|610|Corporate Name Subject|T|T|content|system-generated|
|611|Meeting Name Subject|T|T|content|system-generated|
|630|Title Subject|T|T|content|system-generated|
|650|Topical Subject|T|T|content|system-generated|
|651|Geographic Subject|T|T|content|system-generated|
|653|Uncontrolled Keyword Subject|T|T|content|system-generated|
|656|Associated Occupation|T|T|content|system-generated|
|657|Associated Function|T|T|content|system-generated|
|662|Hierarchical Place Name Subject|T|F|content|system-generated|
|690|Topical Subject \(Locally Assigned\)|T|T|content|system-generated|
|691|Geographic Subject \(Locally Assigned\)s|T|T|content|system-generated|
|692|Personal Name Subject \(Locally Assigned\)|T|T|content|system-generated|
|693|Corporate Name Subject \(Locally Assigned\)|T|T|content|system-generated|
|694|Meeting Name Subject \(Locally Assigned\)|T|T|content|system-generated|
|695|Title Subject \(Locally Assigned\)|T|T|content|system-generated|

## JSON Structure

Type \(Concept\) entities are generated for classification numbers and subject headings.

For each Type entity:

-   A top-level resource is generated.

-   An embedded reference is added to the associated `LinguisticObject`, `VisualItem`, or `DigitalObject` resource.


-   **[Classification Numbers](../type/type_classification.md)**  

-   **[Subject Headings](../type/type_subject.md)**  


