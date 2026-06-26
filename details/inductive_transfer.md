# Inductive Transfer Learning 🧠

## Overview
Inductive Transfer Learning is a setting where the source and target tasks are different ($T_s \neq T_t$), but the source and target domains are identical ($D_s = D_t$). The goal is to improve the learning of the target predictive function using inductive bias from the source domain.

## Core Concept
In this scenario, labeled data is available in the target domain to train the target model. It is further divided based on the availability of labeled data in the source domain:
* **Multi-task Learning**: Labeled data is available in both source and target domains, and the tasks are learned simultaneously.
* **Self-taught Learning**: Only unlabeled data is available in the source domain, and the model must learn general features before adapting to the target task.

```mermaid
flowchart TD
    subgraph Same Domain: D_s = D_t
        A[English Text Corpora]
    end

    subgraph Task s: Classification
        A --> B[Predict Sentiment: Positive/Negative]
    end

    subgraph Task t: Extraction
        A --> C[Extract Part-of-Speech Tags]
    end

    B -.-> |Inductive Bias / Features Transferred| C
```

## Seminal Paper
* **Paper**: [A Survey on Transfer Learning (Pan & Yang, 2010)](https://ieeexplore.ieee.org/document/5288526)
