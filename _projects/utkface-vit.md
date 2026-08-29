---
tag: ML-001
title: "UTKFace Multi-Task ViT"
image: "/assets/images/projects/utkface-multitask-diagram.png"
description: "Vision Transformer predicting age, race, and gender from UTKFace with shared attention blocks."
tech: "Python · PyTorch · ViT"
github: "https://github.com/Sohanuzzaman3301/UTKFace_Multitask_ViT"
writeup: ""
order: 5
---
Vision Transformer-based multi-task model predicting age, race, and gender from UTKFace with shared attention blocks. Joint training improves generalization across demographic attributes.

**Architecture:**
- Shared ViT encoder with multi-head self-attention
- Task-specific prediction heads (age regression, race classification, gender classification)
- Joint optimization with weighted loss balancing
- Data augmentation and regularization for improved generalization

**Performance:**
- Trained on 20K+ UTKFace dataset samples
- Achieved competitive accuracy across all three tasks
- Shared attention blocks reduce parameters while maintaining performance

**What you see:** model architecture diagram with shared attention blocks, performance metrics, and confusion matrices.

**Learned:** Multi-task learning, Vision Transformers, joint optimization, and demographic attribute prediction.
