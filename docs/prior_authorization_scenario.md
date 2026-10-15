# Synthetic Prior-Authorization Scenario

> Educational example only. All patient details and policy requirements are fictional.

## Case ID

SYN-AUTH-001

## Participants

- Patient: Ravi (fictional)
- Provider: City Clinic (fictional)
- Payer: Example Health Plan (fictional)

## Scenario

Ravi visits City Clinic with knee discomfort. The clinician documents the reported symptoms and requests an MRI.

For this exercise, assume the Example Health Plan requires prior authorization for the requested service.

The clinic submits a prior-authorization request with a clinical summary and the requested service details.

## Fictional Policy Requirements

For this exercise, the mock payer policy requires:

1. A documented diagnosis or clinical reason.
2. Supporting clinical documentation.
3. Identification of the requested service.
4. Any additional information specified by the mock policy.

These requirements are invented for software-testing practice. They are not real clinical guidelines or an actual insurer's coverage policy.

## Information Available

- A clinical summary is present.
- The requested service is identified.
- The required supporting clinical documentation is missing from the submitted package.

## Expected Prototype Behavior

The MedAuth-Agentic prototype should:

1. Identify the relevant fictional policy requirements.
2. Compare the available information with each requirement.
3. Preserve the source of each piece of evidence.
4. Flag the missing supporting documentation.
5. Report insufficient evidence where appropriate.
6. Prepare a draft for human review.
7. Avoid inventing clinical facts or making a final autonomous authorization decision.

## Important Distinction

A prior-authorization request is not the same as a claim submitted for payment processing. Even when authorization is granted, final claim payment is not guaranteed.

## Diagnosis and Service Coding Fields

These fields are included for prototype readiness. Their presence does
not mean every payer or prior-authorization request requires both codes.

| Field | Value |
|---|---|
| Documented clinical concern | Knee discomfort |
| Diagnosis code system | ICD-10-CM — International Classification of Diseases, Tenth Revision, Clinical Modification |
| Diagnosis code | UNASSIGNED — verify against the documented diagnosis |
| Requested service | MRI — Magnetic Resonance Imaging of the knee |
| Service code system | CPT — Current Procedural Terminology, or HCPCS — Healthcare Common Procedure Coding System, as applicable |
| Service code | UNASSIGNED — verify the exact requested procedure |

### Coding Safety Rules

- Do not infer a diagnosis code from knee discomfort alone.
- Do not assign a procedure code without sufficient service details.
- Verify codes against appropriate authoritative coding references.
- Record the code system and code separately.
- Follow the applicable fictional payer policy when deciding whether a code is required.
- Flag missing or uncertain information for human review.
