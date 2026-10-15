# Healthcare Data Flow — MedAuth-Agentic

> Simplified educational workflow using fictional data.

```mermaid
flowchart TD
    A[Patient] --> B[Provider: Clinic or Hospital]
    B --> C[EMR or EHR: Clinical Documentation]
    C --> D{Prior authorization required?}
    D -- No --> E[Continue applicable care workflow]
    D -- Yes --> F[Submit Request and Supporting Evidence]
    F --> G[Payer: Health Plan or Insurer]
    G --> H[Evaluate Request Against Plan Rules]
    H --> I[Communicate Outcome or Request More Information]

    C -. Synthetic clinical data .-> J[MedAuth-Agentic Prototype]
    K[Fictional Payer Policies] --> L[RAG Policy Retrieval]
    J --> L
    L --> M[Evidence Assessment and Missing Information]
    M --> N[Source-Cited Draft Recommendation]
    N --> O[Human Reviewer]
