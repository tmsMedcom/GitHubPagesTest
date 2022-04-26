# Introduction to HospitalNotification Implementation Guide

This page aims to give a non-technical introduction to the acutal content of the standard. 

> In case of discrepancies between to [MedComHospitalNotification Implementation Guide (IG)](https://build.fhir.org/ig/hl7dk/dk-medcom-hospitalnotification) and this page, it is the HospitalNotification IG which should be followed. Please contact <fhir@medcom.dk> if you find discrepandies.

On the figure below is the overall content of a HospitalNotification message. Each reqtangle represents a profile used in the standard. 
The pink color represents profiles from [MedComCore IG](https://build.fhir.org/ig/hl7dk/dk-medcom-core), the yellow color represents profiles from [MedComMessaging IG](https://build.fhir.org/ig/hl7dk/dk-medcom-messaging) and the blue color represents profiles from [MedComHospitalNotification IG](https://build.fhir.org/ig/hl7dk/dk-medcom-hospitalnotification). The hierarchical sturcture of the figure represents from where a profile is referenced.

![](/testSimpleDiagram.png)

The following figure uses the same colorcoding as the figure above. It is an example of an admission and finishing of an inpatient hospitalization. It includes the content that shall be present when sending a HospitalNotification message from a hospital to a municipality. <br>
The previous MedComMessagingProvenances in a stream of messages shall always be included, as it constitutes a history of the correspondance. All the id's are made up to simplify the example. They should be generated as UUID.

![](/HNAdmitFinish.png)

``` xml
<creator>
  <!--MedComHospitalNotificationMessage = Bundle begins here-->
  <Bundle xmlns="http://hl7.org/fhir">
    <id value="15e5b880-c087-4055-b9ec-99108695f81d"/>
    <meta>
      <profile
              value="http://medcomfhir.dk/fhir/hospitalnotification/StructureDefinition/medcom-hospitalNotification-message"/>
    </meta>
    <type value="message"/> <!--This is a message-->
    <timestamp value="2020-10-15T13:44:14Z"/> <!--When the message was created-->
    <!--MedComHospitalNotificationMessageHeader = MessageHeader begins here.-->
    <entry>
      <fullUrl value="MessageHeader/29b4818e-02de-4cc4-b418-d20cbc7b5404"/>
      <resource>
        <MessageHeader>
          <id value="29b4818e-02de-4cc4-b418-d20cbc7b5404"/>
          <meta>
            <profile
                    value="http://medcomfhir.dk/fhir/hospitalnotification/StructureDefinition/medcom-hospitalNotification-messageHeader"/>
          </meta>
          <text> <!--Narrative text-->
            <status value="extensions"/>
            <div xmlns="http://www.w3.org/1999/xhtml"><p><b>Generated Narrative</b></p><div style="display: inline-block; background-color: #d9e0e7; padding: 6px; margin: 4px; border: 1px solid #8da1b4; border-radius: 5px; line-height: 60%"><p style="margin-bottom: 0px">Resource "29b4818e-02de-4cc4-b418-d20cbc7b5404" </p><p style="margin-bottom: 0px">Profile: <a href="StructureDefinition-medcom-hospitalNotification-messageHeader.html">MedComHospitalNotificationMessageHeader</a></p></div><p><b>MedComReportOfAdmissionExtension</b>: false</p><p><b>event</b>: Hospital Notification Message (Details: http://medcomfhir.dk/fhir/messaging/CodeSystem/medcom-messaging-eventCodes code hospital-notification-message = 'Hospital Notification Message', stated as 'null')</p><h3>Destinations</h3><table class="grid"><tr><td>-</td><td><b>Extension</b></td><td><b>Endpoint</b></td><td><b>Receiver</b></td></tr><tr><td>*</td><td></td><td><a href="http://medcom.dk/unknown">http://medcom.dk/unknown</a></td><td><a href="#Organization_74cdf292-abf3-4f5f-80ea-60a48013ff6d">See above (Organization/74cdf292-abf3-4f5f-80ea-60a48013ff6d)</a></td></tr></table><p><b>sender</b>: <a href="#Organization_d7056980-a8b2-42aa-8a0e-c1fc85d1f40d">See above (Organization/d7056980-a8b2-42aa-8a0e-c1fc85d1f40d)</a></p><h3>Sources</h3><table class="grid"><tr><td>-</td><td><b>Endpoint</b></td></tr><tr><td>*</td><td><a href="http://medcom.dk/unknown">http://medcom.dk/unknown</a></td></tr></table><p><b>focus</b>: <a href="#Encounter_7790f964-88d3-4652-bbc8-81d2f3d035f8">See above (Encounter/7790f964-88d3-4652-bbc8-81d2f3d035f8)</a></p></div>
          </text>
          <extension
                    url="http://medcomfhir.dk/fhir/hospitalnotification/StructureDefinition/medcom-messaging-reportOfAdmissionExtension">
            <valueBoolean value="false"/> <!--No report of admission (Danish: indlæggelsesrapport) shall be returned-->
          </extension>
          <eventCoding>
            <system
                    value="http://medcomfhir.dk/fhir/messaging/CodeSystem/medcom-messaging-eventCodes"/>
            <code value="hospital-notification-message"/> <!--Type of message-->
          </eventCoding>
          <destination>
            <extension
                      url="http://medcomfhir.dk/fhir/messaging/StructureDefinition/medcom-messaging-destinationUseExtension">
              <valueCoding>
                <system
                        value="http://medcomfhir.dk/fhir/messaging/CodeSystem/medcom-messaging-destinationUse"/>
                <code value="primary"/>
              </valueCoding>
            </extension>
            <endpoint value="http://medcom.dk/unknown"/>
            <receiver>
              <reference value="Organization/74cdf292-abf3-4f5f-80ea-60a48013ff6d"/> <!--Receiver organization-->
            </receiver>
          </destination>
          <sender>
            <reference value="Organization/d7056980-a8b2-42aa-8a0e-c1fc85d1f40d"/> <!--Sender organization-->
          </sender>
          <source>
            <endpoint value="http://medcom.dk/unknown"/>
          </source>
          <focus>
            <reference value="Encounter/7790f964-88d3-4652-bbc8-81d2f3d035f8"/> <!--Focus of the message-->
          </focus>
        </MessageHeader>
      </resource>
    </entry>
  </Bundle> 
</creator>
```



``` xml
<creator>
  <!--MedComHospitalNotificationMessage = Bundle begins here-->
  <Bundle xmlns="http://hl7.org/fhir">
    <id value="15e5b880-c087-4055-b9ec-99108695f81d"/>
    <meta>
      <profile
              value="http://medcomfhir.dk/fhir/hospitalnotification/StructureDefinition/medcom-hospitalNotification-message"/>
    </meta>
    <type value="message"/> <!--This is a message-->
    <timestamp value="2020-10-15T13:44:14Z"/> <!--When the message was created-->
    <!--MedComHospitalNotificationMessageHeader = MessageHeader begins here.-->
    <entry>
      <fullUrl value="MessageHeader/29b4818e-02de-4cc4-b418-d20cbc7b5404"/>
      <resource>
        <MessageHeader>
          <id value="29b4818e-02de-4cc4-b418-d20cbc7b5404"/>
          <meta>
            <profile
                    value="http://medcomfhir.dk/fhir/hospitalnotification/StructureDefinition/medcom-hospitalNotification-messageHeader"/>
          </meta>
          <text> 
            <!--Narrative text will be here-->
          </text>
          <extension
                    url="http://medcomfhir.dk/fhir/hospitalnotification/StructureDefinition/medcom-messaging-reportOfAdmissionExtension">
            <valueBoolean value="false"/> <!--No report of admission (Danish: indlæggelsesrapport) shall be returned-->
          </extension>
          <eventCoding>
            <system
                    value="http://medcomfhir.dk/fhir/messaging/CodeSystem/medcom-messaging-eventCodes"/>
            <code value="hospital-notification-message"/> <!--Type of message-->
          </eventCoding>
          <destination>
            <extension
                      url="http://medcomfhir.dk/fhir/messaging/StructureDefinition/medcom-messaging-destinationUseExtension">
              <valueCoding>
                <system
                        value="http://medcomfhir.dk/fhir/messaging/CodeSystem/medcom-messaging-destinationUse"/>
                <code value="primary"/>
              </valueCoding>
            </extension>
            <endpoint value="http://medcom.dk/unknown"/>
            <receiver>
              <reference value="Organization/74cdf292-abf3-4f5f-80ea-60a48013ff6d"/> <!--Receiver organization-->
            </receiver>
          </destination>
          <sender>
            <reference value="Organization/d7056980-a8b2-42aa-8a0e-c1fc85d1f40d"/> <!--Sender organization-->
          </sender>
          <source>
            <endpoint value="http://medcom.dk/unknown"/>
          </source>
          <focus>
            <reference value="Encounter/7790f964-88d3-4652-bbc8-81d2f3d035f8"/> <!--Focus of the message-->
          </focus>
        </MessageHeader>
      </resource>
    </entry>
  </Bundle> 
</creator>
```



