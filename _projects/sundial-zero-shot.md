---
layout: page
title: Zero-Shot Transfer Capabilities of the Sundial Foundation Model for Leaf Area Index Forecasting
description: Zero-shot leaf area index forecasting with a time-series foundation model.
importance: 3
category: research
github: https://github.com/peiningzhang/sundial-lai
---

### Research question

Can a general-purpose time-series foundation model forecast Leaf Area Index (LAI) without task-specific training? This work evaluates Sundial in a strict zero-shot setting and compares it with models trained specifically for LAI forecasting.

### Data and setup

The experiments use the HiQ LAI dataset, derived from MODIS observations from 2000 to 2022. The study uses the continental United States subset at 5-km spatial resolution, with one observation every eight days and roughly 1,050 time steps per pixel.

The comparison includes Mean, Last Value, Trend, ARIMA, a supervised two-layer LSTM, and the pretrained Sundial model. Sundial is used without fine-tuning and generates forecasts autoregressively from the historical sequence as an in-context prompt.

The evaluation varies the input context from 32 to 1,024 time steps and tests forecast horizons of 1, 4, 8, and 12 steps, corresponding to 8, 32, 64, and 96 days. Metrics include MAE, RMSE, R², MAPE, and CVRMSE.

### Main findings

For one-step forecasting, Sundial reaches an RMSE of 0.140 and an R² of 97.32% with a 1,024-step context, essentially matching the best supervised LSTM result while using no task-specific training.

The key result is a context-length crossover. The LSTM performs best with short contexts, while Sundial improves steadily as more history is provided. With a 512-step context, Sundial outperforms the LSTM for horizons of four steps or longer; for example, the RMSE at horizon four is 0.189 for Sundial versus 0.198 for the LSTM.

The results suggest that Sundial uses long-context in-context learning to capture pixel-specific seasonal patterns, while the LSTM relies more heavily on dataset-level average behavior.

### Limitations and next steps

The method currently needs long historical windows, focuses on univariate LAI, and has higher inference cost than lightweight baselines. The paper points to climatological covariates, multivariate forecasting, few-shot adaptation, and broader geographic transfer as natural next steps.

[Paper](https://arxiv.org/abs/2511.20004) · [PDF](https://arxiv.org/pdf/2511.20004) · [Code](https://github.com/peiningzhang/sundial-lai) · [Dataset](https://essd.copernicus.org/articles/16/1601/2024/)
