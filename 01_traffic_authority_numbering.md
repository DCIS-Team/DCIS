# UK National Numbering System for Road Authorities (RoadRegulatorID)

C-ITS messaging standards (CEN/ISO TS19091 and C-Roads MAPEM/SPATEM) require a nationally unique `RoadRegulatorID` to be assigned to traffic authorities.

## Considerations

* The `RoadRegulatorID` is specified as a 16-bit integer in the range 1 to 65535 which means that existing alphanumeric identifiers for road authorities (e.g. [Street Works Act Codes](https://www.gov.uk/government/publications/street-works-register/street-works-act-codes)) are not suitable.

* European signal companies have already adopted a convention of prefixing the `RoadRegulatorID` with the international dialling code for that country i.e. '44' for UK.  This convention restricts the number of unique `RoadRegulatorIDs` available in the UK to 1000 (i.e. 44000 to 44999 inclusive).

* For some early UK C-ITS implementations an additional convention was been to use the last digits from local authority's Gegraphic Code as maintained by the Office for National Statistics' in their Register of Geographic Codes (RGC) e.g. as  Unitary Authority, York has a geographic code of E060000**14** so the chosen RoadRegulatorID was **44014** but this doesn't work UK wide because local authorities have different administrative entity codes (e.g. in England: E06, E07, E08, E09, E10, E11, E12 etc.) hence duplicate will occur e.g. York is E06000014 and Congleton is E07000014 so both would result in 44014 as the RoadRegulatorID.

## Current proposal

```
ONS     Country              Description                             Current       RoadRegulatorID    Weighting
Entity                                                               ONS           Range              (added to last
Code                                                                 Count                            3 digits of RGC code)
---------------------------------------------------------------------------------------------------------------------------                 
E06     England              Unitary Authorities                          57       44001 - 44099        +0 
E07     England              Non-metropolitan Districts                  188       44101 - 44349      +100
E08     England              Metropolitan Districts                       36       44351 - 44399      +350
E09     England              London Boroughs                              33       44401 - 44449      +400
E10     England              Counties                                     25       44451 - 44469      +450
E11     England              Metropolitan Counties                         6       44501 - 44519      +500
E12     England              Regions                                       9       44521 - 44539      +520
E47     England              Combined Authorities                         10       44541 - 44559      +540
-       England              RESERVED FOR FUTURE USE                       -       44560 - 44599      N/A      
S12     Scotland             Council Areas                                32       44601 - 44699      +600
W06     Wales                Unitary Authorities                          22       44701 - 44799      +700
N09     Northern Ireland     Districts                                    11       44801 - 44899      +800
-       England              National Highways                                     44901
-       Scotland             Traffic Scotland                                      44902
-       Northern Ireland     DfI Roads                                             44903
-       Wales                North & Mid Wales Trunk Road Agent (NMWTRA)           44904
-       Wales                South Wales Trunk Road Agent (SWTRA)                  44905
-       -                    PRIVATE OPERATORS / FUTURE USE                        44906 - 44999       N/A 
---------------------------------------------------------------------------------------------------------------------------
                                                                  TOTAL  429
```