# Transductive Transfer Learning (Domain Adaptation) 🔄

## Overview
Transductive Transfer Learning (often referred to as Domain Adaptation) is a setting where the source and target tasks are identical ($T_s = T_t$), but the source and target domains are different ($D_s \neq D_t$). No labeled data is available in the target domain, but ample labeled data is available in the source domain.

## Core Concept
The challenge in transductive transfer learning is to overcome the domain gap or covariate shift. The input data distribution shifts significantly between the source and target domains, but the underlying classification or regression function remains the same.

```mermaid
flowchart LR
    subgraph Source Domain: D_s (Daytime)
        A[Daytime Camera Images] --> B[Object Detection Task]
    end

    subgraph Target Domain: D_t (Nighttime)
        C[Nighttime Thermal Images] --> B
    end

    A -.-> |Domain Alignment / Adaptation| C
```

## Seminal Paper
* **Paper**: [A Survey on Transfer Learning (Pan & Yang, 2010)](https://ieeexplore.ieee.org/document/5288526)
