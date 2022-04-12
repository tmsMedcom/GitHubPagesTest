# HospitalNotification

This FHIR&reg;&copy; standard is developed by [MedCom](https://www.medcom.dk/). HospitalNotification is a message based standard used to inform a municipality about hospitalization of a patient.

[1 Documentation](#1-documentation)
    [1.1 Non-technical guidelines](#11-non-technical-guidelines)
    [1.2 Use Cases](#12-use-cases)
    [1.3 Implementation Guide](#13-implementation-guide)
    [1.4 Mapping from XDIS20 and XDIS17 to HospitalNotification](#14-mapping-from-xdis20-and-xdis17-to-hospitalnotification)
[2 Introduction to the Content of a HospitalNotification Message](#2-introduction-to-the-content-of-a-hospitalnotification-message)

## 1 Documentation 

### 1.1 Non-technical guidelines 
Descibes the healthcare professional background for modernization of the standard. <br> 
[ENG-guideline](/documentation/NonTechnicalGuidelines_1.0.1.md)

### 1.2 Use Cases
Use cases are used to describe the different scenarios in which a standard can be used. <br> 
[ENG-Use Case](/documentation/UseCase_Eng.md)

### 1.3 Implementation Guide
The Implementation Guide (IG) can be found [here](https://build.fhir.org/ig/hl7dk/dk-medcom-hospitalnotification/). <br> 

### 1.4 Mapping from XDIS20 and XDIS17 to HospitalNotification
Mapping from previous OIOXML standard that has been modernized to HospitalNotification FHIR standard can be found below. Please notice, that not all elements from XDIS20 and XDIS17 are transfered to the FHIR message. Further not all elements from the FHIR message are represented in the document.  <br> 
[ENG-Mapping](/documentation/Map_between_OIOXML_and_FHIR_HospitalNotificationMessages-21-12-22.pdf)

## 2 Introduction to the Content of a HospitalNotification Message
HospitalNotification is a merely closed standard because the message is automatically sent and thus not based on patient consent. The legislation permits this exchange, but the message shall not contain more information than nessecary.

You can read more about the content of the FHIR profiles in a HospitalNotification message [here](documentation/HospitalNotification.md). 

## 3 Test and Certification
Find a general description of MedCom test and certification [here](https://tmsmedcom.github.io/GitHubPagesTest/#test-and-certification). 

### 3.1 Testprotocol
Coming soon... 

## 4 Release Notes

Updates in the latest release. 

## 5 Support or Contact

[MedCom](https://www.medcom.dk/) is responsible for this page.  
For any question regaring the standard, please contact <fhir@medcom.dk>