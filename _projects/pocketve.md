---
layout: page
title: PocketVE
description: Stable and property-guided structure-based drug design with variance-exploding diffusion.
img: assets/img/projects/pocketve/denoised.gif
img_avoid_scaling: true
importance: 0
category: research
---

### Overview

**PocketVE: Stable and Property-Guided Structure-Based Drug Design with Variance-Exploding Diffusion**

Peining Zhang and Jinbo Bi · NeurIPS 2026

[Paper](https://arxiv.org/abs/2609.08101) · [PDF](https://arxiv.org/pdf/2609.08101)

PocketVE generates 3D molecules conditioned on a protein pocket, combining stable coordinate denoising with inference-time property guidance.

### Generation in action

{% include generation_animation.liquid name="PocketVE" denoised="/assets/img/projects/pocketve/denoised.gif" generation="/assets/img/projects/pocketve/generation.gif" caption="Denoised ligand predictions evolve inside the protein pocket over 100 sampling steps. The camera and scale remain fixed." %}

The animation uses a recorded sampling trajectory. The ligand coordinates have not been replaced with docked or minimized coordinates.

### Method

- Variance-exploding diffusion provides the coordinate denoising framework.
- Classifier-free guidance steers molecular properties at inference time without external property classifiers.
- Adaptive protein perturbation regularizes pocket conditioning during training.

### Evaluation

The paper evaluates PocketVE on CrossDocked2020 using the GenBench3D protocol. Relative to the TAGMol architectural baseline, reported Valid3D improves from 58.6 to 80.6, while strain energy decreases from 457.4 to 127.9.

Moderate guidance balances molecular properties and geometric quality. Stronger guidance can degrade geometry and distributional fidelity, highlighting the importance of considering these objectives together.
