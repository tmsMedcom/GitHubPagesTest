### Scope and usage 
This profile is used as the Encounter resource for the HospitalNotification message. The HospitalNotificationEncounter inherits from the MedComCoreEncounter. 
Besides the references shown on the figure below, the MedComHospitalNotificationEncounter contains a status describing the status of the encounter e.g. if the patient is *onleave* and the class of the admission, which can be either *inpatient* or *emergency*. Both status and class shall be included in all messages. Additionally, shall an episode of care identifier be included.

The HospitalNotification message is sent without patient acceptance and only a limited data set is allowed to transmit due to Danish legislation. For this reason, is the HospitalNotificationEncounter profile quite narrow.

<img alt="The MedComHospitalNotificationEncounter references a subject which is a MedComCorePatient and a serviceProvider organization which is a MedComCoreOrganization." src="./hospitalnotification/HospitalNotificationEncounter.png" style="float:none; display:block; margin-left:auto; margin-right:auto;" />

Please refer to the tab "Snapshot Table(Must support)" below for the definition of the required content of a MedComHospitalNotificationEncounter.

