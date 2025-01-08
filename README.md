# IMMA_Reimplementation

This repository contains a reimplementation of the **ECCV 2024** paper:

**IMMA: Immunizing Text-to-Image Models Against Malicious Adaptation**

The IMMA process includes:
  - Inputs: Pre-trained model weights, images, and corresponding prompts.
  - Outputs: Immunized model weights ready for further fine-tuning and task-specific adaptation.

For more details on the methodology and results, please refer to the [project page](https://www.amberyzheng.com/imma/) and [paper](https://arxiv.org/abs/2311.18815).

## Overview

![pipeline](https://github.com/user-attachments/assets/10fda64e-7cef-4e3b-9c25-418d644833d3)

### IMMA: Immunized Model Weights for Fine-Tuning Adaptation
IMMA is a framework designed to enhance the robustness of pre-trained models. By taking in pre-trained model weights, along with images and corresponding prompts, IMMA produces immunized model weights that serve as a secure and effective foundation for downstream tasks.

After the IMMA training process, the immunized model functions as a new pre-trained model, optimized for further fine-tuning and adaptation to specific tasks, while remaining resilient to malicious adaptation.

## Credits
**Author**: [Amber Yijia Zheng](https://amberyzheng.com/), [Raymond A. Yeh](https://raymond-yeh.com/)

Department of Computer Science, Purdue University

**Conference**: ECCV 2024
