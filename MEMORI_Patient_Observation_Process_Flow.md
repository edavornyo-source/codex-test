# MEMORI Patient Observation to Alert Workflow

```mermaid
flowchart LR
    A[🩺 Patient observations entered in Altera] -->
    B[🧠 MEMORI algorithm calculates score] -->
    C[📊 Score generates risk level] -->
    D[🖥️ Risk level appears on ward board] -->
    E{Risk level = High or Critical?}

    E -- Yes --> F[🚨 Alert triggered to clinical team]
    E -- No --> G[✅ Continue routine monitoring]

    classDef input fill:#E8F1FF,stroke:#2F6FED,stroke-width:2px,color:#0B1F44;
    classDef compute fill:#EFE9FF,stroke:#6A3BE6,stroke-width:2px,color:#2A145F;
    classDef output fill:#E9FFF2,stroke:#1F9D55,stroke-width:2px,color:#0E3D23;
    classDef decision fill:#FFF7E8,stroke:#D97706,stroke-width:2px,color:#5A2E00;
    classDef alert fill:#FFE9E9,stroke:#DC2626,stroke-width:2px,color:#5C1111;

    class A input;
    class B,C compute;
    class D,G output;
    class E decision;
    class F alert;
```

## Step-by-step flow

1. **Patient observations are entered in Altera.**
2. **MEMORI computes a score** from the submitted observations.
3. **The score maps to a risk level** (e.g., Low, Medium, High, Critical).
4. **The risk level is displayed on the ward board** for clinical visibility.
5. **If risk is High or Critical, an alert is triggered** for clinical response.
