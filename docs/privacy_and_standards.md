# Healthcare Privacy, Terminology, and Standards

## 1. Purpose

This document summarizes healthcare privacy concepts, interoperability
standards, terminology systems, coding systems, and electronic healthcare
transactions relevant to MedAuth-Agentic.

The project is an educational prototype for reviewing synthetic prior
authorization cases and identifying missing evidence. It does not make
autonomous clinical decisions or guarantee payer approval.

## 2. Privacy Fundamentals

### HIPAA

HIPAA stands for Health Insurance Portability and Accountability Act.
It is a United States federal law that includes requirements for protecting
certain health information.

The HIPAA Privacy, Security, and Breach Notification Rules apply to
covered entities and business associates in defined circumstances.

Learning about HIPAA does not establish that an application is compliant.

### PHI and ePHI

- PHI: Protected Health Information. Under HIPAA, this generally refers to
  individually identifiable health information protected by the applicable
  rules.
- ePHI: Electronic Protected Health Information. This is PHI created,
  received, maintained, or transmitted electronically and subject to the
  HIPAA Security Rule.

Examples of potentially identifying health information include patient
names, dates associated with care, contact details, medical record numbers,
and combinations of clinical details that could identify someone.

### De-identification

Removing a patient's name or replacing it with an identifier does not
automatically make a dataset de-identified.

Dates, locations, rare conditions, and combinations of details may still
permit identification.

The US Department of Health and Human Services describes two HIPAA
de-identification methods:

- Safe Harbor
- Expert Determination

De-identification and anonymization are not interchangeable terms in every
legal or technical context.

### Privacy risks in an LLM workflow

LLM means Large Language Model.

| Risk | Example mitigation |
|---|---|
| Sensitive data sent to an external model | Use synthetic data during development; minimize data sent to models |
| Sensitive information retained in logs | Avoid logging unnecessary clinical text; restrict access and retention |
| Unauthorized retrieval | Apply access controls and isolate case-specific data |
| Excessive data collection | Collect only the information required for the task |
| Inappropriate model or vendor data handling | Review service terms, retention settings, and applicable agreements |
| Sensitive information in prompts or outputs | Validate inputs and outputs; avoid unnecessary identifiers |

Redaction alone does not establish regulatory compliance. Privacy and security
require appropriate technical, organizational, and legal safeguards.

## 3. Healthcare Interoperability

Interoperability is the ability of different systems to exchange information
and use that information meaningfully.

Healthcare systems need interoperability because providers, laboratories,
hospitals, insurers, and other organizations may use different software and
data formats.

Standards reduce ambiguity and support consistent data exchange.

### HL7 v2

HL7 stands for Health Level Seven. HL7 is an organization that develops
healthcare interoperability standards; its name is also commonly used when
referring to its standards.

HL7 Version 2 (HL7 v2) is a messaging standard used to exchange healthcare
events and information between systems.

Examples include patient admission, discharge, transfer, and clinical
observations.

### FHIR

FHIR stands for Fast Healthcare Interoperability Resources.

FHIR represents healthcare information using defined resources that systems
can exchange through supported methods, including web APIs.

Examples relevant to MedAuth-Agentic include:

- Patient: patient-related information
- Encounter: a healthcare interaction
- Condition: a condition or diagnosis
- Observation: a clinical observation or measurement
- MedicationRequest: a medication order or request
- ServiceRequest: a request for a healthcare service
- DocumentReference: metadata about a document

FHIR can carry coded information from appropriate terminology and coding
systems. FHIR does not replace those systems and does not itself decide
whether a prior authorization should be approved.

## 4. Terminology and Coding Systems

| System | Full form | Main purpose |
|---|---|---|
| SNOMED CT | Systematized Nomenclature of Medicine Clinical Terms | Represents clinical concepts such as findings, conditions, and procedures |
| LOINC | Logical Observation Identifiers Names and Codes | Identifies laboratory tests, clinical measurements, observations, and some documents |
| ICD-10-CM | International Classification of Diseases, Tenth Revision, Clinical Modification | Classifies diagnoses and health conditions in the United States |
| CPT | Current Procedural Terminology | Describes medical procedures and professional services |
| HCPCS | Healthcare Common Procedure Coding System | Identifies healthcare procedures, services, supplies, and equipment; Level II covers many items and services not represented by CPT |

These systems serve different purposes. The appropriate code depends on the
documented information and applicable coding rules. Codes must be verified;
they must not be invented from incomplete clinical descriptions.

## 5. X12 Healthcare Transactions

EDI means Electronic Data Interchange: the structured electronic exchange
of business documents between organizations.

ASC X12 refers to Accredited Standards Committee X12, which develops
electronic data interchange standards.

| Transaction | Business purpose |
|---|---|
| 270 | Healthcare eligibility and benefit inquiry |
| 271 | Healthcare eligibility and benefit response |
| 278 | Healthcare services review, including prior authorization and referrals |
| 837 | Healthcare claim submission |
| 835 | Healthcare claim payment and remittance advice |

A simplified workflow may include an eligibility inquiry and response,
a service review when required, claim submission, and payment or remittance
information.

Actual workflows vary. These transactions do not necessarily occur in
one fixed sequence.

A prior authorization does not guarantee payment of a later claim. The claim
is assessed separately under the applicable coverage, coding, documentation,
and payment rules.

## 6. Application to MedAuth-Agentic

The project will use synthetic prior authorization cases and supporting
documents.

The agent should:

1. Identify the requested healthcare service.
2. Identify the evidence required by the fictional policy.
3. Compare available evidence with each requirement.
4. Preserve source references for findings.
5. Flag missing information and insufficient evidence.
6. Route uncertain or consequential decisions for human review.
7. Avoid inventing diagnoses, codes, policy requirements, or clinical facts.

Missing documentation must not automatically be interpreted as proof that
a clinical criterion is unmet.

The prototype is an evidence-review aid, not a payer adjudication system.
It does not submit real X12 transactions or make binding coverage decisions.

## 7. Key Takeaways

- Privacy safeguards must be considered throughout the LLM workflow.
- Removing names alone does not guarantee de-identification.
- HL7 v2 and FHIR support healthcare interoperability in different ways.
- SNOMED CT, LOINC, ICD-10-CM, CPT, and HCPCS have distinct purposes.
- X12 transactions support standardized healthcare business exchanges.
- A prior authorization and a later claim are separate processes.
- The project uses synthetic data and does not claim regulatory compliance
  or production readiness.

## 8. Official References

- HHS HIPAA overview:
  https://www.hhs.gov/hipaa/

- HHS guidance on de-identification:
  https://www.hhs.gov/hipaa/for-professionals/special-topics/de-identification/index.html

- HHS guidance on cloud computing and ePHI:
  https://www.hhs.gov/hipaa/for-professionals/special-topics/health-information-technology/cloud-computing/index.html

- HL7 FHIR Release 4:
  https://hl7.org/fhir/R4/

- HHS adopted standards and operating rules:
  https://www.hhs.gov/guidance/document/adopted-standards-and-operating-rules

- CMS Interoperability and Prior Authorization Final Rule:
  https://www.cms.gov/newsroom/fact-sheets/cms-interoperability-prior-authorization-final-rule-cms-0057-f
