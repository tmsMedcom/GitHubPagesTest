# Governance for MedCom FHIR®© Messaging

**Table of contents**
* [1 Introduction to Governance for MedCom FHIR Messaging](#1-introduction-to-governance-for-medcom-fhir-messaging)
* [2 Terms and abbreviations](#2-terms-and-abbreviations)
  + [2.1 Special terms used in Governance for MedCom FHIR Messaging](#21-special-terms-used-in-governance-for-medcom-fhir-messaging)
* [3 Message exchange](#3-message-exchange)
  + [3.1 Governance for Reliable Messaging in general](#31-governance-for-reliable-messaging-in-general)
  + [3.2 Governance for Network Layer](#32-governance-for-network-layer)
  + [3.3 Governance for MedCom FHIR Message Exchange](#33-governance-for-medcom-fhir-message-exchange)
* [4 MedCom FHIR Messages](#4-medcom-fhir-messages)
  + [4.1 Governance for MedCom FHIR Messages](#41-governance-for-medcom-fhir-messages)
  + [4.2 Governance for displaying MedCom FHIR Messages](#42-governance-for-displaying-medcom-fhir-messages)
* [5 Terminology](#5-terminology)
  + [5.1 Governance for MedCom FHIR Terminology](#51-governance-for-medcom-fhir-terminology)
  + [5.2 Governance for MedCom FHIR Terminology Server](#52-governance-for-medcom-fhir-terminology-server)
* [6 Governance for concrete MedCom FHIR Standards](#6-governance-for-concrete-medcom-fhir-standards)
<br>

## 1 Introduction to Governance for MedCom FHIR Messaging

On this page, you can find information about how MedCom has profiled the <a href="http://hl7.org/fhir/R4/messaging.html" target="_blank">HL7 FHIR Messaging Framework</a> to work in a Danish context.
Governance for MedCom HL7 FHIR Messaging describes the basic ruleset of how MedCom Messages must be exchanged in the Danish Healthcare Messaging Network.
The Danish ruleset is based on:

* the ruleset for the Danish VANS Network
* the general <a href="http://hl7.org/fhir/R4/messaging.html" target="_blank">HL7 FHIR Communication Rules for FHIR Messaging</a>
* the Danish profiling of FHIR messaging.

<br>

These MedCom FHIR Messaging Governance rules are intended to clarify the use of MedCom’s FHIR messages for the health and social area. Formerly these kinds of rules for other MedCom Messaging paradigms were known as ”Syntax & Communication Rules”.

It is the intention that the MedCom FHIR Messaging Governance rules together with MedCom’s FHIR standards for the individual messages form the full and sufficient basis for implementing MedCom’s healthcare messages. Thus, the governance rules must be able to function as “a chief judge”, where there is doubt about the practical application of MedCom’s FHIR messages.

In the following, we follow a top-down approach by initially addressing shipping over the Network Layer and its ruleset, followed by the logistics for MedCom FHIR Messaging and lastly the basic ruleset of how to compose a MedCom FHIR message. Initially, is a brief introduction to the use of terms presented. 

<!-- The “Governance for MedCom FHIR Messaging” ensures uniform use of MedCom’s FHIR messages to the health and social domains in Denmark. -->

<!-- 
Here, you will find how MedCom has profiled the HL7 FHIR Messaging Framework to work in a Danish context. -->

<!-- Governance for MedCom HL7 FHIR Messaging is the basic ruleset of how MedCom Messages must be exchanged in the Danish Healthcare Messaging Network.

The Danish ruleset is based on:

* the ruleset for the Danish VANS Network, the Danish profiling of FHIR messaging 
*

In the following we follow a top-down approach by addressing shipping over the Network Layer and its ruleset first, then the logistics for MedCom FHIR Messaging and last cover the basic ruleset of how to compose a MedCom FHIR message. -->

<!-- [Introduction details (Danish)](/assets/documents/1-Introduction.md)-->

<!-- [Generelle tekniske use cases](Generelle-tekniske-use-cases-v1.0.0-b2.md) -->


## 2 Terms and abbreviations

[Click here to get an overview of the terms and abbreviations used in to describe the Governance.](/assets/documents/011_Governance_Terms.md)

### 2.1 Special terms used in Governance for MedCom FHIR Messaging

MedCom adopts the normative words defined in IETF Best Current Practice 14: Key words for use in RFCs to Indicate Requirement Levels (BCP-14) (currently RFC 2119 and RFC 8174), certain words indicate whether a specific content of the Technical Framework is normative: either required (e.g., “must”, “required”, “shall”) or optional (e.g., “may”, “recommended”). Informative content does not contain these key words.

<a href="https://www.rfc-editor.org/info/rfc2119" target="_blank">RFC 2119</a> specifies common key words that may be used in protocol specifications, where <a href="https://www.rfc-editor.org/info/rfc8174" target="_blank">RFC 8174</a> aims to reduce the ambiguity by clarifying that only UPPERCASE usage of the key words have the defined special meanings.

This specification uses the conformance verbs SHALL, SHOULD, and MAY as defined in RFC 2119. Unlike RFC 2119, however, this specification allows that different applications might not be able to interoperate because of how they use optional features. In particular:

* **SHALL**: (or “REQUIRED” or “MUST”) an absolute requirement for all implementations
* **SHALL NOT**: (or "MUST NOT") an absolute prohibition against inclusion for all implementations
* **SHOULD/SHOULD NOT**: (or “RECOMMENDED”/“NOT RECOMMENDED”) A best practice or recommendation to be considered by implementers within the context of their particular implementation; there may be valid reasons to ignore an item, but the full implications must be understood and carefully weighed before choosing a different course
* **MAY**: (or "OPTIONAL") This is truly optional language for an implementation; can be included or omitted as the implementer decides with no implications

<br>

This convention is in compliance with HL7 FHIR use of the terms, which is descibed by <a href="http://www.hl7.org/fhir/conformance-rules.html#conflang" target="_blank">HL7 FHIR under conformance language</a>.


## 3 Message exchange

MedCom FHIR Messaging is based on Asynchronous Messaging.

In Asynchronous messaging, a Sending EcoSystem dispatches an unsolicited message to a Receiving EcoSystem possibly through several intermediate hubs. Besides sending a possibly requested acknowledgement immediately as a response, the Receiving EcoSystem responds to the Sending EcoSystem separately. The Receiving EcoSystem may respond more than once to any given message.

When exchanging a MedCom FHIR message, it is allowed to send in a FHIR+JSON og FHIR+XML format, which is in alignment with HL7 FHIR. 

### 3.1 Governance for Reliable Messaging in general

Governance for Reliable Messaging in general lays the grounds for Governance for Reliable Messaging using VANSenvelope and Governance for Reliable Messaging using FHIR. The generic ruleset defines the other two rulesets.

[Click here to go to Reliable Messaging in general.](/assets/documents/020_Governance-for-Reliable-Messaging-in-general.md)

### 3.2 Governance for Network Layer

Governance for Network Layer covers rulesets for VANSEnvelope and Reliable Messaging using VANSenvelope.

[Click here to go to Governance for Network Layer.](/assets/documents/030_Governance-for-Network-Layer.md)

### 3.3 Governance for MedCom FHIR Message Exchange

Governance for MedCom FHIR Messaging covers Reliable Messaging using MedCom FHIR Messaging, sending and receiving scenarios, and rulesets for FHIR Messaging and FHIR Messaging Acnowledgement.

[Click here to go to Governance for MedCom FHIR Messaging.](/assets/documents/040_Governance4FHIR-Messaging.md)

## 4 MedCom FHIR Messages

An implementer of a MedCom FHIR Message Standard **SHALL** be compliant with all parts of the documentation laid out for the MedCom FHIR Message Standard.

You can find a description here:<a href="https://medcomdk.github.io/dk-medcom-messaging/assets/documents/Intro-Technical-Spec-ENG.html#21-medcommessagingmessage-bundle" target="_blank"> Click here to read the documentation for the MedCom FHIR Message Standard</a>


### 4.1 Governance for MedCom FHIR Messages

Governance for MedCom FHIR Messages covers the basic ruleset for a MedCom FHIR Message, MedComMessagingMessage and its content, MedComMessagingMessageHeader, MedComMessagingOrganization and MedComMessagingProvenance

[Click here to go to Governance for MedCom FHIR Messages.](/assets/documents/050_Governance-for-MedCom-FHIR-Messages.md)

### 4.2 Governance for displaying MedCom FHIR Messages

Governance for displaying MedCom FHIR Messaging covers the basic demands for a sending system to be able to display before sending and the basic demands for a receiving system to be able to display after having received a MedComMessagingMessage.

[Click here to go to Governance for displaying MedCom FHIR Messages](/assets/documents/060_Governance-for-displaying-MedCom-FHIR-Messages.md)

## 5 Terminology 

### 5.1 Governance for MedCom FHIR Terminology

Governance for MedCom FHIR Terminology covers Codesystems, Valuesets and ConceptMaps, which are published through our MedCom FHIR Terminology IG and hosted on a MedCom FHIR Terminology Server.

[Click here to go to Governance for Terminology.](/assets/documents/070_Governance-for-Terminology.md)

### 5.2 Governance for MedCom FHIR Terminology Server

Governance for the MedCom FHIR Terminology Server will appear here when published.

## 6 Governance for concrete MedCom FHIR Standards

Each MedCom FHIR Message will potentially add some specific Governance Rules to the mix of overall Governance Rules. These are handled on a separate page, to which the specific standard also will link to.

[Click here to go to Governance for concrete MedCom FHIR Message Standards.](/assets/documents/090_Governance-for-concrete-standards.md)
