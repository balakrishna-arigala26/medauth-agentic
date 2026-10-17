# MedAuth-Agentic 🏥🤖

**An AI-assisted healthcare prior-authorization evidence-review copilot — a learning project in development.**

MedAuth-Agentic explores how healthcare domain knowledge, structured healthcare data, information retrieval, and agentic workflows can support the review of prior-authorization documentation.

The project is being developed incrementally using **synthetic healthcare data only**.

> **Current status:** Phase 1 healthcare foundations and documentation are complete. Phase 2, focused on FHIR resources and APIs, is next. Application features listed below are planned unless explicitly marked as implemented.

---

## 🎯 Project Objectives

- Represent healthcare information using structured FHIR R4 resources.
- Identify evidence requirements from synthetic prior-authorization policies.
- Compare available case documentation against individual policy criteria.
- Preserve source references so findings can be traced to supporting evidence.
- Flag missing information and use `INSUFFICIENT_EVIDENCE` when available documentation does not support a conclusion.
- Design human-review checkpoints for consequential determinations.
- Evaluate retrieval quality, correctness, and safe handling of uncertainty.

---

## 🧰 Planned Technology Stack

| Technology | Intended purpose |
|---|---|
| **Python** | Core application development and type hints |
| **FHIR R4** | Structured healthcare data representation and exchange |
| **`fhir.resources`** | Python models for supported FHIR resources |
| **Pydantic v2** | Input validation and data normalization |
| **SQLite / SQLAlchemy** | Local case persistence and metadata-only audit logging design |
| **Microsoft Presidio** | Demonstrate sensitive-information detection and redaction on synthetic text |
| **Hybrid RAG** | Combine `rank-bm25` keyword search with `ChromaDB` vector retrieval |
| **LangGraph** | Orchestrate workflow steps and human-review checkpoints |
| **FastAPI** | Expose application functionality through REST API endpoints |
| **Pytest** | Automated unit, retrieval, and API testing |

**Status note:** This is the intended stack. A technology or feature should be considered implemented only after it has been added, validated, and tested in the repository.

---

## 🏗️ Planned Core Workflow

1. **Load case:** Load a synthetic prior-authorization request and associated healthcare resources.
2. **Validate and normalize:** Validate inputs and normalize case data.
3. **Privacy demonstration:** Run synthetic text through a sensitive-information detection and redaction demonstration.
4. **Hybrid retrieval:** Retrieve relevant sections from synthetic payer-policy documents using keyword search and dense-vector retrieval.
5. **Evaluate criteria:** Compare case documentation against policy requirements.
6. **Structured output:** Classify each criterion as `MET`, `NOT_MET`, or `INSUFFICIENT_EVIDENCE`, with source references where available.
7. **Human review:** Design a workflow checkpoint for human review of uncertain or consequential findings.
8. **Audit and persistence:** Store case state and appropriately minimized metadata, subject to implementation and testing.

> **Safety principles:** The system is designed not to invent clinical facts, coding information, policy requirements, or supporting evidence. These principles must be verified through implementation and testing; they are not a guarantee of error-free behavior.

---

## 📚 Learning Roadmap and Status

| Phase | Focus area | Status |
|---|---|---|
| **Phase 1** | Healthcare domain, privacy, terminology, and standards | **Completed — learning and documentation** |
| **Phase 2** | FHIR resources, APIs, validation, normalization, and SQL | **Next** |
| **Phase 3** | Retrieval-Augmented Generation (RAG) and retrieval evaluation | **Planned** |
| **Phase 4** | Agentic workflow, testing, and project finalization | **Planned** |


---

## 📂 Available Documentation

- [Healthcare glossary](docs/healthcare_glossary.md)
- [Healthcare data flow](docs/healthcare_data_flow.md)
- [Synthetic prior-authorization scenario](docs/prior_authorization_scenario.md)
- [Prior-authorization criteria checklist](docs/prior_authorization_criteria_checklist.md)
- [Privacy and healthcare standards](docs/privacy_and_standards.md)

These documents support the learning process and use fictional scenarios. Confirm that each linked file exists in the repository.

---

## 🔐 Privacy and Safety Principles

- Use synthetic data for development and demonstrations.
- Minimize the information processed and retained.
- Preserve evidence provenance and identify missing information explicitly.
- Do not treat missing documentation as proof that a clinical criterion is unmet.
- Include human review for consequential decisions.
- Review access controls, logging, retention, and external service data-handling terms before processing sensitive information.
- Do not claim regulatory compliance or production readiness without appropriate implementation, assessment, and evidence.

Sensitive-information detection and redaction tools can miss information. Redaction alone does not establish de-identification or regulatory compliance.

---

## 🧪 Current Limitations

This is an educational portfolio project under development. The initial work has focused on healthcare concepts and documentation. The application, FHIR validation, hybrid retrieval pipeline, workflow orchestration, persistence, and API endpoints must be implemented and tested as the roadmap progresses.

The project does not make binding coverage decisions, replace clinical judgment, guarantee prior-authorization approval, or guarantee payment of subsequent claims.

---

## 🚀 Development Approach

Implementation will proceed in small, testable milestones. Each stage should include synthetic examples, validation, tests, and documentation before advancing. The repository's code and tests are the source of truth for implementation status.

---

## 📌 Disclaimer

This repository is for educational and portfolio purposes only. It is not a medical device, clinical decision-making system, or production healthcare service. Do not commit real patient data, credentials, API keys, `.env` files, or other secrets to this repository.

---

## 👤 Author

**Balakrishna Arigala**

- [GitHub](https://github.com/balakrishna-arigala26)
- [LinkedIn](https://www.linkedin.com/in/balakrishna-arigala/)
