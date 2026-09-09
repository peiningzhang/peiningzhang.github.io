---
layout: page
title: Unraveling the Potential of Diffusion Models in Small Molecule Generation
description: A review of diffusion models for molecular generation and drug discovery.
img: assets/img/publication_preview/survey-sbdd.png
importance: 2
category: research
---

### Scope

This review studies how diffusion models are being used for small-molecule generation and drug discovery, from basic mathematical formulations to protein-pocket-aware design.

It explains forward and reverse diffusion, DDPMs, score-based models, and the role of equivariance in preserving the geometry of 3D molecules.

### A taxonomy of molecular diffusion models

The paper organizes methods along several dimensions:

- target-free versus target-aware generation;
- molecular conformation generation versus de novo molecule generation;
- 1D SMILES, 2D graphs, and 3D point-cloud or voxel representations;
- DDPM versus score-based formulations; and
- SE(3)-equivariant, permutation-equivariant, or non-equivariant architectures.

This taxonomy connects the representation and conditioning choices to practical goals such as chemical-space exploration, conformation generation, docking, and ligand design.

### Benchmark and findings

The study benchmarks 18 representative models across QM9, GEOM-Drugs, and CrossDocked2020. It considers validity, uniqueness, novelty, atom and molecule stability, Validity3D, QED, synthetic accessibility, Vina score, and strain energy.

For target-free generation, MiDi shows a strong combination of stability and validity. For target-aware generation, KGDiff performs best in the post-relaxation comparison, although results vary substantially across models and targets.

The review also finds that force-field relaxation can increase average 3D validity from 1.42% to 37.0%, while sometimes changing binding-related scores. This highlights the need for evaluation protocols that measure both chemical validity and physical realism.

### Open challenges

The paper identifies data sparsity, limited interpretability, unreliable evaluation metrics, high computational cost, and missing physics-based constraints as major obstacles.

Future directions include physics-informed diffusion, better target-aware and multimodal modeling, more realistic benchmarks, and methods that make the generation process easier to inspect.

[Paper](https://doi.org/10.1016/j.drudis.2025.104413) · [arXiv](https://arxiv.org/abs/2507.08005)
