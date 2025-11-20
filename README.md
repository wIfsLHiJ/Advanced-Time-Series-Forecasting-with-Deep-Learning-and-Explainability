# Advanced Time-Series Forecasting (LSTM) + Explainability (SHAP)

This repository contains a complete project pipeline that:
- Generates a synthetic **multivariate** time-series (3 interacting features)
- Trains an **LSTM** model for **multi-step** forecasting using a walk-forward validation strategy
- Evaluates forecasting accuracy (RMSE, MAE)
- Produces model explainability using **SHAP** (DeepExplainer aggregated)
- Saves plots and outputs for submission

---

## Files
- `main.py` — full pipeline (data gen, training, CV, SHAP, plotting)
- `requirements.txt` — required Python packages
- `outputs/` — runtime outputs (CSV, plots, model, JSON summaries)
- Uploaded visual reference (if included): `/mnt/data/WhatsApp Image 2025-11-20 at 8.48.29 AM.jpeg`

---

## Quick Start

1. Clone or copy repository.
2. Create a Python virtual environment (recommended).
3. Install dependencies:

```bash
pip install -r requirements.txt
