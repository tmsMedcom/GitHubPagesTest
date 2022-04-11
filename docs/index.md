## HospitalNotification

This FHIR&reg;&copy; standard is developed by [MedCom](https://www.medcom.dk/). HospitalNotification is a message based standard used to inform a municipality about hospitalization of a patient.

|   [Non-technical guidelines](#non-technical-guidelines)   |   [Use Cases](#use-cases)   |   [Implementation Guide](#implementation-guide)   |   [Test and Certification](#test-and-certification)   |

### Introduction to HospitalNotification
HospitalNotification is a merely closed standard because the message is automatically sent and thus not based on patient consent. The legislation permits this exchange, but the message shall not contain more information than nessecary.

You can read more about the content of a HospitalNotification message [here](documentation/HospitalNotification.md) 

### Documentation 

#### Non-technical guidelines 
Descibes the background and the healthcare professional background for modernization of the standard. 
[ENG-guideline](/documentation/NonTechnicalGuidelines_1.0.1.md)

#### Use Cases
Use cases are used to describe the different scenarios in which a standard can be used. 
[ENG-Use Case](/documentation/UseCase_Eng.md)

#### Implementation Guide
The Implementation Guide (IG) can be found [here](https://build.fhir.org/ig/hl7dk/dk-medcom-hospitalnotification/).

#### Mapping from XDISxx to HospitalNotification
Mapping from previous OIOXML standard that has been modernized to HospitalNotification FHIR standard can be found below. Please notice, that not all elements from XDIS.. are transfered to the FHIR message. Further not all elements from the FHIR message are represented in the document. 

[ENG-Use Case](/documentation/Map_between_OIOXML_and_FHIR_HospitalNotificationMessages-21-12-22.pdf)

### Test and Certification
Find a general description of MedCom test and certification [here](https://tmsmedcom.github.io/GitHubPagesTest/#test-and-certification). 

#### Testprotocol
Coming soon... 

### Release Notes

Updates in the latest release. 

### Support or Contact

[MedCom](https://www.medcom.dk/) is responsible for this page.  
For any question regaring the standard, please contact <fhir@medcom.dk>