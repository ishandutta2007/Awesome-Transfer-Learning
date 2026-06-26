# The Supervised Computer Vision Era (~2012–2018) 👁️

## Overview
The supervised computer vision era marked the initial breakthrough of deep transfer learning. It was characterized by training deep Convolutional Neural Networks (CNNs) on large-scale supervised datasets (most notably ImageNet, which contains over 14 million annotated images across 1,000 categories) and reusing the learned feature representations for downstream tasks.

## Core Concept
Deep convolutional networks learn hierarchical feature representations. The early layers learn generic features such as edges, textures, and color blobs, while the deeper layers learn task-specific features (shapes, objects). 

In this era:
1. A network (like AlexNet, VGG, or ResNet) is pre-trained on ImageNet.
2. The classification head (final fully connected layer) is discarded.
3. The remaining layers (frozen backbone) act as a feature extractor.
4. A new head is added and trained on the target domain dataset.

```mermaid
flowchart TD
    subgraph Pre-training Phase (Source)
        A[ImageNet Dataset] --> B[CNN Backbone: AlexNet/VGG/ResNet]
        B --> C[1000-Class Classification Head]
    end

    subgraph Transfer & Fine-Tuning Phase (Target)
        D[Target Domain Dataset] --> E[Frozen CNN Backbone]
        E --> F[New Custom Head]
        F --> G[Target Outputs]
    end

    B -.-> |Weights Transferred & Frozen| E
```

## Seminal Paper
* **Paper**: [ImageNet Classification with Deep Convolutional Neural Networks (Krizhevsky et al., 2012)](https://proceedings.neurips.cc/paper/2012/hash/c3982bc38a8dbd74b5cd367555ddad57-Abstract.html)
