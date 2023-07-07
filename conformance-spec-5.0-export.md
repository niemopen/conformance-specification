# National Information Exchange Model Conformance Specification

- Version 5.0
- March 19, 2021
- NIEM Technical Architecture Committee (NTAC)

# Abstract

This document specifies general conformance guidance, principles, and rules for the National Information Exchange Model (NIEM) version 5.0.

# Status

This document is a draft of the specification for general NIEM conformance. It represents the collaborative work of the NIEM Business Architecture Committee (NBAC) and the NIEM Technical Architecture Committee (NTAC).

This document is a product of the NIEM Management Office (NMO).

Updates, revisions, and errata for this specification are posted to <a class="url" target="_blank" href="https://github.com/NIEM/NIEM-Conformance-Spec">https://github.com/NIEM/NIEM-Conformance-Spec</a>. Please submit comments on this specification as issues at <a class="url" target="_blank" href="https://github.com/NIEM/NIEM-Conformance-Spec/issues">https://github.com/NIEM/NIEM-Conformance-Spec/issues</a>.

# Table of contents

- [1. Introduction](#introduction)
- [2. Purpose](#purpose)
- [3. Artifacts may conform with NIEM](#artifacts-may-conform-with-niem)

	- [3.1. Conformant instance document](#conformant-instance-document)
	- [3.2. Conformant schema document set](#conformant-schema-document-set)
	- [3.3. Conformant message specifications (IEPD)](#conformant-message-specifications-(iepd))

- [4. Implementations cannot conform with NIEM](#implementations-cannot-conform-with-niem)

	- [4.1. NIEM-based Information Exchange](#niem-based-information-exchange)
	- [4.2. NIEM-aware Tools and Systems](#niem-aware-tools-and-systems)

- [5. NIEM components must preserve semantic integrity](#niem-components-must-preserve-semantic-integrity)
- [6. Producers of artifacts should ensure NIEM conformance](#producers-of-artifacts-should-ensure-niem-conformance)

	- [6.1. Reference schema document sets](#reference-schema-document-sets)
	- [6.2. Message specifications](#message-specifications)

- [Appendix A. References](#appendix-a-references)

# Introduction

This document specifies general conformance guidance, principles, and rules for the National Information Exchange Model (NIEM) version 5.0.

# Purpose

This is a high-level document that defines NIEM conformance including how it applies and to what it does and does not apply. The intended audience includes NIEM developers and users.

This specification includes other NIEM specifications by reference. Non-normative information, including tools and implementation guidance are also published at <a class="url" target="_blank" href="https://niem.github.io">https://niem.github.io</a>.

# Artifacts may conform with NIEM

Conformance to NIEM is defined in terms of artifacts. NIEM defines various conformance targets as the classes of artifacts to which sets of normative rules apply, as defined in the [NIEM Conformance Targets Attribute Specification 3.0](#Appendix-A-References)     [Section 3.1, _Conformance Target Defined_](https://reference.niem.gov/niem/specification/conformance-targets-attribute/3.0/#section_3.1).

NIEM conformance targets include:

- Conformant instance document
- Conformant schema document set
- Conformant message specification (also known as an IEPD)

Documents may use the attribute defined in the [NIEM Conformance Targets Attribute Specification 3.0](#Appendix-A-References)     [Section 1.3, _Description of the Conformance Targets Attribute_](https://reference.niem.gov/niem/specification/conformance-targets-attribute/3.0/#section_1.3) to claim that the document conforms to one or more NIEM conformance targets.

## Conformant instance document

A conformant instance document is an instance of a conformant schema document set that conforms to all applicable rules in the [NIEM NDR 5.0](#Appendix-A-References).

## Conformant schema document set

A conformant schema document set is a collection of schema documents that conform to all applicable rules in the [NIEM NDR 5.0](#Appendix-A-References).

A schema document that copies, maps to, or uses the data component names of NIEM document schemas or the data components they contain without importing corresponding NIEM target namespaces does NOT conform to NIEM. Conforming to NIEM requires that a schema document reuse NIEM by importing through xs:import the target namespaces of NIEM reference schema documents or schema subset documents of NIEM reference schema documents.

## Conformant message specifications (IEPD)

A conformant message specification is a package of files that conforms to the rules specified in the [NIEM IEPD Specification 5.0](#Appendix-A-References).

# Implementations cannot conform with NIEM

NIEM conformance is NOT defined in terms of implementations, databases, systems, or tools. 

In describing an implementation that employs NIEM, an author should be as descriptive as is necessary to convey clear understanding of how NIEM is used and which conformance targets are supported.

## NIEM-based Information Exchange

An implementation that sends and receives NIEM-conformant instance documents on a transmission medium is considered a NIEM-based information exchange. An implementation may apply encryption, compression, encoding (e.g. Efficient XML Interchange (EXI) encoding [Efficient XML Interchange (EXI)](#Appendix-A-References)), or other security and/or efficiency techniques to an NIEM instance document as required; and it will still represent a NIEM information exchange. NIEM is a payload layer and, as such, a NIEM-conformant instance document may be contained within a standard envelope (such as SOAP, LEXS, etc.).

## NIEM-aware Tools and Systems

A tool or system, such as a database, may have capabilities designed to support:

- Creation of conformant schema document sets that may include extensions to the NIEM,
- Development of conformant message specifications,
- Implementation of conformant message specifications, including the sending and receiving of conformant instance documents, or
- Testing artifacts for conformance with an NIEM conformance target

Such tools and systems may be considered NIEM-aware or NIEM-supporting.

A registry of NIEM-aware tools is available at [NIEM Tools Catalog](#Appendix-A-References).

# NIEM components must preserve semantic integrity

If an existing NIEM component matches the business semantics required by the message specification, then that component is used by the message specification, either directly or as the basis for derived components. That is, the message specification does not unnecessarily duplicate NIEM components.

Each NIEM schema component used by the message specification, either directly or as the basis for derived components, is used in a manner consistent with the component's structural definition and business semantics. That is, the message specification preserves semantic and structural consistency.

# Producers of artifacts should ensure NIEM conformance

## Reference schema document sets

Reference schema document sets (i.e., NIEM releases, domain updates, and core updates) are subject to rigorous quality and conformance testing by the NIEM MO to ensure they conform to the [NIEM NDR 5.0](#Appendix-A-References).

## Message specifications

Message specifications, message instances, and schema document sets other than those listed above are not under the control of the NIEM MO and no formal certification process exists. Therefore, it is important for NIEM users and developers to understand and make a concerted effort to ensure message specifications they produce conform to the [NIEM IEPD Specification 5.0](#Appendix-A-References).

# Appendix A. References

<p class="hang">[NIEM Conformance Targets Attribute Specification 3.0]: "Attribute Specification, Version 3.0," NIEM Technical Architecture Committee (NTAC). Available from <a class="url" target="_blank" href="https://reference.niem.gov/niem/specification/conformance-targets-attribute/3.0/">https://reference.niem.gov/niem/specification/conformance-targets-attribute/3.0/</a>.

<p class="hang">[NIEM NDR 5.0]: "NIEM Naming and Design Rules, Version 5.0," NIEM Technical Architecture Committee (NTAC). Available from <a class="url" target="_blank" href="https://reference.niem.gov/niem/specification/naming-and-design-rules/5.0/">https://reference.niem.gov/niem/specification/naming-and-design-rules/5.0/</a>.

<p class="hang">[NIEM IEPD Specification 5.0]: "NIEM Information Exchange Package Documentation (IEPD) Specification, Version 5.0," NIEM Technical Architecture Committee (NTAC). Available from <a class="url" target="_blank" href="https://reference.niem.gov/niem/specification/model-package-description/5.0/">https://reference.niem.gov/niem/specification/model-package-description/5.0/</a>.

<p class="hang">[NIEM Tools Catalog]: "NIEM Tools Catalog," NIEM Management Office (MO). Available from <a class="url" target="_blank" href="https://www.niem.gov/tools-catalog">https://www.niem.gov/tools-catalog</a>.

<p class="hang">[Efficient XML Interchange (EXI)]: "Efficient XML Interchange (EXI) Format 1.0 (Second Edition)," W3C. Available from <a class="url" target="_blank" href="https://www.w3.org/TR/exi/">https://www.w3.org/TR/exi/</a>.

