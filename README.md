# IMMA_Reimplementation

This repository contains a reimplementation of the **ECCV 2024** paper:

**[IMMA: Immunizing Text-to-Image Models Against Malicious Adaptation](https://arxiv.org/abs/2311.18815)**

The IMMA framework enhances the security of generative models by immunizing them against harmful adaptations. This repository provides a detailed implementation, experimentation, and results analysis based on the original methodology proposed in the paper.

## Overview

![Pipeline](https://github.com/user-attachments/assets/10fda64e-7cef-4e3b-9c25-418d644833d3)

IMMA provides a **model-level defense** by modifying the internal parameters of pre-trained models to resist malicious fine-tuning, such as style replication and sensitive content generation, while retaining the model's usability for benign tasks. The process includes:
- **Inputs**: Pre-trained model weights, images, and corresponding prompts.
- **Outputs**: Immunized model weights resistant to unauthorized adaptations.

## Key Features of Reimplementation

1. **Adaptation Resistance**: Evaluates the ability of IMMA to prevent unauthorized relearning of specific styles (e.g., Van Gogh's art) and personalized content generation (e.g., DreamBooth).
2. **Computational Challenges**: Adjustments were made for resource efficiency, including:
   - Lowering resolution from 512 to 256 pixels.
   - Reducing training epochs from 50 to 11.
   - Utilizing mixed-precision FP16 instead of FP32.
3. **Experimental Validation**: Demonstrated the effectiveness of IMMA across two primary tasks:
   - **Relearning Prevention**: Preventing unauthorized relearning of an erased Van Gogh style.
   - **DreamBooth Personalization**: Blocking unauthorized personalized content creation (e.g., "a purse on a beach").

## Experimental Setup

### 1. Relearning Artistic Styles
- **Objective**: Prevent the model from relearning erased artistic styles using LoRA.
- **Metrics**: CLIP and DINO similarity scores were used to evaluate adaptation.
- **Results**:
  - Without IMMA: High similarity scores (e.g., CLIP ~0.9).
  - With IMMA: Strong resistance to relearning (CLIP ~0.75, DINO ~0.3).

### 2. Personalized Content Adaptation
- **Objective**: Evaluate IMMA's performance against DreamBooth adaptation for content generation.
- **Metrics**: CLIP and DINO similarities for a target concept ("a purse on a beach").
- **Results**:
  - Without IMMA: Successful adaptation (CLIP ~0.875).
  - With IMMA: Constrained adaptation (CLIP ~0.75).

## Challenges and Optimizations

1. **Resource Constraints**:
   - The full model required significant memory (~20GB).
   - Experiments were adjusted to run efficiently on GPUs like A10, A30, and A100, while avoiding OOM errors on lower-capacity GPUs like V100.

2. **Computational Adjustments**:
   - Reduced input resolution and training duration for efficiency.
   - Enabled mixed-precision training (FP16) to optimize memory usage.

## Future Directions

1. **Improving Scalability**:
   - Enhance the computational efficiency of IMMA's bi-level optimization for larger models.
2. **Extending Protection**:
   - Develop methods to immunize against multiple adaptation targets simultaneously.
3. **Selective Immunization**:
   - Create adaptive mechanisms to balance malicious adaptation resistance and flexibility for benign tasks.

## How to Run 
1. Clone the repository:
   ```bash
   git clone https://github.com/heesookiim/IMMA_Reimplementation.git
   cd IMMA_Reimplementation

2. Run all cells in Reimplementation.ipynb


## Credits

**Authors**: [Amber Yijia Zheng](https://amberyzheng.com/), [Raymond A. Yeh](https://raymond-yeh.com/) (Department of Computer Science, Purdue University)

**Conference**: ECCV 2024

Reimplementation by: [Heesoo Kim](http://heesookiim.github.io) (Elmore Family School of Electrical and Computer Engineering, Purdue University)
