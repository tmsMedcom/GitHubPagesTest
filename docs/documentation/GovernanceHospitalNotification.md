# Governance for MedCom HospitalNotification



## Exchange of HospitalNotification message 

The flow of events of a HospitalNotification message differs from the regular messageexchange over the VANS-network, as a message is exchange over the VANS-network and KOMBITs-network. Any questions regarding KOMBITs infrastructure, called Fælleskommunal infrastruktur, and KOMBIT's envelope, called Beskedfordeler-envelope, should be addressed to KOMBIT. 


### VANS-network and KOMBIT's Beskedfordeler
(INSERT sequensdiagram)

|Rules describing the flow of events when sending, and acknowledging a HospitalNotification message|
|:---|
|A Sending EcoSystem **SHALL** wrap a HospitalNotification in a VANS-envelope|
|The Fælleskommunal infratruktur **SHALL** unwrap a HospitalNotification in a VANS-envelope|
|The Fælleskommunal infratruktur **SHALL** wrap a HospitalNotification in a Beskedfordeler-envelope|
|A Receiving EcoSystem **SHALL** unwrap a HospitalNotification in a Kombit beskedfordeler kuvert|
|A Receiving EcoSystem **SHALL** wrap an Acknowledgement in a Kombit beskedfordeler kuvert|
|The Fælleskommunal infratruktur **SHALL** unwrap a Acknowledgement in a Beskedfordeler-envelope|
|The Fælleskommunal infratruktur **SHALL** wrap a Acknowledgement in a VANS-envelope|
|A Sending EcoSystem **SHALL** unwrap an Acknowledgement in a VANS-envelope|


### Acknowledgements

All MedCom FHIR messages **SHALL** be acknowledged, which is also valid for a HospitalNotification message. To acknowledge a HospitalNotification message the [MedCom FHIR Acknowledgement](https://medcomdk.github.io/dk-medcom-acknowledgement/) standard **SHALL** be used.

### Envelopes

When the HospitalNotification message is sent over the VANS-network, it **SHALL** be in a VANS-envelope. [This page describes the use of VANS-envelope](/docs/assets/documents/030_Governance-for-Network-Layer.md)

Values of fields used in a VANSenvelop **SHALL** obey to the [specifications described on the page for VANSenvelope](https://medcomdk.github.io/MedCom-FHIR-Communication/assets/documents/FHIRMessages_NetworkEnvelopes_EN.html#32-hospitalnotification) for a HospitalNotification message.

When the HospitalNotification message is sent over KOMBITs-network, it **SHALL** be in a beskedfordelerkuvert. [More information can be found on](kombit.dk)??? 

## HospitalNotification message

HospitalNotification follows [MedComs generic messaging model](https://medcomdk.github.io/dk-medcom-messaging/assets/documents/Intro-Technical-Spec-ENG.html#21-medcommessagingmessage-bundle), which is described on the GitHub pages for the messaging IG. To embrace the business requiries, the HospitalNotification standard expands the generic messaging model by including more profiles and rules. The structure and included profiles can be seen on <a href="#Fig2">Figure 2</a>. The rules can be found below the figure. 

<figure style="margin-left: 0px; margin-right: 0px; width: 100%;">
<a href="../images/HospitalNotification.svg" target="_blank"> <img src="../images/HospitalNotification.svg" alt="The structure and included profiles in HospitalNotification" style="width:auto; margin-left:0px; margin-right:0px;" id="Fig2"></a>
<figcaption text-align="left"><b>Figure 2: The structure and included profiles in HospitalNotification</b></figcaption>
</figure>
<br>

### MedComHospitalNotificationMessage profile

|Rule name|Rules used to constrain the possibilities in a MedComHospitalNotificationMessage profile|
|:---|:---|
|medcom-hospitalNotification-1 | The MessageHeader **SHALL** conform to MedComHospitalNotificationMessageHeader |
|medcom-hospitalNotification-2 | Entry **SHALL** contain exactly one patient resource |
|medcom-hospitalNotification-3 | All Provenance resources **SHALL** contain activities from medcom-hospitalNotification-messageActivities ValueSet |
|medcom-hospitalNotification-4 | The system of Patient.identifier **SHALL** be 'urn:oid:1.2.208.176.1.2', which represents an official Danish CPR-number |
|medcom-hospitalNotification-5 | The receiver of a HospitalNotification **SHALL** be a primary receiver. |
|medcom-messaging-2 | There **SHALL** be at least one Provenance resource in a MedCom message |
|medcom-messaging-3 | All Provenance resources shall conform to medcom-messaging-provenance profile |

<br>

### MedComHospitalNotificationEncounter profile

One episodeOfCare-identifier **SHALL** be included. 

|Rule name|Rules used to constrain the possibilities in a MedComHospitalNotificationEncounter profile|
|:---|:---|
|uuidv5 | The episodeOfCare-identifier **MAY** be an LPR3-identifier, which **SHALL** be an UUID version 5. |

### Provenance

I det første advis (STIN eller STAA) vil der altid kun være én provenance. Ved de efterfølgende adviser, vil antallet af provenance ressourcer være afhængigt af antallet af tidligere sendte adviser. Her vil den seneste tilføjet Provenance være tilknyttet selve adviset. Dette kan også verificeres ved at se på hvor Provenance.target og MessageHeader.id er ens.





