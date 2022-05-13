---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, ]
---

# Locations and call numbers

Locations and call numbers are derived from MARC holdings records \(MFHDs\).

|Domains|Usage|
|-------|-----|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `LinguisticObject` or `VisualItem`.|
|`Set → members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: LocationsAndCallNumbers
sampleBibs:
  - 3
  - 9447
  - 12237283
fieldSpec:
  - item
  - mfhd852bhimk
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  For each [carrier-level record](../../glossary/carrier_level_record.md), extract the call number from the corresponding MFHD.

2.  Use the Voyager location code lookup table, which contains mappings between location codes and their corresponding names.

    |Campus division|Location|Location code|
    |---------------|--------|-------------|
    |Yale University Library|Bass Library|bassill|
    |Yale University Library|Bass Library|ccl|
    |Yale University Library|Bass Library|ccl2wkr|
    |Yale University Library|Bass Library|ccl3day|
    |Yale University Library|Bass Library|cclaud|
    |Yale University Library|Bass Library|cclaudio|
    |Yale University Library|Bass Library|cclbind|
    |Yale University Library|Bass Library|cclbmec|
    |Yale University Library|Bass Library|cclborr|
    |Yale University Library|Bass Library|cclcd|
    |Yale University Library|Bass Library|cclclicker|
    |Yale University Library|Bass Library|cclclos|
    |Yale University Library|Bass Library|ccldesk|
    |Yale University Library|Bass Library|ccldvd|
    |Yale University Library|Bass Library|cclec|
    |Yale University Library|Bass Library|ccletextcd|
    |Yale University Library|Bass Library|cclger|
    |Yale University Library|Bass Library|cclgraph|
    |Yale University Library|Bass Library|cclhr2|
    |Yale University Library|Bass Library|cclhr24|
    |Yale University Library|Bass Library|ccllibn|
    |Yale University Library|Bass Library|cclmtn|
    |Yale University Library|Bass Library|cclnew|
    |Yale University Library|Bass Library|cclnogo|
    |Yale University Library|Bass Library|cclop|
    |Yale University Library|Bass Library|cclpoor|
    |Yale University Library|Bass Library|cclpres|
    |Yale University Library|Bass Library|cclra1|
    |Yale University Library|Bass Library|cclref|
    |Yale University Library|Bass Library|cclrefa|
    |Yale University Library|Bass Library|cclsoft|
    |Yale University Library|Bass Library|ccltran|
    |Yale University Library|Bass Library|ccltravel|
    |Yale University Library|Bass Library|cclvd|
    |Yale University Library|Bass Library|cclvid|
    |Yale University Library|Bass Library|cclyccdvd|
    |Yale University Library|Bass Library|cclzzz|
    |Yale University Library|Bass Library|lsfmtn|
    |Yale University Library|Bass Library|smllnbm|
    |Yale University Library|Bass Library|smllnbt|
    |Yale University Library|Beinecke Library|beineliz|
    |Yale University Library|Beinecke Library|beingen|
    |Yale University Library|Beinecke Library|beinosb|
    |Yale University Library|Beinecke Library|beinref|
    |Yale University Library|Beinecke Library|beinsref|
    |Yale University Library|Beinecke Library|beinwa|
    |Yale University Library|Beinecke Library|beinycal|
    |Yale University Library|Beinecke Library|beinycgl|
    |Yale University Library|Beinecke Library|lsfbeiar|
    |Yale University Library|Beinecke Library|lsfbeigr|
    |Yale University Library|Beinecke Library|lsfbeior|
    |Yale University Library|Beinecke Library|lsfbeir|
    |Yale University Library|Beinecke Library|lsfbeiwr|
    |Yale University Library|Classics Library|clanum|
    |Yale University Library|Classics Library|clas|
    |Yale University Library|Classics Library|clasclos|
    |Yale University Library|Classics Library|clasdict|
    |Yale University Library|Classics Library|clasref|
    |Yale University Library|Classics Library|clasres|
    |Yale University Library|Classics Library|lsfcla|
    |Yale University Library|Classics Library|lsfnum|
    |Yale University Library|Classics Library|lsfnumr|
    |Yale University Library|Cushing/Whitney Medical Library|eph|
    |Yale University Library|Cushing/Whitney Medical Library|ephcens|
    |Yale University Library|Cushing/Whitney Medical Library|ephcirc|
    |Yale University Library|Cushing/Whitney Medical Library|ephhist|
    |Yale University Library|Cushing/Whitney Medical Library|ephhr24|
    |Yale University Library|Cushing/Whitney Medical Library|ephnchs|
    |Yale University Library|Cushing/Whitney Medical Library|ephper|
    |Yale University Library|Cushing/Whitney Medical Library|ephref|
    |Yale University Library|Cushing/Whitney Medical Library|ephres|
    |Yale University Library|Cushing/Whitney Medical Library|ephres3|
    |Yale University Library|Cushing/Whitney Medical Library|ephsref|
    |Yale University Library|Cushing/Whitney Medical Library|lsfeph|
    |Yale University Library|Cushing/Whitney Medical Library|lsfephr|
    |Yale University Library|Cushing/Whitney Medical Library|lsfmed|
    |Yale University Library|Cushing/Whitney Medical Library|lsfmedr|
    |Yale University Library|Cushing/Whitney Medical Library|med|
    |Yale University Library|Cushing/Whitney Medical Library|med3day|
    |Yale University Library|Cushing/Whitney Medical Library|medbiog|
    |Yale University Library|Cushing/Whitney Medical Library|medcat|
    |Yale University Library|Cushing/Whitney Medical Library|medcirc|
    |Yale University Library|Cushing/Whitney Medical Library|medcird|
    |Yale University Library|Cushing/Whitney Medical Library|medcres|
    |Yale University Library|Cushing/Whitney Medical Library|medhper|
    |Yale University Library|Cushing/Whitney Medical Library|medhr24|
    |Yale University Library|Cushing/Whitney Medical Library|medhr4|
    |Yale University Library|Cushing/Whitney Medical Library|medhrf|
    |Yale University Library|Cushing/Whitney Medical Library|medhs|
    |Yale University Library|Cushing/Whitney Medical Library|medhsl|
    |Yale University Library|Cushing/Whitney Medical Library|medhslmini|
    |Yale University Library|Cushing/Whitney Medical Library|medill|
    |Yale University Library|Cushing/Whitney Medical Library|medjres|
    |Yale University Library|Cushing/Whitney Medical Library|medmic|
    |Yale University Library|Cushing/Whitney Medical Library|mednref|
    |Yale University Library|Cushing/Whitney Medical Library|mednres|
    |Yale University Library|Cushing/Whitney Medical Library|medper|
    |Yale University Library|Cushing/Whitney Medical Library|medref|
    |Yale University Library|Cushing/Whitney Medical Library|medrefchc|
    |Yale University Library|Cushing/Whitney Medical Library|medrefec|
    |Yale University Library|Cushing/Whitney Medical Library|medrefeol|
    |Yale University Library|Cushing/Whitney Medical Library|medrefrc|
    |Yale University Library|Cushing/Whitney Medical Library|medres|
    |Yale University Library|Cushing/Whitney Medical Library|medsref|
    |Yale University Library|Cushing/Whitney Medical Library|medtcc|
    |Yale University Library|Cushing/Whitney Medical Library|medthes|
    |Yale University Library|Cushing/Whitney Medical Library|medts|
    |Yale University Library|Cushing/Whitney Medical Library|medwk1|
    |Yale University Library|Cushing/Whitney Medical Library|medzzz|
    |Yale University Library|Cushing/Whitney Medical Library|mesjres|
    |Yale University Library|Cushing/Whitney Medical Library|rad|
    |Yale University Library|Divinity Library|div|
    |Yale University Library|Divinity Library|div3day|
    |Yale University Library|Divinity Library|divannx|
    |Yale University Library|Divinity Library|divborr|
    |Yale University Library|Divinity Library|divbss|
    |Yale University Library|Divinity Library|divcd|
    |Yale University Library|Divinity Library|divdmr|
    |Yale University Library|Divinity Library|divdmrref|
    |Yale University Library|Divinity Library|diveast|
    |Yale University Library|Divinity Library|divhr24|
    |Yale University Library|Divinity Library|divlo|
    |Yale University Library|Divinity Library|divmrc|
    |Yale University Library|Divinity Library|divmrclc|
    |Yale University Library|Divinity Library|divmrr|
    |Yale University Library|Divinity Library|divmrv|
    |Yale University Library|Divinity Library|divrc|
    |Yale University Library|Divinity Library|divres|
    |Yale University Library|Divinity Library|divrlo|
    |Yale University Library|Divinity Library|divrr|
    |Yale University Library|Divinity Library|divrrus|
    |Yale University Library|Divinity Library|divrsno|
    |Yale University Library|Divinity Library|divspc|
    |Yale University Library|Divinity Library|divsr|
    |Yale University Library|Divinity Library|divts|
    |Yale University Library|Divinity Library|divwk1r|
    |Yale University Library|Divinity Library|lsfdiv|
    |Yale University Library|Divinity Library|lsfdivr|
    |Yale University Library|Film Archive|filmdvd|
    |Yale University Library|Film Archive|filmfidv|
    |Yale University Library|Film Archive|filmlasr|
    |Yale University Library|Film Archive|filmref|
    |Yale University Library|Film Archive|filmvidb|
    |Yale University Library|Film Archive|fsfilm|
    |Yale University Library|Film Archive|lsffs|
    |Yale University Library|Film Archive|lsffsfilm|
    |Yale University Library|Film Archive|lsffsvideo|
    |Yale University Library|Film Archive|lsffsvidr|
    |Yale University Library|Government Documents|gdcsslr|
    |Yale University Library|Government Documents|lsfgdc|
    |Yale University Library|Haas Arts Library|art|
    |Yale University Library|Haas Arts Library|artbas3|
    |Yale University Library|Haas Arts Library|artbirr|
    |Yale University Library|Haas Arts Library|artcr|
    |Yale University Library|Haas Arts Library|artlck1|
    |Yale University Library|Haas Arts Library|artlck2|
    |Yale University Library|Haas Arts Library|artlo1|
    |Yale University Library|Haas Arts Library|artlo2|
    |Yale University Library|Haas Arts Library|artmicl|
    |Yale University Library|Haas Arts Library|artnogo|
    |Yale University Library|Haas Arts Library|artop|
    |Yale University Library|Haas Arts Library|artor|
    |Yale University Library|Haas Arts Library|artper|
    |Yale University Library|Haas Arts Library|artref|
    |Yale University Library|Haas Arts Library|artrefb|
    |Yale University Library|Haas Arts Library|artrefc|
    |Yale University Library|Haas Arts Library|artrefi|
    |Yale University Library|Haas Arts Library|artspc|
    |Yale University Library|Haas Arts Library|artspr|
    |Yale University Library|Haas Arts Library|artsps|
    |Yale University Library|Haas Arts Library|artsty1|
    |Yale University Library|Haas Arts Library|artsty2|
    |Yale University Library|Haas Arts Library|artts|
    |Yale University Library|Haas Arts Library|artunca|
    |Yale University Library|Haas Arts Library|artuncd|
    |Yale University Library|Haas Arts Library|artunci|
    |Yale University Library|Haas Arts Library|artzzz|
    |Yale University Library|Haas Arts Library|dra|
    |Yale University Library|Haas Arts Library|drabbx|
    |Yale University Library|Haas Arts Library|dracr|
    |Yale University Library|Haas Arts Library|drafoll|
    |Yale University Library|Haas Arts Library|drafolo|
    |Yale University Library|Haas Arts Library|dragpb|
    |Yale University Library|Haas Arts Library|drahclc|
    |Yale University Library|Haas Arts Library|dranbs|
    |Yale University Library|Haas Arts Library|draod|
    |Yale University Library|Haas Arts Library|draor|
    |Yale University Library|Haas Arts Library|draperc|
    |Yale University Library|Haas Arts Library|drar|
    |Yale University Library|Haas Arts Library|drarefl|
    |Yale University Library|Haas Arts Library|drarefo|
    |Yale University Library|Haas Arts Library|drascrc|
    |Yale University Library|Haas Arts Library|draspc|
    |Yale University Library|Haas Arts Library|drathe|
    |Yale University Library|Haas Arts Library|lsfaobr|
    |Yale University Library|Haas Arts Library|lsfart|
    |Yale University Library|Haas Arts Library|lsfartr|
    |Yale University Library|Haas Arts Library|lsfartrr|
    |Yale University Library|Haas Arts Library|lsfclar|
    |Yale University Library|Haas Arts Library|lsfdra|
    |Yale University Library|Haas Arts Library|lsfdrar|
    |Yale University Library|Haas Arts Library|lsfdrarr|
    |Yale University Library|Haas Arts Library|lsfvrcr|
    |Yale University Library|Haas Arts Library|smlaob|
    |Yale University Library|Haas Arts Library|vrcspc|
    |Yale University Library|Law Library|law|
    |Yale University Library|Lewis Walpole Library|lwl|
    |Yale University Library|Lewis Walpole Library|lwlint|
    |Yale University Library|Lewis Walpole Library|lwlprsat|
    |Yale University Library|Lewis Walpole Library|lwlref|
    |Yale University Library| |lsf|
    |Yale University Library|Manuscripts and Archives|lsffesr|
    |Yale University Library|Manuscripts and Archives|lsfhvt|
    |Yale University Library|Manuscripts and Archives|lsfmssr|
    |Yale University Library|Manuscripts and Archives|lsfr|
    |Yale University Library|Manuscripts and Archives|smlmss|
    |Yale University Library|Manuscripts and Archives|smlyal|
    |Yale University Library|Manuscripts and Archives|smlyalc|
    |Yale University Library|Manuscripts and Archives|smlyalt|
    |Yale University Library|Marx Library|ast|
    |Yale University Library|Marx Library|astref|
    |Yale University Library|Marx Library|chem|
    |Yale University Library|Marx Library|chemref|
    |Yale University Library|Marx Library|chemwkst|
    |Yale University Library|Marx Library|csssi|
    |Yale University Library|Marx Library|csssi24hr|
    |Yale University Library|Marx Library|csssi2hr|
    |Yale University Library|Marx Library|csssi3day|
    |Yale University Library|Marx Library|csssiannex|
    |Yale University Library|Marx Library|csssifolio|
    |Yale University Library|Marx Library|csssiper|
    |Yale University Library|Marx Library|csssiperm|
    |Yale University Library|Marx Library|csssiref|
    |Yale University Library|Marx Library|csssirefst|
    |Yale University Library|Marx Library|engn|
    |Yale University Library|Marx Library|engnborr|
    |Yale University Library|Marx Library|engnhr24|
    |Yale University Library|Marx Library|engnlo|
    |Yale University Library|Marx Library|engnnonc|
    |Yale University Library|Marx Library|engnper|
    |Yale University Library|Marx Library|engnperm|
    |Yale University Library|Marx Library|engnref|
    |Yale University Library|Marx Library|engnrep|
    |Yale University Library|Marx Library|engnres|
    |Yale University Library|Marx Library|fes|
    |Yale University Library|Marx Library|fesfol|
    |Yale University Library|Marx Library|fesfsc|
    |Yale University Library|Marx Library|feshr2|
    |Yale University Library|Marx Library|feshr24|
    |Yale University Library|Marx Library|fesover|
    |Yale University Library|Marx Library|fesper|
    |Yale University Library|Marx Library|fesref|
    |Yale University Library|Marx Library|festhe|
    |Yale University Library|Marx Library|geo|
    |Yale University Library|Marx Library|geodsk|
    |Yale University Library|Marx Library|geofol|
    |Yale University Library|Marx Library|geogis|
    |Yale University Library|Marx Library|geohr2|
    |Yale University Library|Marx Library|geomap|
    |Yale University Library|Marx Library|geomic|
    |Yale University Library|Marx Library|geonbs|
    |Yale University Library|Marx Library|geonogo|
    |Yale University Library|Marx Library|geononc|
    |Yale University Library|Marx Library|geoper|
    |Yale University Library|Marx Library|geoperm|
    |Yale University Library|Marx Library|georbc|
    |Yale University Library|Marx Library|georbr|
    |Yale University Library|Marx Library|georef|
    |Yale University Library|Marx Library|geores|
    |Yale University Library|Marx Library|georrr|
    |Yale University Library|Marx Library|geothe|
    |Yale University Library|Marx Library|geots|
    |Yale University Library|Marx Library|geozzz|
    |Yale University Library|Marx Library|ksl|
    |Yale University Library|Marx Library|kslabs|
    |Yale University Library|Marx Library|kslannex|
    |Yale University Library|Marx Library|kslant|
    |Yale University Library|Marx Library|kslantc|
    |Yale University Library|Marx Library|kslanto|
    |Yale University Library|Marx Library|kslantp|
    |Yale University Library|Marx Library|kslantr|
    |Yale University Library|Marx Library|kslcage|
    |Yale University Library|Marx Library|kslclb|
    |Yale University Library|Marx Library|kslclp|
    |Yale University Library|Marx Library|kslfolio|
    |Yale University Library|Marx Library|kslherb|
    |Yale University Library|Marx Library|kslkoff|
    |Yale University Library|Marx Library|kslloff|
    |Yale University Library|Marx Library|kslnew|
    |Yale University Library|Marx Library|kslop|
    |Yale University Library|Marx Library|kslopen|
    |Yale University Library|Marx Library|kslper|
    |Yale University Library|Marx Library|kslperm|
    |Yale University Library|Marx Library|kslpers|
    |Yale University Library|Marx Library|kslrec|
    |Yale University Library|Marx Library|kslref|
    |Yale University Library|Marx Library|kslrefa|
    |Yale University Library|Marx Library|kslrefd|
    |Yale University Library|Marx Library|kslrefj|
    |Yale University Library|Marx Library|kslrefo|
    |Yale University Library|Marx Library|kslroff|
    |Yale University Library|Marx Library|kslsngo|
    |Yale University Library|Marx Library|kslstks|
    |Yale University Library|Marx Library|ksltoff|
    |Yale University Library|Marx Library|kslvid|
    |Yale University Library|Marx Library|kslzzz|
    |Yale University Library|Marx Library|lsfche|
    |Yale University Library|Marx Library|lsfchem|
    |Yale University Library|Marx Library|lsfcher|
    |Yale University Library|Marx Library|lsfcsssi|
    |Yale University Library|Marx Library|lsfeng|
    |Yale University Library|Marx Library|lsfengr|
    |Yale University Library|Marx Library|lsffes|
    |Yale University Library|Marx Library|lsffor|
    |Yale University Library|Marx Library|lsfforr|
    |Yale University Library|Marx Library|lsfgdcr|
    |Yale University Library|Marx Library|lsfgeo|
    |Yale University Library|Marx Library|lsfgeor|
    |Yale University Library|Marx Library|lsfksl|
    |Yale University Library|Marx Library|lsfkslant|
    |Yale University Library|Marx Library|lsfkslr|
    |Yale University Library|Marx Library|lsflamc|
    |Yale University Library|Marx Library|lsfssl|
    |Yale University Library|Marx Library|lsfsslc|
    |Yale University Library|Marx Library|lsfsslr|
    |Yale University Library|Marx Library|lsfstat|
    |Yale University Library|Marx Library|orn|
    |Yale University Library|Marx Library|ornref|
    |Yale University Library|Marx Library|ssl|
    |Yale University Library|Marx Library|ssl3day|
    |Yale University Library|Marx Library|sslP2|
    |Yale University Library|Marx Library|sslcd|
    |Yale University Library|Marx Library|sslclr|
    |Yale University Library|Marx Library|ssldar|
    |Yale University Library|Marx Library|sslegc|
    |Yale University Library|Marx Library|sslgdcr|
    |Yale University Library|Marx Library|sslhr24|
    |Yale University Library|Marx Library|sslmic1|
    |Yale University Library|Marx Library|sslp24|
    |Yale University Library|Marx Library|sslpam1|
    |Yale University Library|Marx Library|sslpam2|
    |Yale University Library|Marx Library|sslper|
    |Yale University Library|Marx Library|sslref|
    |Yale University Library|Marx Library|sslref5|
    |Yale University Library|Marx Library|sslref6|
    |Yale University Library|Marx Library|ssltec|
    |Yale University Library|Marx Library|sslvid|
    |Yale University Library|Marx Library|sslzzz|
    |Yale University Library|Math Library|lsfmath|
    |Yale University Library|Math Library|math|
    |Yale University Library|Math Library|mathannex|
    |Yale University Library|Math Library|mathper|
    |Yale University Library|Math Library|mathref|
    |Yale University Library|Music Library|lsfhsrr|
    |Yale University Library|Music Library|lsfmus|
    |Yale University Library|Music Library|lsfmusr|
    |Yale University Library|Music Library|mus|
    |Yale University Library|Music Library|muscar|
    |Yale University Library|Music Library|muscirc|
    |Yale University Library|Music Library|mushsr|
    |Yale University Library|Music Library|musmic|
    |Yale University Library|Music Library|musoff1|
    |Yale University Library|Music Library|musoff2|
    |Yale University Library|Music Library|musoff3|
    |Yale University Library|Music Library|musohm|
    |Yale University Library|Music Library|musper|
    |Yale University Library|Music Library|musrar1|
    |Yale University Library|Music Library|musrar2|
    |Yale University Library|Music Library|musrec|
    |Yale University Library|Music Library|musref|
    |Yale University Library|Music Library|musres|
    |Yale University Library|Music Library|muszzz|
    |Yale University Library|Oral History of American Music|musohm|
    |Yale University Library|Sterling Memorial Library|kslantm|
    |Yale University Library|Sterling Memorial Library|kslmic|
    |Yale University Library|Sterling Memorial Library|lsfbaby|
    |Yale University Library|Sterling Memorial Library|lsfjud|
    |Yale University Library|Sterling Memorial Library|lsfmap|
    |Yale University Library|Sterling Memorial Library|lsfmapr|
    |Yale University Library|Sterling Memorial Library|lsfnea|
    |Yale University Library|Sterling Memorial Library|lsfpresr|
    |Yale University Library|Sterling Memorial Library|lsfsla|
    |Yale University Library|Sterling Memorial Library|lsfslar|
    |Yale University Library|Sterling Memorial Library|lsfsmlaris|
    |Yale University Library|Sterling Memorial Library|lsfsmlasi|
    |Yale University Library|Sterling Memorial Library|lsfsmlasir|
    |Yale University Library|Sterling Memorial Library|lsfsmlear|
    |Yale University Library|Sterling Memorial Library|lsfsmlmicr|
    |Yale University Library|Sterling Memorial Library|lsfsmlphi|
    |Yale University Library|Sterling Memorial Library|sml|
    |Yale University Library|Sterling Memorial Library|smlafr|
    |Yale University Library|Sterling Memorial Library|smlamst|
    |Yale University Library|Sterling Memorial Library|smland|
    |Yale University Library|Sterling Memorial Library|smlaos|
    |Yale University Library|Sterling Memorial Library|smlaris|
    |Yale University Library|Sterling Memorial Library|smlasi|
    |Yale University Library|Sterling Memorial Library|smlasi2|
    |Yale University Library|Sterling Memorial Library|smlasi3|
    |Yale University Library|Sterling Memorial Library|smlbab|
    |Yale University Library|Sterling Memorial Library|smlbib|
    |Yale University Library|Sterling Memorial Library|smlbind|
    |Yale University Library|Sterling Memorial Library|smlbldg|
    |Yale University Library|Sterling Memorial Library|smlcat|
    |Yale University Library|Sterling Memorial Library|smlcatr|
    |Yale University Library|Sterling Memorial Library|smlcd|
    |Yale University Library|Sterling Memorial Library|smlchir|
    |Yale University Library|Sterling Memorial Library|smlcoff|
    |Yale University Library|Sterling Memorial Library|smlcon|
    |Yale University Library|Sterling Memorial Library|smldesk|
    |Yale University Library|Sterling Memorial Library|smldskn|
    |Yale University Library|Sterling Memorial Library|smlear|
    |Yale University Library|Sterling Memorial Library|smleasc|
    |Yale University Library|Sterling Memorial Library|smleaso|
    |Yale University Library|Sterling Memorial Library|smlegypt|
    |Yale University Library|Sterling Memorial Library|smleng|
    |Yale University Library|Sterling Memorial Library|smlfolio|
    |Yale University Library|Sterling Memorial Library|smlfolior|
    |Yale University Library|Sterling Memorial Library|smlfra|
    |Yale University Library|Sterling Memorial Library|smlgen|
    |Yale University Library|Sterling Memorial Library|smlhtxt|
    |Yale University Library|Sterling Memorial Library|smlill|
    |Yale University Library|Sterling Memorial Library|smljpnr|
    |Yale University Library|Sterling Memorial Library|smljud|
    |Yale University Library|Sterling Memorial Library|smljudr|
    |Yale University Library|Sterling Memorial Library|smlkorr|
    |Yale University Library|Sterling Memorial Library|smllamc|
    |Yale University Library|Sterling Memorial Library|smllnb|
    |Yale University Library|Sterling Memorial Library|smlmap|
    |Yale University Library|Sterling Memorial Library|smlmapa|
    |Yale University Library|Sterling Memorial Library|smlmapb|
    |Yale University Library|Sterling Memorial Library|smlmapg|
    |Yale University Library|Sterling Memorial Library|smlmapl|
    |Yale University Library|Sterling Memorial Library|smlmapr|
    |Yale University Library|Sterling Memorial Library|smlmapu|
    |Yale University Library|Sterling Memorial Library|smlmic|
    |Yale University Library|Sterling Memorial Library|smlmicr|
    |Yale University Library|Sterling Memorial Library|smlmlc|
    |Yale University Library|Sterling Memorial Library|smlnea|
    |Yale University Library|Sterling Memorial Library|smlneg|
    |Yale University Library|Sterling Memorial Library|smlnegd|
    |Yale University Library|Sterling Memorial Library|smlnews|
    |Yale University Library|Sterling Memorial Library|smlnogo|
    |Yale University Library|Sterling Memorial Library|smlnonc|
    |Yale University Library|Sterling Memorial Library|smlnrc|
    |Yale University Library|Sterling Memorial Library|smlnum|
    |Yale University Library|Sterling Memorial Library|smlop|
    |Yale University Library|Sterling Memorial Library|smlparl|
    |Yale University Library|Sterling Memorial Library|smlper|
    |Yale University Library|Sterling Memorial Library|smlphi|
    |Yale University Library|Sterling Memorial Library|smlpres|
    |Yale University Library|Sterling Memorial Library|smlref|
    |Yale University Library|Sterling Memorial Library|smlrefa|
    |Yale University Library|Sterling Memorial Library|smlrefd|
    |Yale University Library|Sterling Memorial Library|smlrefh|
    |Yale University Library|Sterling Memorial Library|smlrefi|
    |Yale University Library|Sterling Memorial Library|smlrefl|
    |Yale University Library|Sterling Memorial Library|smlres|
    |Yale University Library|Sterling Memorial Library|smlrfof|
    |Yale University Library|Sterling Memorial Library|smlrstr|
    |Yale University Library|Sterling Memorial Library|smlsea|
    |Yale University Library|Sterling Memorial Library|smlsem|
    |Yale University Library|Sterling Memorial Library|smlser|
    |Yale University Library|Sterling Memorial Library|smlsin|
    |Yale University Library|Sterling Memorial Library|smlsla|
    |Yale University Library|Sterling Memorial Library|smlslam|
    |Yale University Library|Sterling Memorial Library|smlslanews|
    |Yale University Library|Sterling Memorial Library|smlslar|
    |Yale University Library|Sterling Memorial Library|smlsub|
    |Yale University Library|Sterling Memorial Library|smlsyst|
    |Yale University Library|Sterling Memorial Library|smly|
    |Yale University Library|Sterling Memorial Library|smlzeta|
    |Yale University Library|Sterling Memorial Library|smlzzz|
    |Yale University Library|Sterling Memorial Library|stat|
    |Yale University Library|Sterling Memorial Library|statper|
    |Yale University Library|Sterling Memorial Library|statref|
    |Yale Center for British Art|Yale Center for British Art Institutional Archives|bacia|
    |Yale Center for British Art|Yale Center for British Art Prints and Drawings|bacpd|
    |Yale Center for British Art|Yale Center for British Art Prints and Drawings|bacpdref|
    |Yale Center for British Art|Yale Center for British Art Rare Rare Books and Manuscripts|bacrb|
    |Yale Center for British Art|Yale Center for British Art Rare Books and Manuscripts|bacrb1|
    |Yale Center for British Art|Yale Center for British Art Rare Books and Manuscripts|bacrb2|
    |Yale Center for British Art|Yale Center for British Art Rare Books and Manuscripts|bacrb3|
    |Yale Center for British Art|Yale Center for British Art Rare Books and Manuscripts|bacrbb|
    |Yale Center for British Art|Yale Center for British Art Rare Books and Manuscripts|bacrbca|
    |Yale Center for British Art|Yale Center for British Art Rare Books and Manuscripts|bacrbcu|
    |Yale Center for British Art|Yale Center for British Art Rare Books and Manuscripts|bacrbf|
    |Yale Center for British Art|Yale Center for British Art Rare Books and Manuscripts|bacrbs|
    |Yale Center for British Art|Yale Center for British Art Reference Library|bacref|
    |Yale Center for British Art|Yale Center for British Art Reference Library|bacrefc|
    |Yale Center for British Art|Yale Center for British Art Reference Library|bacrefd|
    |Yale Center for British Art|Yale Center for British Art Reference Library|bacrefl|
    |Yale Center for British Art|Yale Center for British Art Reference Library|bacrefp|
    |Yale Center for British Art|Yale Center for British Art Reference Library|bacrefr|
    |Yale Center for British Art|Yale Center for British Art Reference Library|bacrefv|
    |Yale Center for British Art|Yale Center for British Art Rare Books and Manuscripts|lsfbacr|
    |Yale Center for British Art|Yale Center for British Art Reference Library|lsfbarr|
    |Yale University Art Gallery| |artgal|
    |Yale University Art Gallery|Yale University Art Gallery Numismatics|yuagcm|
    |Yale University Art Gallery|Yale University Art Gallery Prints and Drawings|yuagpr|

3.  For each `852` field that contains a subfield `b`, select and save the value of subfield `b`.

4.  If field `852` does not contain a subfield `b`, skip the `852` field.

5.  [Normalize](../../glossary/normalization.md) the value of subfield `b` and test whether it is equal to `withdrawn` or `suppressed`.

6.  If the value of subfield `b` is equal to either `withdrawn` or `suppressed`, skip the `852` field.

7.  If the value of subfield `b` is equal to `yulint` or `yulintx`, generate a `DigitalObject` carrier resource.

    See [Content and carriers](../content_and_carriers.md) for more information.

    MFHDs with a subfield `b` value of `yulint` or `yulintx` will not have an associated item record.

    Subfield `b` with a value of `yulint` should not have a call number \(i.e., a value of `None` in subfield `h`\).

    However, subfield `b` with a value of `yulintx` may include call number information \(e.g., when the MFHD represents a digital copy of a digitized resource\).

    **Note:** MFHDs for digitized copies may be suppressed.

    1.  Extract the call number for \(suppressed\) MFHDs with a subfield `b` value of `yulintx`.

        `852 80 $b yulintx $k SUPPRESSED $k Folio $h 49 $i 3582 $m (Oversize)`

8.  Process all other location values.

    1.  Match the value of subfield `b` against the location code lookup table and save the value of the `location_name`.

    2.  Surround the value of the `location_name` with square brackets.

        `[Library Shelving Facility (LSF)]`

9.  Select and save the value of subfield `h`.

    1.  [Normalize](../../glossary/normalization.md) the value.

    2.  If the value contains “\(lc\)”, select the original substring before “\(lc\)” and trim whitespace.

10. Select and save the value of subfield `i`.

    1.  [Normalize](../../glossary/normalization.md) the value.

    2.  If the value contains “\(lc\)”, select the original substring before “\(lc\)” and trim whitespace.

11. Select and save the value of subfield `k`.

    Ignore any subfield `k` with a value of `SUPPRESSED`.

12. Select and save the value of subfield `m`.

13. Join the values of subfields `852hikm` with a whitespace character. This is the `call_number`.

14. Concatenate the `call_number` with item-specific information.

15. If the carrier-level record is an item record, inspect the `Enum` and `Chron` fields.

16. If there is textual content in both the `Enum` and `Chron` fields, extract the values as `enum_val` and `chron_val`.

    1.  Concatenate `enum_val` and `chron_val` with a comma and whitespace character.

    2.  Surround the concatenated value with square brackets.

    3.  Save the value as `enum_chron_val`.

    4.  Concatenate `call_number` and `enum_chron_val` with a whitespace character and save the value as `call_number_2`.

    5.  Concatenate `call_number_2` with the `location_name` with a whitespace character.

    `12104059 [item]`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/object/c0fd4d84-4b50-496d-a56e-ebf952f8dcf2",
      "type": "HumanMadeObject",
      "_label": "Transactions [v.6, 1812]",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300028051",
          "type": "Type",
          "_label": "Journals and Periodicals",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300215390",
              "type": "Type",
              "_label": "Type of Object"
            }
          ]
        }
      ],  
      "identified_by": [
        {
          "type": "Name",
          "content": "Transactions [v.6, 1812]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "ils:yul:mfhd:13867637",
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "carried_out_by": [
                {
                  "id": "https://lux.collections.yale.edu/data/group/yale-university-library",
                  "type": "Group",
                  "_label": "Yale University Library"
                }
              ]
            }
          ],
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435704",
              "type": "Type",
              "_label": "System-Assigned Number"
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "ils:yul:item:12104059",
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "carried_out_by": [
                {
                  "id": "https://lux.collections.yale.edu/data/group/yale-university-library",
                  "type": "Group",
                  "_label": "Yale University Library"
                }
              ]
            }
          ],
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435704",
              "type": "Type",
              "_label": "System-Assigned Number"
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "A48 020 [v.6, 1812] [Library Shelving Facility (LSF)]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311706",
              "type": "Type",
              "_label": "Call Number"
            }
          ]
        }
      ],
      "carries": [
        {
          "id": "https://lux.collections.yale.edu/data/text/416165c2-1108-4acd-b7ab-008f773a2ba3xyz",
          "type": "LinguisticObject",
          "_label": "Transactions"
        }
      ]
    }
    ```

