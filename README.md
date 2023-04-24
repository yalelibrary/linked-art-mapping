# MARC 21 to Linked Art Crosswalk Specifications

Browse the specifications from the [table of contents](https://github.com/yalelibrary/linked-art-mapping/blob/main/specs/md/index.md). 

## Overview
The MARC-to-Linked Art crosswalk specifications have been written using the [Darwin Information Typing Architecture (DITA) standard](http://docs.oasis-open.org/dita/dita/v1.3/dita-v1.3-part0-overview.html). The specification documents are edited and maintained using the oXygen XML Editor.

## Transformation
DITA XML can be transformed into a variety of output formats, including GitHub-flavored Markdown.

The DITA user community maintains [DITA-OT](https://www.dita-ot.org/), an open-source publishing engine for DITA documentation. **Note**: The current version of the specifications is incompatible with DITA-OT versions later than 3.7.4.

1. Download [DITA-OT 3.7.4](https://github.com/dita-ot/dita-ot/releases/tag/3.7.4).
1. Extract the contents of the package to the directory where you want to install DITA-OT.
1. Add the absolute path for the `bin` folder of the DITA-OT installation directory to the [PATH environment variable](https://en.wikipedia.org/wiki/PATH_(variable)).
1. The specifications include three custom element definitions (`yulbibid`, `yulmfhdid`, and `yulitemid`), which have been packaged as a [plugin](https://github.com/yalelibrary/linked-art-mapping/blob/documentation/plugins/edu.yale.library.doctypes.zip) in the `plugins` folder. This plugin **must** be installed in the DITA-OT environment before running the transformation.
1. From the root folder, run `dita install ./plugins/edu.yale.library.doctypes.zip` to install the plugin.
1. Run `dita -i ./specs/dita/lux-v2.ditamap -f markdown_github -o ./specs/md -v` to run the transformation (with verbose output).

The specifications can also be transformed by configuring a scenario within the oXygen XML Editor. oXygen includes robust [support for DITA editing](https://www.oxygenxml.com/doc/versions/25.1/ug-editor/topics/eppo-first-dita-topic.html) and currently comes packaged with version 3 of DITA-OT for DITA transformations. 