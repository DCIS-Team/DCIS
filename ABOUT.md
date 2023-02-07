# Digital (Traffic Signal) Controller Interface Specification

The DCIS project is run by the UK Department for Transport and is a working group tasked with establishing standards for the digitisation of traffic signal controller configuration.

## National Numbering System for Road Authorities

C-ITS messaging standards (SAE J2735 and CEN/ISO TS19091) require a nationally unique RoadRegulatorID to be assigned to traffic authorities.  This is a 16-bit integer in the range 1 to 65535.

## Signalised Intersection Numbering

Each signalised intersection requires an IntersectionID which is assigned by the RoadRegulator.  This is a 16-bit integer in the range 256 to 65535.

## Signalised Intersection Definition

A JSON schema defining intersection turning movement logic aligned with CEN/IS TS19091 MAPEM standards.

## Digitised Traffic Signal Controller Configuration

A JSON schema defining the configuration of a traffic signal controller.