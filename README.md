# SST El Niño Anomaly Detection Portfolio

A portfolio-ready, reproducible machine learning notebook project for detecting **sea surface temperature (SST) anomalies** as a proxy signal for **El Niño-related variability** using **Isolation Forest** and comparator methods.

## Project Overview

This repository demonstrates an end-to-end anomaly detection workflow on TAO buoy SST observations:
- Data loading and preprocessing
- Monthly SST anomaly proxy construction
- Unsupervised model benchmarking (`IsolationForest`, `OneClassSVM`, `LocalOutlierFactor`)
- Robustness and sensitivity diagnostics
- Exported results for transparent review

The focal method is **Isolation Forest**, with benchmarking included for fair comparison.

## Repository Structure

```text
sst-el-nino-iforest/
├── notebooks/
│   ├── isolation_forest_sst_el_nino.ipynb
│   └── isolation_forest_sst_el_nino.executed.ipynb
├── data/
│   └── elnino.csv
├── results/
│   ├── benchmark_metrics.csv
│   ├── monthly_predictions.csv
│   ├── iforest_sensitivity.csv
│   ├── proxy_threshold_diagnostics.csv
│   ├── feature_set_comparison.csv
│   ├── model_agreement_by_month.csv
│   ├── top_proxy_months.csv
│   ├── iforest_case_summary.csv
│   └── data_missingness_summary.csv
├── figures/
│   ├── sst_proxy_trend.png
│   ├── iforest_timeline.png
│   ├── benchmark_comparison.png
│   ├── iforest_sensitivity_heatmap.png
│   └── model_agreement_overview.png
├── requirements.txt
├── .gitignore
└── LICENSE
```

## Quick Start

### 1) Create environment

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 2) Launch and run notebook

```bash
jupyter notebook
```

Open one of:
- `notebooks/isolation_forest_sst_el_nino.executed.ipynb` (already contains outputs; best for quick review)
- `notebooks/isolation_forest_sst_el_nino.ipynb` (cleaner version for re-run)

## Reproducibility Contract

- Input dataset: `data/elnino.csv`
- Output tables: generated in `results/`
- Supporting visuals: available in `figures/`

The notebook is configured to resolve paths from this repo root (`data/`, `results/`) so it can run independently from any parent project.

## Portfolio Highlights

- Reproducible notebook workflow with explicit exported artifacts
- Comparative unsupervised anomaly detection benchmarks
- Clear separation of inputs (`data/`), analysis (`notebooks/`), and outputs (`results/`, `figures/`)
- GitHub-friendly structure suitable for reviewer/recruiter inspection

## Notes

- This project uses an internal SST anomaly proxy for evaluation and analysis.
- Results should be interpreted as anomaly-detection benchmarking, not official ENSO ground-truth classification.
