# MEMORI System Integration Diagram (EKHUFT)

Use this page as slide-ready content for either:
- a **process flow** view, or
- a **system architecture** view.

## Option 1: Process Flow (Clinician-facing workflow)

```mermaid
flowchart LR
    A[Clinician documents in Sunrise EHR\n(physiological + non-physiological patient data)] --> B[Altera platform receives\nstructured patient inputs]
    B --> C[MEMORI algorithm engine\n(runs within Altera at EKHUFT)]
    C --> D[MEMORI calculates\nRisk Score + Risk Level]
    D --> E[Results displayed in Sunrise EHR\nfor clinical decision support]
    D --> F[Results available in\nMEMORI Explainability Dashboard]
    G[New observations, monitoring, and chart updates\nentered into Sunrise EHR] --> B
    G --> H[Continuous recalculation cycle]
    H --> C
```

### Suggested slide title
**"MEMORI Clinical Risk Workflow in Sunrise EHR (EKHUFT)"**

### Suggested callouts
- MEMORI operates **within Altera** and is surfaced in Sunrise EHR.
- Inputs include both physiological and non-physiological data.
- Risk score and risk level update as new data arrives.

---

## Option 2: System Architecture (Where MEMORI sits)

```mermaid
flowchart TB
    subgraph EKHUFT_Clinical_Environment[EKHUFT Clinical Environment]
        C1[Clinicians]
        EHR[Sunrise EHR UI]

        subgraph ALT[Altera Platform]
            INTAKE[Patient data intake layer\n(vitals, labs, observations, notes, context)]
            MEMORI[MEMORI algorithm service]
            SCORE[Risk output service\n(score + level)]
        end

        EXPLAIN[MEMORI Explainability Dashboard]
    end

    C1 -->|Document & review| EHR
    EHR -->|Patient data entry| INTAKE
    INTAKE --> MEMORI
    MEMORI --> SCORE
    SCORE -->|Display risk score/level| EHR
    SCORE -->|Detailed feature-level interpretation| EXPLAIN
    EHR -->|Ongoing monitoring updates| INTAKE
```

### Suggested slide title
**"MEMORI Integration in Altera and Sunrise EHR"**

### Suggested legend
- **Clinical interface:** Sunrise EHR
- **Compute location:** MEMORI algorithm inside Altera
- **Decision outputs:** Risk score + risk level
- **Transparency:** Explainability dashboard

---

## One-line narrative for presenter notes
"At EKHUFT, clinicians enter patient data in Sunrise EHR; MEMORI runs within Altera to process both physiological and non-physiological inputs, generates an updated risk score and level, and presents results in the EHR with optional drill-down through the explainability dashboard."
