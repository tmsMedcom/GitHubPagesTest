# Introduction to HospitalNotification Message

This page aims to give a non-technical introduction to the acutal content of the standard. 

> In case of discrepancies between to [MedComHospitalNotification Implementation Guide (IG)](https://build.fhir.org/ig/hl7dk/dk-medcom-hospitalnotification) and this page, it will be the HospitalNotification IG which should be followed. Please contact <fhir@medcom.dk> if you find discrepandies.

On the figure below is the overall content of a HospitalNotification message. Each reqtangle represents a profile used in the standard. 
The pink color represents profiles from [MedComCore IG](https://build.fhir.org/ig/hl7dk/dk-medcom-core), the yellow color represents profiles from [MedComMessaging IG](https://build.fhir.org/ig/hl7dk/dk-medcom-messaging) and the blue color represents profiles from [MedComHospitalNotification IG](https://build.fhir.org/ig/hl7dk/dk-medcom-hospitalnotification). The hierarchical sturcture of the figure represents from where a profile is referenced.

![](/testSimpleDiagram.png)

The following figure uses the same colorcoding as the figure above. It is an example of an admission and finishing of an inpatient hospitalization. It includes the content that shall be present when sending a HospitalNotification message from a hospital to a municipality. <br>
The previous MedComMessagingProvenances in a stream of messages shall always be included, as it constitutes a history of the correspondance. All the id's are made up to simplify the example. They should be generated as UUID.

![](/HNAdmitFinish.png)



