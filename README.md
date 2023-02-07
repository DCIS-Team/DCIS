# Digital (Traffic Signal) Controller Interface Specification

The DCIS project is a working group under the Transport Technology Forum sponsored by the UK Department for Transport and is tasked with establishing standards for the digitisation of traffic signal controller configurations ensuring alignment with these relevant standards:

* [TOPAS2500 2500B Specification for Traffic Signal Controllers](https://topasgroup.org.uk/specification/topas-2500b/)
* [CEN ISO/TS 19091 Intelligent transport systems — Cooperative ITS — Using V2I and I2V communications for applications related to signalized intersections](https://www.iso.org/standard/73781.html)
* [C-Roads C-ITS European Handbook for MAPEM and SPATEM Creation](https://www.c-roads.eu/platform.html)

## Contents

The DCIS project is split into 4 discrete areas as below:

1. [UK national numbering system for traffic authorities (RoadRegulatorID)](/01_traffic_authority_numbering.md)
2. [Intersection Numbering (IntersectionID)](/02_intersection_numbering.md)
3. [Signalised Intersection Definition - aligned with CEN ISO/TS 19091 (MAPEM/SPATEM)](/03_intersection_definition.md)
4. [Traffic Signal Controller Configuration - digitisation of TOPAS2500](/04_controller_configuration.md)

## The problem

Most traffic signals in the UK and around the world are operated by dedicated `controller` hardware, which normally are highly specialised computer-based systems located in roadside cabinets. They determine the way in which the individual lights are illuminated at a given time, known as `phases` and the sequence they appear in, known as `stages`. The operation of the `controller` is influenced by traffic detection systems and software to maximise the efficiency of the junction. This is commonly the MOVA system that is hosted within the controller itself or SCOOT which operates across multiple junctions from a remote location.

In all cases, however it is the roadside `controller` that is ultimately responsible for the safe and proper operation of the junction. The logic that controls the `phases` and `stages`, the interaction of optimisation systems, and communications into the controller is currently defined by the [TOPAS2500 specification](https://topasgroup.org.uk/specification/topas-2500b/) which is maintained by the [Topas Group](https://topasgroup.org.uk/) and generally takes the form of a paper document, PDF form or non-standard spreadsheet. This sets out the operations the junction is able to perform and those which are prohibited, how the junction is to be configured to ensure it operates as required by the legislation and how the minimum safety standards and fault tolerances are to be applied. It also includes elements that describe site geography, road and lane layout and any special conditions that apply.

No standard digital model exists for describing [TOPAS2500 specification](https://topasgroup.org.uk/specification/topas-2500b/) for others to use and so this key element of road infrastructure is not compatible with the increasing use of digital systems we are seeing develop. Satnav makers, traffic planners and modellers, maintenance teams and connected / automated vehicles would benefit enormously from this data, but their systems cannot access what is currently an essentially paper or pdf-based data model.

Having this data, for the roughly 35,000 traffic signal sites in the UK accessible by automated systems in a common, open-standard national data model would greatly simplify the production of digital twins of road systems, allow for much more efficient traffic modelling, drive the adoption of services like Green Light Advice that link traffic signals to vehicles and make procurement and maintenance simpler and cheaper. Such opportunities could help to reduce emissions and carbon, potentially improve safety, and reduce road network operation and maintenance costs, as well as providing better services for public transport, active travel and vulnerable road users.

## The solution

Whilst it is not proposed to fundamentally alter or replace the [TOPAS2500 specification](https://topasgroup.org.uk/specification/topas-2500b/), there is a strong case to move controller definition that this standard mandates to a 'digital first' model. This would make accurate, standardised data easily available for wider use to meet the opportunities outlined above and would support the provision of traffic signal logic and geometry data through emerging data channels such as the DfT National Access Point (a.k.a. Find Transport Data). Currently each traffic signal supplier has a unique and proprietary approach to handling paper or spreadsheet form TOPAS2500 data and so the value this could have to a variety of stakeholders is diminished.

The DfT, through the [Transport Technology Forum (TTF)](https://https://ttf.uk.net/) has commissioned White Willow Consulting Ltd to lead an industry group to develop DCIS, the **Digital Controller Interface Specification** to address this challenge. DCIS will move the paper form to a digital model that describes the junction logic and geography defined by [TOPAS2500 specification](https://topasgroup.org.uk/specification/topas-2500b/) and will allow integration with the modelling systems that digital twins use and the international C-ITS standards (specifically [CEN ISO/TS 19091](https://www.iso.org/standard/73781.html)) that connected and automated vehicles use.

DCIS has identified eleven high level end-user cases based on and expanding the work of the Europe-wide [C-Roads Platform](https://www.c-roads.eu/platform.html) and started to consider the ways in which a digital model of traffic signal operation will make their realisation and adoption easier. Examples of sectors who would benefit from this in developing new services include emerging traffic simulation companies, satnav providers, road network modellers and tier one and two automotive suppliers.
DCIS development is still in its infancy and has not yet gone deeper than scratching the surface of the key use cases. It has not yet developed alignment with other developments such as Digital Twins, the wider road networks that feed into signalised junctions or the underground assets that lie beneath them. Hence DCIS is currently a 'traffic signals world' view and needs to develop its use cases for traffic authorities, road users and integration with other digital twins in more depth.

## The benefits

DCIS will develop a digital model of the [TOPAS2500 specification](https://topasgroup.org.uk/specification/topas-2500b/) allowing it to be described in a structured data format (JSON or XML) which would solve the problems of a paper/ pdf / spreadsheet-based system and create important new opportunities for data sharing and service development. It could:

* Allow better modelling of how signals work in complicated use cases, for example with a mixed legacy and automated traffic mix
* Link with other digital twins to reduce risks and costs – for example utilities often dig up traffic loops in the road that are vital to sensing traffic to reduce congestion and emissions, yet their digital twin may not have this data
* Enable a central store of all UK signal configurations for satnav companies and others, rather than the current 150+ traffic authority points of contact
* Avoid the errors and delays inherent in manual coding from paper forms
* Enable usable rules for automated vehicles, with machine-to-machine data the default
* Enable dynamic changes to signal controller logic to be published to vehicles
* Make accurate satnav updates much more rapid
* Reduce the cost of building traffic models – for example, we estimate that City of York Council spent £30k finding, reading and coding paper forms
* Allow interoperable digital manufacturing of controllers, and eventually remote software definition of their logic
* Reduce traffic signal maintenance and replacement costs, by enabling configuration settings to be accessed and transferred digitally
* Enable new services geared to emerging automated vehicles

A particular area of benefit could be around temporary and portable signals, as they have ever changing locations and configurations, yet make up 20% of the signals in the UK and can cause significant delay and emissions. There is an opportunity to align with the current review of the [DfT Pink Book](https://www.gov.uk/government/publications/introduction-to-the-use-of-portable-vehicular-signals) standards that govern how temporary signals are set up.

> The desired outcome is that “digital signals” will become business as usual for a traffic authority, with automated linking of data to other initiatives such as Digital Traffic Regulation Orders, to check that the controller logic for a junction is actually supported legally by a TRO for example, and to Street Manager, to allow temporary signals and the permitted works that they protect to be linked. They will also align with the international standards needed for current connected and future automated vehicles.

## Where is DCIS today?

The DCIS team has developed an outline JSON conceptual model and the 'schema' that makes it easy to use. This allows testing to be commenced based on a single sample junction from one controller manufacturer and suggests that a significant proportion of the functionality of over 80% of UK traffic signal sites could be covered by a relatively simple model. For the remaining 20% of sites, which are generally complex junctions or roundabout / gyratory systems, or where interactions with railways or trams occur, additional development work will be required. The initial model is being tested currently. It also has yet to be expanded to include the lane geography of the junction that automated vehicles need.

The project has also developed a way for uniquely numbering each signalised intersection in the UK, as it is essential to move away from the authority-based numbering systems currently in use which can result in many duplicates site numbers across the UK.

By developing more and wider use cases based around traffic authority practice and experience, and deepening those that have been skimmed already, a better model for wider adoption will be developed. DCIS will also raise awareness of 'digital first' thinking and join up with other digital projects, such as utilities under the junction and the roads linking into it, or to help develop tools for making junction modelling and coding simpler.

## What are the next steps?

The Project Team will:

* Continue to consult with more traffic modelling companies and begin our consultation with signal companies
* Engage with other digital twin initiatives, CCAV, and other parts of DfT
* Consult widely with stakeholders on the proposed UK numbering system for controllers
* Improve the JSON model following feedback
* Work with signal companies to explore how transition might occur

For more information contact: <andy@whitewillow.biz>

# Diagrams

## Scope of the DCIS project

![DCIS Scope](/images/dcis_overview.png)

## Proposed Digital TOPAS2500 Document Structure

![Digital TOPAS2500 Document structure](/images/topas2500_document_structure.png)

## Schematic of an intersection

![Intersection Definition Diagram](/images/intersection_definition.png)

<div>
<span><img src="images/dft_logo.svg" alt="Department for Transport Logo" width="150px" /><span>
<span><img src="images/ttf_logo.png" alt="Transport Technology Forum Logo" width="150px" /><span>
<span><img src="images/topas_logo.png" alt="Topas Logo" width="150px" /><span>
<span><img src="images/croads_logo.svg" alt="C-Roads Logo" width="150px" /><span>
</div>