17. If there is textual content in only one of the `Enum` and `Chron` fields, extract the value.

    1.  Surround the extracted value with square brackets.

    2.  Save the value as `enum_val` or `chron_val`.

    3.  Concatenate `call_number` and `enum_val` or `chron_val` with a whitespace character and save the value as `call_number_2`.

    `10962371 [item]`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/digital/0283cba8-169b-4950-bb88-5ba3cdd4ca1d",
      "type": "DigitalObject",
      "_label": "弘前藩庁日記ひろひよみ : 気象・災害等の記述を中心に. Vol.2, (1741年-1868年) [CD]",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300028566",
          "type": "Type",
          "_label": "Software Applications",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435443",
              "type": "Type",
              "_label": "Type of Object"
            }
          ]
        }
      ],
      "identified_by": [
        {
          "type": "Identifier",
          "content": "QC990.J32 H576 2014 CD [CD] [Library Shelving Facility (LSF)]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311706",
              "type": "Type",
              "_label": "Call Number"
            }
          ]
        },
        {
          "type": "Name",
          "content": "Hirosaki hanchō nikki hiroiyomi : kishō saigai nado no kijutsu o chūshin ni. Vol.2, (1741-nen-1868-nen) [CD]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        },
        {
          "type": "Name",
          "content": "弘前藩庁日記ひろひよみ : 気象・災害等の記述を中心に. Vol.2, (1741年-1868年) [CD]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ],
          "language": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/70cb6397-2b2f-400c-b887-70fd80969c8b",
              "type": "Language",
              "_label": "und"
            }
          ]
        }
      ],
      "digitally_carries": [
        {
          "id": "https://lux.collections.yale.edu/data/text/example-content1",
          "type": "LinguisticObject",
          "_label": "Hirosaki hanchō nikki hiroiyomi : kishō saigai nado no kijutsu o chūshin ni. Vol.2, (1741-nen-1868-nen)"
        }
      ]
    }
    ```

18. If the carrier-level record is a holdings record \(i.e., there are no attached item records\), look for `866`, `867`, or `868` fields in the holdings record.

19. Process each `866`, `867`, or `868` as a *separate* carrier-level resource.

    1.  For each `866`, `867`, or `868` \(“textual holdings”\) field, extract the value as `holdings_val`.

    2.  If the `holdings_val` each with a comma, trim the comma from the end of `holdings_val`.

    3.  Surround `holdings_val` with square brackets.

    4.  Concatenate `call_number` and `holdings_val` with a whitespace character and save the value as `call_number_2`.

    `4082244 [MFHD]`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://linked-art.library.yale.edu/node/a436dbcb-fbd0-4364-a27f-1f9a6e79f475",
      "type": "HumanMadeObject",
      "_label": "The Massachusetts gazette, and the Boston post-boy and advertiser [no.229(1762:Jan.4)]",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300026656",
          "type": "Type",
          "_label": "Newspapers",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435443",
              "type": "Type",
              "_label": "Type of Object"
            }
          ]
        }
      ],
      "identified_by": [
        {
          "type": "Identifier",
          "content": "ils:yul:mfhd:4082244",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435704",
              "type": "Type",
              "_label": "System-Assigned Number"
            }
          ],
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "carried_out_by": [
                {
                  "id": "https://linked-art.library.yale.edu/node/0ed3ecaa-4483-4e4e-a015-a6d5ca448106",
                  "type": "Group",
                  "_label": "Yale University Library"
                }
              ]
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "Folio AN22 B7 M383 [no.229(1762:Jan.4)] [Beinecke Library]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311706",
              "type": "Type",
              "_label": "Call Number"
            }
          ]
        },
        {
          "type": "Name",
          "content": "The Massachusetts gazette, and the Boston post-boy and advertiser [no.229(1762:Jan.4)]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "member_of": [
        {
          "id": "https://linked-art.library.yale.edu/node/9d83b3ef-e184-4a46-a2b3-db895d9948bcxyz",
          "type": "Set",
          "_label": "Beinecke Library"
        }
      ],
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "In the Library",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300133046",
              "type": "Type",
              "_label": "Access Statement",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ]
        }
      ],
      "carries": [
        {
          "id": "https://linked-art.library.yale.edu/node/f74f5b5c-a8fd-4c24-85bf-8f09f7ee37eb",
          "type": "LinguisticObject",
          "_label": "The Massachusetts gazette, and the Boston post-boy and advertiser"
        }
      ]
    }
    ```


**Parent topic:**[Identifiers](../../concepts/identifiers.md)

