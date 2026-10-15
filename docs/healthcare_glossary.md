# Healthcare Glossary — MedAuth-Agentic

> Educational project. All examples are fictional. Do not use real patient information.

## 1. EMR — Electronic Medical Record

A digital medical chart commonly used within a particular medical practice or healthcare organization.

Example: A clinic records a patient's symptoms, examination findings, diagnosis, and treatment plan in its EMR.

## 2. EHR — Electronic Health Record

An electronic health record designed to support a broader view of a patient's health information across care settings. Information sharing depends on interoperability and the systems, permissions, and rules involved.

Example: A hospital may obtain relevant records from another clinic when the systems can exchange the information appropriately.

## 3. Provider

A person or organization that delivers healthcare, such as a doctor, clinic, or hospital.

Example: A hospital requests prior authorization for a service its clinician has ordered.

## 4. Payer

An organization responsible for paying for or administering covered healthcare benefits under an insurance arrangement.

Example: A health insurer evaluates a prior-authorization request under the applicable plan rules.

Note: A third-party administrator may administer plan operations without necessarily bearing the insurance risk.

## 5. Patient and Member

- Patient: A person receiving healthcare.
- Member: A person enrolled in a health plan.

One person may be both a patient and a health-plan member.

## 6. Health Plan

The coverage and benefits arrangement that describes which services may be covered and under what conditions.

## 7. Third-Party Administrator (TPA)

An organization that performs administrative functions for a health plan, such as claims processing. Its exact responsibilities depend on the arrangement.

## 8. Encounter

A healthcare interaction, such as an office visit, consultation, or hospital visit.

## 9. Diagnosis

A description or identification of a health condition documented by a healthcare professional.

## 10. Procedure or Service

A healthcare service or intervention, such as an imaging study or laboratory test.

## 11. Clinical Note

Narrative documentation of a healthcare interaction, including relevant symptoms, findings, and plans.

## 12. Prior Authorization

A process in which a payer requires a request and supporting information to be reviewed before a particular service is provided or covered under specified circumstances. Requirements vary by plan and service.

Prior authorization is not a guarantee of final claim payment.

## 13. Structured Data

Information organized into defined fields, making it easier to validate, filter, and query.

Fictional example:

- Patient reference: SYN-P001
- Encounter type: Outpatient
- Requested service: MRI

## 14. Unstructured Data

Information primarily expressed as free text or documents.

Fictional example:

"The patient reports knee discomfort when walking upstairs."

## 15. FHIR

Fast Healthcare Interoperability Resources (FHIR) is a standard for representing and exchanging healthcare information using defined resources and interfaces.

In this project, we will use FHIR R4 examples with synthetic data.

FHIR can support data exchange; it does not itself approve or deny prior authorization.

## 16. RAG

Retrieval-Augmented Generation (RAG) retrieves relevant source material and provides it as context for a language model to help produce a grounded response.

In MedAuth-Agentic, RAG will retrieve relevant passages from fictional payer-policy documents. The prototype must preserve source references and report when evidence is insufficient.

## 17. Human Review

A qualified human reviews the evidence and draft recommendation before a final decision-like action. The prototype does not autonomously make the final insurance decision.

## Simplified Healthcare Data Flow

1. A patient visits a provider.
2. The provider documents the encounter and relevant clinical information.
3. When required, the provider submits a prior-authorization request and supporting documentation to the payer.
4. The payer evaluates the request under the applicable plan rules.
5. The outcome or a request for more information is communicated through the applicable workflow.
6. In MedAuth-Agentic, the prototype helps organize policy evidence, identify missing information, and prepare a draft for human review.

## Project Boundaries

- Use synthetic data only.
- Do not include real patient records or confidential employer information.
- Do not treat retrieved text or model output as a substitute for qualified review.
- Do not claim the educational prototype is production-ready or HIPAA-compliant.
