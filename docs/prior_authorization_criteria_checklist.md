# Prior-Authorization Criteria Checklist

> Educational checklist for the synthetic MedAuth-Agentic scenario. Not a real clinical policy.

## Case

- Case ID: SYN-AUTH-001
- Provider: City Clinic (fictional)
- Payer: Example Health Plan (fictional)
- Requested service: MRI

## Criteria Assessment

| Criterion | Evidence available | Status |
|---|---|---|
| Diagnosis or clinical reason documented | Clinical summary is present; verify its contents | INSUFFICIENT_EVIDENCE |
| Supporting clinical documentation supplied | Required documentation is missing | INSUFFICIENT_EVIDENCE |
| Requested service identified | MRI is identified in the request | MET |
| Additional mock-policy requirements checked | Must be checked against the complete fictional policy | INSUFFICIENT_EVIDENCE |

## Status Definitions

- MET: The available evidence supports the criterion.
- NOT_MET: Available evidence indicates the criterion is not satisfied.
- INSUFFICIENT_EVIDENCE: There is not enough reliable information to assess the criterion.

Missing documentation does not automatically mean that a clinical criterion is NOT_MET.

## Missing Information

- The supporting clinical documentation required by the fictional policy.
- Confirmation that the clinical summary contains enough information to support the diagnosis or clinical reason.
- Confirmation that all additional mock-policy requirements have been checked.

## Draft Workflow Outcome

Suggested status: NEEDS_MORE_INFORMATION

Next action: Route the case for human review and identify the missing documentation.

The suggested status is a workflow outcome for this educational example, not a real insurance decision.

## Safety Rules

- Do not invent missing clinical information.
- Preserve policy document identifiers and evidence references when available.
- Distinguish evidence from interpretation.
- Use INSUFFICIENT_EVIDENCE when the available information is inadequate.
- Keep a human reviewer responsible for the final decision.

## Diagnosis and Service Coding Checks

These are additional prototype checks. Whether a code is mandatory
depends on the applicable payer policy and requested service.

| Criterion | Current evidence | Status |
|---|---|---|
| Diagnosis code identified and supported, when required | Knee discomfort is documented, but a specific diagnosis code has not been verified | INSUFFICIENT_EVIDENCE |
| Requested service code identified and validated, when required | Knee MRI is identified, but the exact procedure code has not been verified | INSUFFICIENT_EVIDENCE |
| Code system recorded correctly | Diagnosis uses ICD-10-CM; service coding may use CPT or HCPCS, as applicable | NEEDS_VALIDATION |

### Coding Review Rules

- ICD-10-CM means International Classification of Diseases, Tenth Revision, Clinical Modification.
- CPT means Current Procedural Terminology.
- HCPCS means Healthcare Common Procedure Coding System.
- Do not invent or guess codes.
- Do not treat an unassigned code as proof that the clinical criterion is not met.
- Confirm the applicable coding system and payer requirements before implementation.
- Send unresolved coding questions to a human reviewer.
