# UK National Numbering System for Road Authorities (RoadRegulatorID)

C-ITS messaging standards (CEN/ISO TS19091 and C-Roads MAPEM/SPATEM) require a nationally unique `RoadRegulatorID` to be assigned to traffic authorities.

## Considerations

* The `RoadRegulatorID` is specified as a 16-bit integer in the range 1 to 65535 which means that existing alphanumeric identifiers for road authorities (e.g. [Street Works Act Codes](https://www.gov.uk/government/publications/street-works-register/street-works-act-codes)) are not suitable.

* European signal companies have already adopted a convention of prefixing the `RoadRegulatorID` with the international dialling code for that country i.e. '44' for UK.  This convention restricts the number of unique `RoadRegulatorIDs` available in the UK to 1000 (i.e. 44000 to 44999 inclusive) which is constraining but not unworkable.

* For some early UK C-ITS implementations an additional convention was to use the last digits from local authority's Gegraphic Code as maintained by the [Office for National Statistics in their 'Register of Geographic Codes' (RGC)](https://geoportal.statistics.gov.uk/) e.g. as a Unitary Authority, York has a geographic code of E060000**14** so the chosen RoadRegulatorID was **44014** but this won't work nationally because local authorities have different administrative entity codes (e.g. for England: E06, E07, E08, E09, E10, E11, E12 etc.) hence duplicates will occur e.g. York is E06000014 and Congleton is E07000014 so both would result in 44014 as the RoadRegulatorID.

* It is acknowledged that not all road operators are local authorities.  Any national numbering scheme needs to allow for private traffic operators.

* For the avoidance of doubt, for our purposes, 'national' means England, Wales, Scotland and Northern Ireland.

## Current proposal

The currently proposed numbering system is based on ONS *administrative* Geographic Codes but applies a 'weighting' to the last 3 digits of the code based on the ONS entity code to avoid duplicates.  It also allows additional ranges for road operators who don't have ONS geographic codes e.g. National Highways and private operators.

Scottish data comes from thje [Scotland Register of GSS Codes](https://www.gov.scot/publications/small-area-statistics-reference-materials/)

| ONS Entity Code | Country | Description | RoadRegulatorID range | Weighting |
| --- | --- | --- | --- | --- |           
| E06 | England | Unitary Authorities | 44001 - 44099 | +0 |
| E07 | England | Non-metropolitan Districts | 44101 - 44349 | +100 |
| E08 | England | Metropolitan Districts | 44351 - 44399 | +350 |
| E09 | England | London Boroughs | 44401 - 44449 | +400 |
| E10 | England | Counties | 44451 - 44469 | +450 |
| E11 | England | Metropolitan Counties | 44501 - 44519 | +500 |
| E12 | England | Regions | 44521 - 44539 | +520 |
| E47 | England | Combined Authorities | 44541 - 44559 | +540 |
| - | England | RESERVED FOR FUTURE USE | 44560 - 44599 | - |
| S12 | Scotland | Council Areas | 44601 - 44699 | +600 |
| W06 | Wales | Unitary Authorities | 44701 - 44799 | +700 |
| N09 | Northern Ireland | Districts | 44801 - 44899 | +800 |
| - | England | National Highways | 44901 | - |
| - | Scotland | Traffic Scotland | 44902 | - |
| - | Northern Ireland | DfI Roads | 44903 | - |
| - | Wales | North & Mid Wales Trunk Road Agent (NMWTRA) | 44904 | - |
| - | Wales | South Wales Trunk Road Agent (SWTRA) | 44905 | - |
| - | - | PRIVATE OPERATORS / FUTURE USE | 44906 - 44999 | - |

## UK RoadRegulatorIDs (proposed)

| RoadRegulatorID | Authority | ONS code | Country |
|  ---  |  ---  |  ---  |  ---  |
| 44001 | Hartlepool | E06000001 | ENGLAND |
| 44002 | Middlesbrough | E06000002 | ENGLAND |
| 44003 | Redcar and Cleveland | E06000003 | ENGLAND |
| 44004 | Stockton-on-Tees | E06000004 | ENGLAND |
| 44005 | Darlington | E06000005 | ENGLAND |
| 44006 | Halton | E06000006 | ENGLAND |
| 44007 | Warrington | E06000007 | ENGLAND |
| 44008 | Blackburn with Darwen | E06000008 | ENGLAND |
| 44009 | Blackpool | E06000009 | ENGLAND |
| 44010 | Kingston upon Hull, City of | E06000010 | ENGLAND |
| 44011 | East Riding of Yorkshire | E06000011 | ENGLAND |
| 44012 | North East Lincolnshire | E06000012 | ENGLAND |
| 44013 | North Lincolnshire | E06000013 | ENGLAND |
| 44014 | York | E06000014 | ENGLAND |
| 44015 | Derby | E06000015 | ENGLAND |
| 44016 | Leicester | E06000016 | ENGLAND |
| 44017 | Rutland | E06000017 | ENGLAND |
| 44018 | Nottingham | E06000018 | ENGLAND |
| 44019 | Herefordshire, County of | E06000019 | ENGLAND |
| 44020 | Telford and Wrekin | E06000020 | ENGLAND |
| 44021 | Stoke-on-Trent | E06000021 | ENGLAND |
| 44022 | Bath and North East Somerset | E06000022 | ENGLAND |
| 44023 | Bristol, City of | E06000023 | ENGLAND |
| 44024 | North Somerset | E06000024 | ENGLAND |
| 44025 | South Gloucestershire | E06000025 | ENGLAND |
| 44026 | Plymouth | E06000026 | ENGLAND |
| 44027 | Torbay | E06000027 | ENGLAND |
| 44030 | Swindon | E06000030 | ENGLAND |
| 44031 | Peterborough | E06000031 | ENGLAND |
| 44032 | Luton | E06000032 | ENGLAND |
| 44033 | Southend-on-Sea | E06000033 | ENGLAND |
| 44034 | Thurrock | E06000034 | ENGLAND |
| 44035 | Medway | E06000035 | ENGLAND |
| 44036 | Bracknell Forest | E06000036 | ENGLAND |
| 44037 | West Berkshire | E06000037 | ENGLAND |
| 44038 | Reading | E06000038 | ENGLAND |
| 44039 | Slough | E06000039 | ENGLAND |
| 44040 | Windsor and Maidenhead | E06000040 | ENGLAND |
| 44041 | Wokingham | E06000041 | ENGLAND |
| 44042 | Milton Keynes | E06000042 | ENGLAND |
| 44043 | Brighton and Hove | E06000043 | ENGLAND |
| 44044 | Portsmouth | E06000044 | ENGLAND |
| 44045 | Southampton | E06000045 | ENGLAND |
| 44046 | Isle of Wight | E06000046 | ENGLAND |
| 44047 | County Durham | E06000047 | ENGLAND |
| 44049 | Cheshire East | E06000049 | ENGLAND |
| 44050 | Cheshire West and Chester | E06000050 | ENGLAND |
| 44051 | Shropshire | E06000051 | ENGLAND |
| 44052 | Cornwall | E06000052 | ENGLAND |
| 44053 | Isles of Scilly | E06000053 | ENGLAND |
| 44054 | Wiltshire | E06000054 | ENGLAND |
| 44055 | Bedford | E06000055 | ENGLAND |
| 44056 | Central Bedfordshire | E06000056 | ENGLAND |
| 44057 | Northumberland | E06000057 | ENGLAND |
| 44058 | Bournemouth, Christchurch and Poole | E06000058 | ENGLAND |
| 44059 | Dorset | E06000059 | ENGLAND |
| 44060 | Buckinghamshire | E06000060 | ENGLAND |
| 44061 | North Northamptonshire | E06000061 | ENGLAND |
| 44062 | West Northamptonshire | E06000062 | ENGLAND |
| 44108 | Cambridge | E07000008 | ENGLAND |
| 44109 | East Cambridgeshire | E07000009 | ENGLAND |
| 44110 | Fenland | E07000010 | ENGLAND |
| 44111 | Huntingdonshire | E07000011 | ENGLAND |
| 44112 | South Cambridgeshire | E07000012 | ENGLAND |
| 44126 | Allerdale | E07000026 | ENGLAND |
| 44127 | Barrow-in-Furness | E07000027 | ENGLAND |
| 44128 | Carlisle | E07000028 | ENGLAND |
| 44129 | Copeland | E07000029 | ENGLAND |
| 44130 | Eden | E07000030 | ENGLAND |
| 44131 | South Lakeland | E07000031 | ENGLAND |
| 44132 | Amber Valley | E07000032 | ENGLAND |
| 44133 | Bolsover | E07000033 | ENGLAND |
| 44134 | Chesterfield | E07000034 | ENGLAND |
| 44135 | Derbyshire Dales | E07000035 | ENGLAND |
| 44136 | Erewash | E07000036 | ENGLAND |
| 44137 | High Peak | E07000037 | ENGLAND |
| 44138 | North East Derbyshire | E07000038 | ENGLAND |
| 44139 | South Derbyshire | E07000039 | ENGLAND |
| 44140 | East Devon | E07000040 | ENGLAND |
| 44141 | Exeter | E07000041 | ENGLAND |
| 44142 | Mid Devon | E07000042 | ENGLAND |
| 44143 | North Devon | E07000043 | ENGLAND |
| 44144 | South Hams | E07000044 | ENGLAND |
| 44145 | Teignbridge | E07000045 | ENGLAND |
| 44146 | Torridge | E07000046 | ENGLAND |
| 44147 | West Devon | E07000047 | ENGLAND |
| 44161 | Eastbourne | E07000061 | ENGLAND |
| 44162 | Hastings | E07000062 | ENGLAND |
| 44163 | Lewes | E07000063 | ENGLAND |
| 44164 | Rother | E07000064 | ENGLAND |
| 44165 | Wealden | E07000065 | ENGLAND |
| 44166 | Basildon | E07000066 | ENGLAND |
| 44167 | Braintree | E07000067 | ENGLAND |
| 44168 | Brentwood | E07000068 | ENGLAND |
| 44169 | Castle Point | E07000069 | ENGLAND |
| 44170 | Chelmsford | E07000070 | ENGLAND |
| 44171 | Colchester | E07000071 | ENGLAND |
| 44172 | Epping Forest | E07000072 | ENGLAND |
| 44173 | Harlow | E07000073 | ENGLAND |
| 44174 | Maldon | E07000074 | ENGLAND |
| 44175 | Rochford | E07000075 | ENGLAND |
| 44176 | Tendring | E07000076 | ENGLAND |
| 44177 | Uttlesford | E07000077 | ENGLAND |
| 44178 | Cheltenham | E07000078 | ENGLAND |
| 44179 | Cotswold | E07000079 | ENGLAND |
| 44180 | Forest of Dean | E07000080 | ENGLAND |
| 44181 | Gloucester | E07000081 | ENGLAND |
| 44182 | Stroud | E07000082 | ENGLAND |
| 44183 | Tewkesbury | E07000083 | ENGLAND |
| 44184 | Basingstoke and Deane | E07000084 | ENGLAND |
| 44185 | East Hampshire | E07000085 | ENGLAND |
| 44186 | Eastleigh | E07000086 | ENGLAND |
| 44187 | Fareham | E07000087 | ENGLAND |
| 44188 | Gosport | E07000088 | ENGLAND |
| 44189 | Hart | E07000089 | ENGLAND |
| 44190 | Havant | E07000090 | ENGLAND |
| 44191 | New Forest | E07000091 | ENGLAND |
| 44192 | Rushmoor | E07000092 | ENGLAND |
| 44193 | Test Valley | E07000093 | ENGLAND |
| 44194 | Winchester | E07000094 | ENGLAND |
| 44195 | Broxbourne | E07000095 | ENGLAND |
| 44196 | Dacorum | E07000096 | ENGLAND |
| 44198 | Hertsmere | E07000098 | ENGLAND |
| 44199 | North Hertfordshire | E07000099 | ENGLAND |
| 44202 | Three Rivers | E07000102 | ENGLAND |
| 44203 | Watford | E07000103 | ENGLAND |
| 44205 | Ashford | E07000105 | ENGLAND |
| 44206 | Canterbury | E07000106 | ENGLAND |
| 44207 | Dartford | E07000107 | ENGLAND |
| 44208 | Dover | E07000108 | ENGLAND |
| 44209 | Gravesham | E07000109 | ENGLAND |
| 44210 | Maidstone | E07000110 | ENGLAND |
| 44211 | Sevenoaks | E07000111 | ENGLAND |
| 44212 | Folkestone and Hythe | E07000112 | ENGLAND |
| 44213 | Swale | E07000113 | ENGLAND |
| 44214 | Thanet | E07000114 | ENGLAND |
| 44215 | Tonbridge and Malling | E07000115 | ENGLAND |
| 44216 | Tunbridge Wells | E07000116 | ENGLAND |
| 44217 | Burnley | E07000117 | ENGLAND |
| 44218 | Chorley | E07000118 | ENGLAND |
| 44219 | Fylde | E07000119 | ENGLAND |
| 44220 | Hyndburn | E07000120 | ENGLAND |
| 44221 | Lancaster | E07000121 | ENGLAND |
| 44222 | Pendle | E07000122 | ENGLAND |
| 44223 | Preston | E07000123 | ENGLAND |
| 44224 | Ribble Valley | E07000124 | ENGLAND |
| 44225 | Rossendale | E07000125 | ENGLAND |
| 44226 | South Ribble | E07000126 | ENGLAND |
| 44227 | West Lancashire | E07000127 | ENGLAND |
| 44228 | Wyre | E07000128 | ENGLAND |
| 44229 | Blaby | E07000129 | ENGLAND |
| 44230 | Charnwood | E07000130 | ENGLAND |
| 44231 | Harborough | E07000131 | ENGLAND |
| 44232 | Hinckley and Bosworth | E07000132 | ENGLAND |
| 44233 | Melton | E07000133 | ENGLAND |
| 44234 | North West Leicestershire | E07000134 | ENGLAND |
| 44235 | Oadby and Wigston | E07000135 | ENGLAND |
| 44236 | Boston | E07000136 | ENGLAND |
| 44237 | East Lindsey | E07000137 | ENGLAND |
| 44238 | Lincoln | E07000138 | ENGLAND |
| 44239 | North Kesteven | E07000139 | ENGLAND |
| 44240 | South Holland | E07000140 | ENGLAND |
| 44241 | South Kesteven | E07000141 | ENGLAND |
| 44242 | West Lindsey | E07000142 | ENGLAND |
| 44243 | Breckland | E07000143 | ENGLAND |
| 44244 | Broadland | E07000144 | ENGLAND |
| 44245 | Great Yarmouth | E07000145 | ENGLAND |
| 44246 | King's Lynn and West Norfolk | E07000146 | ENGLAND |
| 44247 | North Norfolk | E07000147 | ENGLAND |
| 44248 | Norwich | E07000148 | ENGLAND |
| 44249 | South Norfolk | E07000149 | ENGLAND |
| 44263 | Craven | E07000163 | ENGLAND |
| 44264 | Hambleton | E07000164 | ENGLAND |
| 44265 | Harrogate | E07000165 | ENGLAND |
| 44266 | Richmondshire | E07000166 | ENGLAND |
| 44267 | Ryedale | E07000167 | ENGLAND |
| 44268 | Scarborough | E07000168 | ENGLAND |
| 44269 | Selby | E07000169 | ENGLAND |
| 44270 | Ashfield | E07000170 | ENGLAND |
| 44271 | Bassetlaw | E07000171 | ENGLAND |
| 44272 | Broxtowe | E07000172 | ENGLAND |
| 44273 | Gedling | E07000173 | ENGLAND |
| 44274 | Mansfield | E07000174 | ENGLAND |
| 44275 | Newark and Sherwood | E07000175 | ENGLAND |
| 44276 | Rushcliffe | E07000176 | ENGLAND |
| 44277 | Cherwell | E07000177 | ENGLAND |
| 44278 | Oxford | E07000178 | ENGLAND |
| 44279 | South Oxfordshire | E07000179 | ENGLAND |
| 44280 | Vale of White Horse | E07000180 | ENGLAND |
| 44281 | West Oxfordshire | E07000181 | ENGLAND |
| 44287 | Mendip | E07000187 | ENGLAND |
| 44288 | Sedgemoor | E07000188 | ENGLAND |
| 44289 | South Somerset | E07000189 | ENGLAND |
| 44292 | Cannock Chase | E07000192 | ENGLAND |
| 44293 | East Staffordshire | E07000193 | ENGLAND |
| 44294 | Lichfield | E07000194 | ENGLAND |
| 44295 | Newcastle-under-Lyme | E07000195 | ENGLAND |
| 44296 | South Staffordshire | E07000196 | ENGLAND |
| 44297 | Stafford | E07000197 | ENGLAND |
| 44298 | Staffordshire Moorlands | E07000198 | ENGLAND |
| 44299 | Tamworth | E07000199 | ENGLAND |
| 44300 | Babergh | E07000200 | ENGLAND |
| 44302 | Ipswich | E07000202 | ENGLAND |
| 44303 | Mid Suffolk | E07000203 | ENGLAND |
| 44307 | Elmbridge | E07000207 | ENGLAND |
| 44308 | Epsom and Ewell | E07000208 | ENGLAND |
| 44309 | Guildford | E07000209 | ENGLAND |
| 44310 | Mole Valley | E07000210 | ENGLAND |
| 44311 | Reigate and Banstead | E07000211 | ENGLAND |
| 44312 | Runnymede | E07000212 | ENGLAND |
| 44313 | Spelthorne | E07000213 | ENGLAND |
| 44314 | Surrey Heath | E07000214 | ENGLAND |
| 44315 | Tandridge | E07000215 | ENGLAND |
| 44316 | Waverley | E07000216 | ENGLAND |
| 44317 | Woking | E07000217 | ENGLAND |
| 44318 | North Warwickshire | E07000218 | ENGLAND |
| 44319 | Nuneaton and Bedworth | E07000219 | ENGLAND |
| 44320 | Rugby | E07000220 | ENGLAND |
| 44321 | Stratford-on-Avon | E07000221 | ENGLAND |
| 44322 | Warwick | E07000222 | ENGLAND |
| 44323 | Adur | E07000223 | ENGLAND |
| 44324 | Arun | E07000224 | ENGLAND |
| 44325 | Chichester | E07000225 | ENGLAND |
| 44326 | Crawley | E07000226 | ENGLAND |
| 44327 | Horsham | E07000227 | ENGLAND |
| 44328 | Mid Sussex | E07000228 | ENGLAND |
| 44329 | Worthing | E07000229 | ENGLAND |
| 44334 | Bromsgrove | E07000234 | ENGLAND |
| 44335 | Malvern Hills | E07000235 | ENGLAND |
| 44336 | Redditch | E07000236 | ENGLAND |
| 44337 | Worcester | E07000237 | ENGLAND |
| 44338 | Wychavon | E07000238 | ENGLAND |
| 44339 | Wyre Forest | E07000239 | ENGLAND |
| 44340 | St Albans | E07000240 | ENGLAND |
| 44341 | Welwyn Hatfield | E07000241 | ENGLAND |
| 44342 | East Hertfordshire | E07000242 | ENGLAND |
| 44343 | Stevenage | E07000243 | ENGLAND |
| 44344 | East Suffolk | E07000244 | ENGLAND |
| 44345 | West Suffolk | E07000245 | ENGLAND |
| 44346 | Somerset West and Taunton | E07000246 | ENGLAND |
| 44351 | Bolton | E08000001 | ENGLAND |
| 44352 | Bury | E08000002 | ENGLAND |
| 44353 | Manchester | E08000003 | ENGLAND |
| 44354 | Oldham | E08000004 | ENGLAND |
| 44355 | Rochdale | E08000005 | ENGLAND |
| 44356 | Salford | E08000006 | ENGLAND |
| 44357 | Stockport | E08000007 | ENGLAND |
| 44358 | Tameside | E08000008 | ENGLAND |
| 44359 | Trafford | E08000009 | ENGLAND |
| 44360 | Wigan | E08000010 | ENGLAND |
| 44361 | Knowsley | E08000011 | ENGLAND |
| 44362 | Liverpool | E08000012 | ENGLAND |
| 44363 | St. Helens | E08000013 | ENGLAND |
| 44364 | Sefton | E08000014 | ENGLAND |
| 44365 | Wirral | E08000015 | ENGLAND |
| 44366 | Barnsley | E08000016 | ENGLAND |
| 44367 | Doncaster | E08000017 | ENGLAND |
| 44368 | Rotherham | E08000018 | ENGLAND |
| 44369 | Sheffield | E08000019 | ENGLAND |
| 44371 | Newcastle upon Tyne | E08000021 | ENGLAND |
| 44372 | North Tyneside | E08000022 | ENGLAND |
| 44373 | South Tyneside | E08000023 | ENGLAND |
| 44374 | Sunderland | E08000024 | ENGLAND |
| 44375 | Birmingham | E08000025 | ENGLAND |
| 44376 | Coventry | E08000026 | ENGLAND |
| 44377 | Dudley | E08000027 | ENGLAND |
| 44378 | Sandwell | E08000028 | ENGLAND |
| 44379 | Solihull | E08000029 | ENGLAND |
| 44380 | Walsall | E08000030 | ENGLAND |
| 44381 | Wolverhampton | E08000031 | ENGLAND |
| 44382 | Bradford | E08000032 | ENGLAND |
| 44383 | Calderdale | E08000033 | ENGLAND |
| 44384 | Kirklees | E08000034 | ENGLAND |
| 44385 | Leeds | E08000035 | ENGLAND |
| 44386 | Wakefield | E08000036 | ENGLAND |
| 44387 | Gateshead | E08000037 | ENGLAND |
| 44401 | City of London | E09000001 | ENGLAND |
| 44402 | Barking and Dagenham | E09000002 | ENGLAND |
| 44403 | Barnet | E09000003 | ENGLAND |
| 44404 | Bexley | E09000004 | ENGLAND |
| 44405 | Brent | E09000005 | ENGLAND |
| 44406 | Bromley | E09000006 | ENGLAND |
| 44407 | Camden | E09000007 | ENGLAND |
| 44408 | Croydon | E09000008 | ENGLAND |
| 44409 | Ealing | E09000009 | ENGLAND |
| 44410 | Enfield | E09000010 | ENGLAND |
| 44411 | Greenwich | E09000011 | ENGLAND |
| 44412 | Hackney | E09000012 | ENGLAND |
| 44413 | Hammersmith and Fulham | E09000013 | ENGLAND |
| 44414 | Haringey | E09000014 | ENGLAND |
| 44415 | Harrow | E09000015 | ENGLAND |
| 44416 | Havering | E09000016 | ENGLAND |
| 44417 | Hillingdon | E09000017 | ENGLAND |
| 44418 | Hounslow | E09000018 | ENGLAND |
| 44419 | Islington | E09000019 | ENGLAND |
| 44420 | Kensington and Chelsea | E09000020 | ENGLAND |
| 44421 | Kingston upon Thames | E09000021 | ENGLAND |
| 44422 | Lambeth | E09000022 | ENGLAND |
| 44423 | Lewisham | E09000023 | ENGLAND |
| 44424 | Merton | E09000024 | ENGLAND |
| 44425 | Newham | E09000025 | ENGLAND |
| 44426 | Redbridge | E09000026 | ENGLAND |
| 44427 | Richmond upon Thames | E09000027 | ENGLAND |
| 44428 | Southwark | E09000028 | ENGLAND |
| 44429 | Sutton | E09000029 | ENGLAND |
| 44430 | Tower Hamlets | E09000030 | ENGLAND |
| 44431 | Waltham Forest | E09000031 | ENGLAND |
| 44432 | Wandsworth | E09000032 | ENGLAND |
| 44433 | Westminster | E09000033 | ENGLAND |
| 44453 | Cambridgeshire | E10000003 | ENGLAND |
| 44456 | Cumbria | E10000006 | ENGLAND |
| 44457 | Derbyshire | E10000007 | ENGLAND |
| 44458 | Devon | E10000008 | ENGLAND |
| 44461 | East Sussex | E10000011 | ENGLAND |
| 44462 | Essex | E10000012 | ENGLAND |
| 44463 | Gloucestershire | E10000013 | ENGLAND |
| 44464 | Hampshire | E10000014 | ENGLAND |
| 44465 | Hertfordshire | E10000015 | ENGLAND |
| 44466 | Kent | E10000016 | ENGLAND |
| 44467 | Lancashire | E10000017 | ENGLAND |
| 44468 | Leicestershire | E10000018 | ENGLAND |
| 44469 | Lincolnshire | E10000019 | ENGLAND |
| 44470 | Norfolk | E10000020 | ENGLAND |
| 44473 | North Yorkshire | E10000023 | ENGLAND |
| 44474 | Nottinghamshire | E10000024 | ENGLAND |
| 44475 | Oxfordshire | E10000025 | ENGLAND |
| 44477 | Somerset | E10000027 | ENGLAND |
| 44478 | Staffordshire | E10000028 | ENGLAND |
| 44479 | Suffolk | E10000029 | ENGLAND |
| 44480 | Surrey | E10000030 | ENGLAND |
| 44481 | Warwickshire | E10000031 | ENGLAND |
| 44482 | West Sussex | E10000032 | ENGLAND |
| 44484 | Worcestershire | E10000034 | ENGLAND |
| 44501 | Greater Manchester | E11000001 | ENGLAND |
| 44502 | Merseyside | E11000002 | ENGLAND |
| 44503 | South Yorkshire | E11000003 | ENGLAND |
| 44505 | West Midlands | E11000005 | ENGLAND |
| 44506 | West Yorkshire | E11000006 | ENGLAND |
| 44507 | Tyne and Wear | E11000007 | ENGLAND |
| 44521 | North East | E12000001 | ENGLAND |
| 44522 | North West | E12000002 | ENGLAND |
| 44523 | Yorkshire and The Humber | E12000003 | ENGLAND |
| 44524 | East Midlands | E12000004 | ENGLAND |
| 44525 | West Midlands | E12000005 | ENGLAND |
| 44526 | East of England | E12000006 | ENGLAND |
| 44527 | London | E12000007 | ENGLAND |
| 44528 | South East | E12000008 | ENGLAND |
| 44529 | South West | E12000009 | ENGLAND |
| 44541 | Greater Manchester | E47000001 | ENGLAND |
| 44542 | Sheffield City Region | E47000002 | ENGLAND |
| 44543 | West Yorkshire | E47000003 | ENGLAND |
| 44544 | Liverpool City Region | E47000004 | ENGLAND |
| 44546 | Tees Valley | E47000006 | ENGLAND |
| 44547 | West Midlands | E47000007 | ENGLAND |
| 44548 | Cambridgeshire and Peterborough | E47000008 | ENGLAND |
| 44549 | West of England | E47000009 | ENGLAND |
| 44550 | North East | E47000010 | ENGLAND |
| 44551 | North of Tyne | E47000011 | ENGLAND |
| 44605 | Clackmannanshire | S12000005 | SCOTLAND |
| 44606 | Dumfries and Galloway | S12000006 | SCOTLAND |
| 44608 | East Ayrshire | S12000008 | SCOTLAND |
| 44610 | East Lothian | S12000010 | SCOTLAND |
| 44611 | East Renfrewshire | S12000011 | SCOTLAND |
| 44613 | Na h-Eileanan Siar | S12000013 | SCOTLAND |
| 44614 | Falkirk | S12000014 | SCOTLAND |
| 44617 | Highland | S12000017 | SCOTLAND |
| 44618 | Inverclyde | S12000018 | SCOTLAND |
| 44619 | Midlothian | S12000019 | SCOTLAND |
| 44620 | Moray | S12000020 | SCOTLAND |
| 44621 | North Ayrshire | S12000021 | SCOTLAND |
| 44623 | Orkney Islands | S12000023 | SCOTLAND |
| 44626 | Scottish Borders | S12000026 | SCOTLAND |
| 44627 | Shetland Islands | S12000027 | SCOTLAND |
| 44628 | South Ayrshire | S12000028 | SCOTLAND |
| 44629 | South Lanarkshire | S12000029 | SCOTLAND |
| 44630 | Stirling | S12000030 | SCOTLAND |
| 44633 | Aberdeen City | S12000033 | SCOTLAND |
| 44634 | Aberdeenshire | S12000034 | SCOTLAND |
| 44635 | Argyll and Bute | S12000035 | SCOTLAND |
| 44636 | City of Edinburgh | S12000036 | SCOTLAND |
| 44638 | Renfrewshire | S12000038 | SCOTLAND |
| 44639 | West Dunbartonshire | S12000039 | SCOTLAND |
| 44640 | West Lothian | S12000040 | SCOTLAND |
| 44641 | Angus | S12000041 | SCOTLAND |
| 44642 | Dundee City | S12000042 | SCOTLAND |
| 44645 | East Dunbartonshire | S12000045 | SCOTLAND |
| 44647 | Fife | S12000047 | SCOTLAND |
| 44648 | Perth and Kinross | S12000048 | SCOTLAND |
| 44649 | Glasgow City | S12000049 | SCOTLAND |
| 44650 | North Lanarkshire | S12000050 | SCOTLAND |
| 44701 | Isle of Anglesey | W06000001 | WALES |
| 44702 | Gwynedd | W06000002 | WALES |
| 44703 | Conwy | W06000003 | WALES |
| 44704 | Denbighshire | W06000004 | WALES |
| 44705 | Flintshire | W06000005 | WALES |
| 44706 | Wrexham | W06000006 | WALES |
| 44708 | Ceredigion | W06000008 | WALES |
| 44709 | Pembrokeshire | W06000009 | WALES |
| 44710 | Carmarthenshire | W06000010 | WALES |
| 44711 | Swansea | W06000011 | WALES |
| 44712 | Neath Port Talbot | W06000012 | WALES |
| 44713 | Bridgend | W06000013 | WALES |
| 44714 | Vale of Glamorgan | W06000014 | WALES |
| 44715 | Cardiff | W06000015 | WALES |
| 44716 | Rhondda Cynon Taf | W06000016 | WALES |
| 44718 | Caerphilly | W06000018 | WALES |
| 44719 | Blaenau Gwent | W06000019 | WALES |
| 44720 | Torfaen | W06000020 | WALES |
| 44721 | Monmouthshire | W06000021 | WALES |
| 44722 | Newport | W06000022 | WALES |
| 44723 | Powys | W06000023 | WALES |
| 44724 | Merthyr Tydfil | W06000024 | WALES |
| 44801 | Antrim and Newtownabbey | N09000001 | NORTHERN IRELAND |
| 44802 | Armagh City, Banbridge and Craigavon | N09000002 | NORTHERN IRELAND |
| 44803 | Belfast | N09000003 | NORTHERN IRELAND |
| 44804 | Causeway Coast and Glens | N09000004 | NORTHERN IRELAND |
| 44805 | Derry City and Strabane | N09000005 | NORTHERN IRELAND |
| 44806 | Fermanagh and Omagh | N09000006 | NORTHERN IRELAND |
| 44807 | Lisburn and Castlereagh | N09000007 | NORTHERN IRELAND |
| 44808 | Mid and East Antrim | N09000008 | NORTHERN IRELAND |
| 44809 | Mid Ulster | N09000009 | NORTHERN IRELAND |
| 44810 | Newry, Mourne and Down | N09000010 | NORTHERN IRELAND |
| 44811 | Ards and North Down | N09000011 | NORTHERN IRELAND |
| 44901 | National Highways |  | ENGLAND |
| 44902 | Traffic Scotland |  | SCOTLAND |
| 44903 | DfI Roads |  | NORTHERN IRELAND |
| 44904 | North & Mid Wales Trunk Road Agent (NMWTRA) |  | WALES |
| 44905 | South Wales Trunk Road Agent (SWTRA) |  | WALES |

