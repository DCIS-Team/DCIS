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

## UK RoadRegulatorIDs (proposed)

|ONS code|Country|Authority|RoadRegulatorID|
---
|E06000001|ENGLAND|Hartlepool|44001|
|E06000002|ENGLAND|Middlesbrough|44002|
|E06000003|ENGLAND|Redcar and Cleveland|44003|
|E06000004|ENGLAND|Stockton-on-Tees|44004|
|E06000005|ENGLAND|Darlington|44005|
|E06000006|ENGLAND|Halton|44006|
|E06000007|ENGLAND|Warrington|44007|
|E06000008|ENGLAND|Blackburn with Darwen|44008|
|E06000009|ENGLAND|Blackpool|44009|
|E06000010|ENGLAND|Kingston upon Hull, City of|44010|
|E06000011|ENGLAND|East Riding of Yorkshire|44011|
|E06000012|ENGLAND|North East Lincolnshire|44012|
|E06000013|ENGLAND|North Lincolnshire|44013|
|E06000014|ENGLAND|York|44014|
|E06000015|ENGLAND|Derby|44015|
|E06000016|ENGLAND|Leicester|44016|
|E06000017|ENGLAND|Rutland|44017|
|E06000018|ENGLAND|Nottingham|44018|
|E06000019|ENGLAND|Herefordshire, County of|44019|
|E06000020|ENGLAND|Telford and Wrekin|44020|
|E06000021|ENGLAND|Stoke-on-Trent|44021|
|E06000022|ENGLAND|Bath and North East Somerset|44022|
|E06000023|ENGLAND|Bristol, City of|44023|
|E06000024|ENGLAND|North Somerset|44024|
|E06000025|ENGLAND|South Gloucestershire|44025|
|E06000026|ENGLAND|Plymouth|44026|
|E06000027|ENGLAND|Torbay|44027|
|E06000030|ENGLAND|Swindon|44030|
|E06000031|ENGLAND|Peterborough|44031|
|E06000032|ENGLAND|Luton|44032|
|E06000033|ENGLAND|Southend-on-Sea|44033|
|E06000034|ENGLAND|Thurrock|44034|
|E06000035|ENGLAND|Medway|44035|
|E06000036|ENGLAND|Bracknell Forest|44036|
|E06000037|ENGLAND|West Berkshire|44037|
|E06000038|ENGLAND|Reading|44038|
|E06000039|ENGLAND|Slough|44039|
|E06000040|ENGLAND|Windsor and Maidenhead|44040|
|E06000041|ENGLAND|Wokingham|44041|
|E06000042|ENGLAND|Milton Keynes|44042|
|E06000043|ENGLAND|Brighton and Hove|44043|
|E06000044|ENGLAND|Portsmouth|44044|
|E06000045|ENGLAND|Southampton|44045|
|E06000046|ENGLAND|Isle of Wight|44046|
|E06000047|ENGLAND|County Durham|44047|
|E06000049|ENGLAND|Cheshire East|44049|
|E06000050|ENGLAND|Cheshire West and Chester|44050|
|E06000051|ENGLAND|Shropshire|44051|
|E06000052|ENGLAND|Cornwall|44052|
|E06000053|ENGLAND|Isles of Scilly|44053|
|E06000054|ENGLAND|Wiltshire|44054|
|E06000055|ENGLAND|Bedford|44055|
|E06000056|ENGLAND|Central Bedfordshire|44056|
|E06000057|ENGLAND|Northumberland|44057|
|E06000058|ENGLAND|Bournemouth, Christchurch and Poole|44058|
|E06000059|ENGLAND|Dorset|44059|
|E06000060|ENGLAND|Buckinghamshire|44060|
|E06000061|ENGLAND|North Northamptonshire|44061|
|E06000062|ENGLAND|West Northamptonshire|44062|
|E07000008|ENGLAND|Cambridge|44108|
|E07000009|ENGLAND|East Cambridgeshire|44109|
|E07000010|ENGLAND|Fenland|44110|
|E07000011|ENGLAND|Huntingdonshire|44111|
|E07000012|ENGLAND|South Cambridgeshire|44112|
|E07000026|ENGLAND|Allerdale|44126|
|E07000027|ENGLAND|Barrow-in-Furness|44127|
|E07000028|ENGLAND|Carlisle|44128|
|E07000029|ENGLAND|Copeland|44129|
|E07000030|ENGLAND|Eden|44130|
|E07000031|ENGLAND|South Lakeland|44131|
|E07000032|ENGLAND|Amber Valley|44132|
|E07000033|ENGLAND|Bolsover|44133|
|E07000034|ENGLAND|Chesterfield|44134|
|E07000035|ENGLAND|Derbyshire Dales|44135|
|E07000036|ENGLAND|Erewash|44136|
|E07000037|ENGLAND|High Peak|44137|
|E07000038|ENGLAND|North East Derbyshire|44138|
|E07000039|ENGLAND|South Derbyshire|44139|
|E07000040|ENGLAND|East Devon|44140|
|E07000041|ENGLAND|Exeter|44141|
|E07000042|ENGLAND|Mid Devon|44142|
|E07000043|ENGLAND|North Devon|44143|
|E07000044|ENGLAND|South Hams|44144|
|E07000045|ENGLAND|Teignbridge|44145|
|E07000046|ENGLAND|Torridge|44146|
|E07000047|ENGLAND|West Devon|44147|
|E07000061|ENGLAND|Eastbourne|44161|
|E07000062|ENGLAND|Hastings|44162|
|E07000063|ENGLAND|Lewes|44163|
|E07000064|ENGLAND|Rother|44164|
|E07000065|ENGLAND|Wealden|44165|
|E07000066|ENGLAND|Basildon|44166|
|E07000067|ENGLAND|Braintree|44167|
|E07000068|ENGLAND|Brentwood|44168|
|E07000069|ENGLAND|Castle Point|44169|
|E07000070|ENGLAND|Chelmsford|44170|
|E07000071|ENGLAND|Colchester|44171|
|E07000072|ENGLAND|Epping Forest|44172|
|E07000073|ENGLAND|Harlow|44173|
|E07000074|ENGLAND|Maldon|44174|
|E07000075|ENGLAND|Rochford|44175|
|E07000076|ENGLAND|Tendring|44176|
|E07000077|ENGLAND|Uttlesford|44177|
|E07000078|ENGLAND|Cheltenham|44178|
|E07000079|ENGLAND|Cotswold|44179|
|E07000080|ENGLAND|Forest of Dean|44180|
|E07000081|ENGLAND|Gloucester|44181|
|E07000082|ENGLAND|Stroud|44182|
|E07000083|ENGLAND|Tewkesbury|44183|
|E07000084|ENGLAND|Basingstoke and Deane|44184|
|E07000085|ENGLAND|East Hampshire|44185|
|E07000086|ENGLAND|Eastleigh|44186|
|E07000087|ENGLAND|Fareham|44187|
|E07000088|ENGLAND|Gosport|44188|
|E07000089|ENGLAND|Hart|44189|
|E07000090|ENGLAND|Havant|44190|
|E07000091|ENGLAND|New Forest|44191|
|E07000092|ENGLAND|Rushmoor|44192|
|E07000093|ENGLAND|Test Valley|44193|
|E07000094|ENGLAND|Winchester|44194|
|E07000095|ENGLAND|Broxbourne|44195|
|E07000096|ENGLAND|Dacorum|44196|
|E07000098|ENGLAND|Hertsmere|44198|
|E07000099|ENGLAND|North Hertfordshire|44199|
|E07000102|ENGLAND|Three Rivers|44202|
|E07000103|ENGLAND|Watford|44203|
|E07000105|ENGLAND|Ashford|44205|
|E07000106|ENGLAND|Canterbury|44206|
|E07000107|ENGLAND|Dartford|44207|
|E07000108|ENGLAND|Dover|44208|
|E07000109|ENGLAND|Gravesham|44209|
|E07000110|ENGLAND|Maidstone|44210|
|E07000111|ENGLAND|Sevenoaks|44211|
|E07000112|ENGLAND|Folkestone and Hythe|44212|
|E07000113|ENGLAND|Swale|44213|
|E07000114|ENGLAND|Thanet|44214|
|E07000115|ENGLAND|Tonbridge and Malling|44215|
|E07000116|ENGLAND|Tunbridge Wells|44216|
|E07000117|ENGLAND|Burnley|44217|
|E07000118|ENGLAND|Chorley|44218|
|E07000119|ENGLAND|Fylde|44219|
|E07000120|ENGLAND|Hyndburn|44220|
|E07000121|ENGLAND|Lancaster|44221|
|E07000122|ENGLAND|Pendle|44222|
|E07000123|ENGLAND|Preston|44223|
|E07000124|ENGLAND|Ribble Valley|44224|
|E07000125|ENGLAND|Rossendale|44225|
|E07000126|ENGLAND|South Ribble|44226|
|E07000127|ENGLAND|West Lancashire|44227|
|E07000128|ENGLAND|Wyre|44228|
|E07000129|ENGLAND|Blaby|44229|
|E07000130|ENGLAND|Charnwood|44230|
|E07000131|ENGLAND|Harborough|44231|
|E07000132|ENGLAND|Hinckley and Bosworth|44232|
|E07000133|ENGLAND|Melton|44233|
|E07000134|ENGLAND|North West Leicestershire|44234|
|E07000135|ENGLAND|Oadby and Wigston|44235|
|E07000136|ENGLAND|Boston|44236|
|E07000137|ENGLAND|East Lindsey|44237|
|E07000138|ENGLAND|Lincoln|44238|
|E07000139|ENGLAND|North Kesteven|44239|
|E07000140|ENGLAND|South Holland|44240|
|E07000141|ENGLAND|South Kesteven|44241|
|E07000142|ENGLAND|West Lindsey|44242|
|E07000143|ENGLAND|Breckland|44243|
|E07000144|ENGLAND|Broadland|44244|
|E07000145|ENGLAND|Great Yarmouth|44245|
|E07000146|ENGLAND|King's Lynn and West Norfolk|44246|
|E07000147|ENGLAND|North Norfolk|44247|
|E07000148|ENGLAND|Norwich|44248|
|E07000149|ENGLAND|South Norfolk|44249|
|E07000163|ENGLAND|Craven|44263|
|E07000164|ENGLAND|Hambleton|44264|
|E07000165|ENGLAND|Harrogate|44265|
|E07000166|ENGLAND|Richmondshire|44266|
|E07000167|ENGLAND|Ryedale|44267|
|E07000168|ENGLAND|Scarborough|44268|
|E07000169|ENGLAND|Selby|44269|
|E07000170|ENGLAND|Ashfield|44270|
|E07000171|ENGLAND|Bassetlaw|44271|
|E07000172|ENGLAND|Broxtowe|44272|
|E07000173|ENGLAND|Gedling|44273|
|E07000174|ENGLAND|Mansfield|44274|
|E07000175|ENGLAND|Newark and Sherwood|44275|
|E07000176|ENGLAND|Rushcliffe|44276|
|E07000177|ENGLAND|Cherwell|44277|
|E07000178|ENGLAND|Oxford|44278|
|E07000179|ENGLAND|South Oxfordshire|44279|
|E07000180|ENGLAND|Vale of White Horse|44280|
|E07000181|ENGLAND|West Oxfordshire|44281|
|E07000187|ENGLAND|Mendip|44287|
|E07000188|ENGLAND|Sedgemoor|44288|
|E07000189|ENGLAND|South Somerset|44289|
|E07000192|ENGLAND|Cannock Chase|44292|
|E07000193|ENGLAND|East Staffordshire|44293|
|E07000194|ENGLAND|Lichfield|44294|
|E07000195|ENGLAND|Newcastle-under-Lyme|44295|
|E07000196|ENGLAND|South Staffordshire|44296|
|E07000197|ENGLAND|Stafford|44297|
|E07000198|ENGLAND|Staffordshire Moorlands|44298|
|E07000199|ENGLAND|Tamworth|44299|
|E07000200|ENGLAND|Babergh|44300|
|E07000202|ENGLAND|Ipswich|44302|
|E07000203|ENGLAND|Mid Suffolk|44303|
|E07000207|ENGLAND|Elmbridge|44307|
|E07000208|ENGLAND|Epsom and Ewell|44308|
|E07000209|ENGLAND|Guildford|44309|
|E07000210|ENGLAND|Mole Valley|44310|
|E07000211|ENGLAND|Reigate and Banstead|44311|
|E07000212|ENGLAND|Runnymede|44312|
|E07000213|ENGLAND|Spelthorne|44313|
|E07000214|ENGLAND|Surrey Heath|44314|
|E07000215|ENGLAND|Tandridge|44315|
|E07000216|ENGLAND|Waverley|44316|
|E07000217|ENGLAND|Woking|44317|
|E07000218|ENGLAND|North Warwickshire|44318|
|E07000219|ENGLAND|Nuneaton and Bedworth|44319|
|E07000220|ENGLAND|Rugby|44320|
|E07000221|ENGLAND|Stratford-on-Avon|44321|
|E07000222|ENGLAND|Warwick|44322|
|E07000223|ENGLAND|Adur|44323|
|E07000224|ENGLAND|Arun|44324|
|E07000225|ENGLAND|Chichester|44325|
|E07000226|ENGLAND|Crawley|44326|
|E07000227|ENGLAND|Horsham|44327|
|E07000228|ENGLAND|Mid Sussex|44328|
|E07000229|ENGLAND|Worthing|44329|
|E07000234|ENGLAND|Bromsgrove|44334|
|E07000235|ENGLAND|Malvern Hills|44335|
|E07000236|ENGLAND|Redditch|44336|
|E07000237|ENGLAND|Worcester|44337|
|E07000238|ENGLAND|Wychavon|44338|
|E07000239|ENGLAND|Wyre Forest|44339|
|E07000240|ENGLAND|St Albans|44340|
|E07000241|ENGLAND|Welwyn Hatfield|44341|
|E07000242|ENGLAND|East Hertfordshire|44342|
|E07000243|ENGLAND|Stevenage|44343|
|E07000244|ENGLAND|East Suffolk|44344|
|E07000245|ENGLAND|West Suffolk|44345|
|E07000246|ENGLAND|Somerset West and Taunton|44346|
|E08000001|ENGLAND|Bolton|44351|
|E08000002|ENGLAND|Bury|44352|
|E08000003|ENGLAND|Manchester|44353|
|E08000004|ENGLAND|Oldham|44354|
|E08000005|ENGLAND|Rochdale|44355|
|E08000006|ENGLAND|Salford|44356|
|E08000007|ENGLAND|Stockport|44357|
|E08000008|ENGLAND|Tameside|44358|
|E08000009|ENGLAND|Trafford|44359|
|E08000010|ENGLAND|Wigan|44360|
|E08000011|ENGLAND|Knowsley|44361|
|E08000012|ENGLAND|Liverpool|44362|
|E08000013|ENGLAND|St. Helens|44363|
|E08000014|ENGLAND|Sefton|44364|
|E08000015|ENGLAND|Wirral|44365|
|E08000016|ENGLAND|Barnsley|44366|
|E08000017|ENGLAND|Doncaster|44367|
|E08000018|ENGLAND|Rotherham|44368|
|E08000019|ENGLAND|Sheffield|44369|
|E08000021|ENGLAND|Newcastle upon Tyne|44371|
|E08000022|ENGLAND|North Tyneside|44372|
|E08000023|ENGLAND|South Tyneside|44373|
|E08000024|ENGLAND|Sunderland|44374|
|E08000025|ENGLAND|Birmingham|44375|
|E08000026|ENGLAND|Coventry|44376|
|E08000027|ENGLAND|Dudley|44377|
|E08000028|ENGLAND|Sandwell|44378|
|E08000029|ENGLAND|Solihull|44379|
|E08000030|ENGLAND|Walsall|44380|
|E08000031|ENGLAND|Wolverhampton|44381|
|E08000032|ENGLAND|Bradford|44382|
|E08000033|ENGLAND|Calderdale|44383|
|E08000034|ENGLAND|Kirklees|44384|
|E08000035|ENGLAND|Leeds|44385|
|E08000036|ENGLAND|Wakefield|44386|
|E08000037|ENGLAND|Gateshead|44387|
|E09000001|ENGLAND|City of London|44401|
|E09000002|ENGLAND|Barking and Dagenham|44402|
|E09000003|ENGLAND|Barnet|44403|
|E09000004|ENGLAND|Bexley|44404|
|E09000005|ENGLAND|Brent|44405|
|E09000006|ENGLAND|Bromley|44406|
|E09000007|ENGLAND|Camden|44407|
|E09000008|ENGLAND|Croydon|44408|
|E09000009|ENGLAND|Ealing|44409|
|E09000010|ENGLAND|Enfield|44410|
|E09000011|ENGLAND|Greenwich|44411|
|E09000012|ENGLAND|Hackney|44412|
|E09000013|ENGLAND|Hammersmith and Fulham|44413|
|E09000014|ENGLAND|Haringey|44414|
|E09000015|ENGLAND|Harrow|44415|
|E09000016|ENGLAND|Havering|44416|
|E09000017|ENGLAND|Hillingdon|44417|
|E09000018|ENGLAND|Hounslow|44418|
|E09000019|ENGLAND|Islington|44419|
|E09000020|ENGLAND|Kensington and Chelsea|44420|
|E09000021|ENGLAND|Kingston upon Thames|44421|
|E09000022|ENGLAND|Lambeth|44422|
|E09000023|ENGLAND|Lewisham|44423|
|E09000024|ENGLAND|Merton|44424|
|E09000025|ENGLAND|Newham|44425|
|E09000026|ENGLAND|Redbridge|44426|
|E09000027|ENGLAND|Richmond upon Thames|44427|
|E09000028|ENGLAND|Southwark|44428|
|E09000029|ENGLAND|Sutton|44429|
|E09000030|ENGLAND|Tower Hamlets|44430|
|E09000031|ENGLAND|Waltham Forest|44431|
|E09000032|ENGLAND|Wandsworth|44432|
|E09000033|ENGLAND|Westminster|44433|
|E10000003|ENGLAND|Cambridgeshire|44453|
|E10000006|ENGLAND|Cumbria|44456|
|E10000007|ENGLAND|Derbyshire|44457|
|E10000008|ENGLAND|Devon|44458|
|E10000011|ENGLAND|East Sussex|44461|
|E10000012|ENGLAND|Essex|44462|
|E10000013|ENGLAND|Gloucestershire|44463|
|E10000014|ENGLAND|Hampshire|44464|
|E10000015|ENGLAND|Hertfordshire|44465|
|E10000016|ENGLAND|Kent|44466|
|E10000017|ENGLAND|Lancashire|44467|
|E10000018|ENGLAND|Leicestershire|44468|
|E10000019|ENGLAND|Lincolnshire|44469|
|E10000020|ENGLAND|Norfolk|44470|
|E10000023|ENGLAND|North Yorkshire|44473|
|E10000024|ENGLAND|Nottinghamshire|44474|
|E10000025|ENGLAND|Oxfordshire|44475|
|E10000027|ENGLAND|Somerset|44477|
|E10000028|ENGLAND|Staffordshire|44478|
|E10000029|ENGLAND|Suffolk|44479|
|E10000030|ENGLAND|Surrey|44480|
|E10000031|ENGLAND|Warwickshire|44481|
|E10000032|ENGLAND|West Sussex|44482|
|E10000034|ENGLAND|Worcestershire|44484|
|E11000001|ENGLAND|Greater Manchester|44501|
|E11000002|ENGLAND|Merseyside|44502|
|E11000003|ENGLAND|South Yorkshire|44503|
|E11000005|ENGLAND|West Midlands|44505|
|E11000006|ENGLAND|West Yorkshire|44506|
|E11000007|ENGLAND|Tyne and Wear|44507|
|E12000001|ENGLAND|North East|44521|
|E12000002|ENGLAND|North West|44522|
|E12000003|ENGLAND|Yorkshire and The Humber|44523|
|E12000004|ENGLAND|East Midlands|44524|
|E12000005|ENGLAND|West Midlands|44525|
|E12000006|ENGLAND|East of England|44526|
|E12000007|ENGLAND|London|44527|
|E12000008|ENGLAND|South East|44528|
|E12000009|ENGLAND|South West|44529|
|E47000001|ENGLAND|Greater Manchester|44541|
|E47000002|ENGLAND|Sheffield City Region|44542|
|E47000003|ENGLAND|West Yorkshire|44543|
|E47000004|ENGLAND|Liverpool City Region|44544|
|E47000006|ENGLAND|Tees Valley|44546|
|E47000007|ENGLAND|West Midlands|44547|
|E47000008|ENGLAND|Cambridgeshire and Peterborough|44548|
|E47000009|ENGLAND|West of England|44549|
|E47000010|ENGLAND|North East|44550|
|E47000011|ENGLAND|North of Tyne|44551|
|S12000005|SCOTLAND|Clackmannanshire|44605|
|S12000006|SCOTLAND|Dumfries and Galloway|44606|
|S12000008|SCOTLAND|East Ayrshire|44608|
|S12000010|SCOTLAND|East Lothian|44610|
|S12000011|SCOTLAND|East Renfrewshire|44611|
|S12000013|SCOTLAND|Na h-Eileanan Siar|44613|
|S12000014|SCOTLAND|Falkirk|44614|
|S12000017|SCOTLAND|Highland|44617|
|S12000018|SCOTLAND|Inverclyde|44618|
|S12000019|SCOTLAND|Midlothian|44619|
|S12000020|SCOTLAND|Moray|44620|
|S12000021|SCOTLAND|North Ayrshire|44621|
|S12000023|SCOTLAND|Orkney Islands|44623|
|S12000026|SCOTLAND|Scottish Borders|44626|
|S12000027|SCOTLAND|Shetland Islands|44627|
|S12000028|SCOTLAND|South Ayrshire|44628|
|S12000029|SCOTLAND|South Lanarkshire|44629|
|S12000030|SCOTLAND|Stirling|44630|
|S12000033|SCOTLAND|Aberdeen City|44633|
|S12000034|SCOTLAND|Aberdeenshire|44634|
|S12000035|SCOTLAND|Argyll and Bute|44635|
|S12000036|SCOTLAND|City of Edinburgh|44636|
|S12000038|SCOTLAND|Renfrewshire|44638|
|S12000039|SCOTLAND|West Dunbartonshire|44639|
|S12000040|SCOTLAND|West Lothian|44640|
|S12000041|SCOTLAND|Angus|44641|
|S12000042|SCOTLAND|Dundee City|44642|
|S12000045|SCOTLAND|East Dunbartonshire|44645|
|S12000047|SCOTLAND|Fife|44647|
|S12000048|SCOTLAND|Perth and Kinross|44648|
|S12000049|SCOTLAND|Glasgow City|44649|
|S12000050|SCOTLAND|North Lanarkshire|44650|
|W06000001|WALES|Isle of Anglesey|44701|
|W06000002|WALES|Gwynedd|44702|
|W06000003|WALES|Conwy|44703|
|W06000004|WALES|Denbighshire|44704|
|W06000005|WALES|Flintshire|44705|
|W06000006|WALES|Wrexham|44706|
|W06000008|WALES|Ceredigion|44708|
|W06000009|WALES|Pembrokeshire|44709|
|W06000010|WALES|Carmarthenshire|44710|
|W06000011|WALES|Swansea|44711|
|W06000012|WALES|Neath Port Talbot|44712|
|W06000013|WALES|Bridgend|44713|
|W06000014|WALES|Vale of Glamorgan|44714|
|W06000015|WALES|Cardiff|44715|
|W06000016|WALES|Rhondda Cynon Taf|44716|
|W06000018|WALES|Caerphilly|44718|
|W06000019|WALES|Blaenau Gwent|44719|
|W06000020|WALES|Torfaen|44720|
|W06000021|WALES|Monmouthshire|44721|
|W06000022|WALES|Newport|44722|
|W06000023|WALES|Powys|44723|
|W06000024|WALES|Merthyr Tydfil|44724|
|N09000001|NORTHERN IRELAND|Antrim and Newtownabbey|44801|
|N09000002|NORTHERN IRELAND|Armagh City, Banbridge and Craigavon|44802|
|N09000003|NORTHERN IRELAND|Belfast|44803|
|N09000004|NORTHERN IRELAND|Causeway Coast and Glens|44804|
|N09000005|NORTHERN IRELAND|Derry City and Strabane|44805|
|N09000006|NORTHERN IRELAND|Fermanagh and Omagh|44806|
|N09000007|NORTHERN IRELAND|Lisburn and Castlereagh|44807|
|N09000008|NORTHERN IRELAND|Mid and East Antrim|44808|
|N09000009|NORTHERN IRELAND|Mid Ulster|44809|
|N09000010|NORTHERN IRELAND|Newry, Mourne and Down|44810|
|N09000011|NORTHERN IRELAND|Ards and North Down|44811|
