---
layout: page
title: VEDA
description: 3D molecular generation via variance-exploding diffusion with annealing.
img: assets/img/publication_preview/veda.png
importance: 1
category: research
github: https://github.com/peiningzhang/VEDA
---

### Overview

VEDA ("Generation of 3D Molecules via Variance-Exploding Diffusion with Annealing") addresses the trade-off between sampling efficiency and conformational accuracy in 3D molecular generation.

The framework combines continuous coordinate diffusion with discrete molecular-feature generation in a unified SE(3)-equivariant model.

### Method

- A variance-exploding (VE) noise schedule acts like simulated annealing, smoothing the molecular energy landscape during sampling.
- A preconditioning scheme reconciles coordinate prediction with the residual-style objective used by diffusion models.
- VEDA-E uses an EGNN backbone with implicit bond inference, while VEDA-S uses a Semla backbone with explicit bond generation.
- Discrete masked diffusion and a Discrete Flow Matching sampler generate atom and bond features alongside 3D coordinates.
- An arcsin-based scheduler allocates more sampling steps near log-SNR = 0, where the paper finds molecular structure formation to be especially sensitive.

### Evaluation and results

The experiments use QM9 and GEOM-DRUGS, measuring stability, validity, uniqueness, relaxation energy, RMSD, and the number of function evaluations (NFE).

On QM9, VEDA-E reaches 97.9% valid-and-unique molecules with 50 NFE. VEDA-S reaches 98.9% with 100 NFE and remains competitive with only 30 or 50 steps.

On GEOM-DRUGS, VEDA-S achieves 0.995 molecular stability and 0.988 validity-and-connectivity at 100 NFE. Its median relaxation energy is 1.72 kcal/mol, compared with 32.3 kcal/mol for SemlaFlow.

These results show that the same framework can preserve chemical and geometric quality while reducing the sampling cost of 3D generation.

[Paper](https://doi.org/10.1609/aaai.v40i33.40063) · [arXiv](https://arxiv.org/abs/2511.09568) · [Code](https://github.com/peiningzhang/VEDA)
