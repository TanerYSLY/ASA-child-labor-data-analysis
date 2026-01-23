# ASA Child Labor Data Analysis | Quanta Quartet

## Introduction

This repository showcases a comprehensive statistical analysis of child labor indicators by **Quanta Quartet**, a winning team in the American Statistical Association's International DataQuest 2025 competition. The project demonstrates advanced data science techniques including exploratory data analysis (EDA), regression modeling, and clustering applied to a global child labor dataset.

Through rigorous statistical methodology, insightful visualizations, and ethical considerations, we aim to uncover patterns and relationships in child labor dynamics across different regions and economic conditions.

**Official Presentation:** https://www.youtube.com/watch?v=-r9DeI_vplI (presented by Ahmed Önder Akkaya)

## Awards

This project won the **American Statistical Association's DataQuest 2025** Turkish regional competition:

- 🥇 **1st Place** — Statistical Insight
- 🥈 **2nd Place** — Data Visualization
- 🥉 **3rd Place** — Consideration of Ethics

*The international leg of the competition is currently ongoing, as of December 2025.*

## Table of Contents

- Awards
- Overview
- Datasets
- Notebook Map
- Project Structure
- Quickstart (Windows PowerShell)
- Reproducibility
- Troubleshooting (Windows)
- Results
- Contributing
- License
- Contact

## Overview

We aim to:

- Understand the dynamics of child labor through multiple indicators
- Produce insights with visual EDA and correlation analyses
- Build and evaluate regression models for inference and prediction
- Cluster similar countries/regions based on selected features

Ethics note: Child labor is a sensitive topic. Results and visualizations should be interpreted responsibly and in context.

## Datasets

CSV files at the repository root:

- `analyze data.csv` — Main dataset for EDA and relationship analysis
- `asa_under14_dataset.csv` — Subset focusing on metrics related to under-14 population
- `clustering_data.csv` — Feature-selected/scaled dataset prepared for clustering

Notes:

- Column names and transformations are documented in the notebooks.
- If you modify any CSV columns or paths, adjust the corresponding notebook cells.

## Notebook Map (Suggested Order)

1. `01_04_combined_analysis.ipynb` — EDA, visualizations, and relationships
2. `02_regression.ipynb` — Baseline regression model(s) and diagnostics
3. `03_reg2.ipynb` — Additional regression experiments (features/parameters)
4. `03_reg3.ipynb` — Further regression variants and comparisons
5. `04_Clustering.ipynb` — Clustering (e.g., K-Means/hierarchical) and interpretation

Each notebook can run independently, but following the order above helps with context.

## Project Structure

```
ASA-child-labor-data-analysis/
├─ src/
│  ├─ 01_04_combined_analysis.ipynb    (EDA & visualizations)
│  ├─ 02_regression.ipynb               (Regression modeling)
│  ├─ 03_reg2.ipynb                     (Regression experiments)
│  ├─ 03_reg3.ipynb                     (Advanced regression)
│  └─ 04_Clustering.ipynb               (Clustering analysis)
├─ Datasets/
│  ├─ analyze data.csv                  (Main EDA dataset)
│  ├─ asa_under14_dataset.csv           (Under-14 metrics subset)
│  └─ clustering_data.csv               (Preprocessed clustering data)
├─ Figures/
│  ├─ figure_02_target_distributions.png
│  ├─ figure_03_gdp_vs_child_employment.png
│  ├─ figure_04_regional_income_comparison.png
│  ├─ figure_05_corrected_temporal_trends.png
│  ├─ figure_06_latest_year_world_map.html
│  ├─ figure_detailed_temporal_analysis.png
│  ├─ figure_regional_temporal_analysis.png
│  └─ figure_regression_assumptions.png
├─ Presentation/
│  ├─ QuantaQuartet-Sunum.pdf
│  ├─ merged-quantaquartet.pdf
│  └─ video explaination.pdf
├─ requirements.txt
└─ README.md
```

## Quickstart (Windows PowerShell)

Run the following from the project root. The commands are tailored for Windows PowerShell.

1) Create and activate a virtual environment

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

If you hit an execution policy error, temporarily allow script execution for this session:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

2) Install dependencies

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

(Optional) Conda users:

```powershell
conda create -n asa-child-labor python=3.11 -y
conda activate asa-child-labor
pip install -r requirements.txt
```

3) Run the notebooks

- In VS Code, open any `*.ipynb`, choose the created environment as the kernel, and run cells.
- Or launch Jupyter:

```powershell
jupyter lab
# or
jupyter notebook
```

## Reproducibility

- Use fixed `random_state`/seeds for stochastic steps.
- Keep consistent Python and package versions (see `requirements.txt`).
- Ensure CSV files remain at the repository root with expected names.

## Troubleshooting (Windows)

- Execution policy error when activating the venv:
	- Use the temporary command shown above (Process-scope Bypass), then re-run activation.
- `jupyter lab` not found:
	- Make sure `jupyterlab` is installed (it is pinned in `requirements.txt`). Reinstall if needed: `pip install jupyterlab`.
- Plotly figures not showing in VS Code/Jupyter:
	- Set a compatible renderer in a notebook cell:

		```python
		import plotly.io as pio
		pio.renderers.default = "notebook_connected"  # or "vscode" / "browser"
		```
- Build errors while installing SciPy (rare on Windows with wheels):
	- Upgrade build tooling and retry:

		```powershell
		python -m pip install --upgrade pip setuptools wheel
		pip install --only-binary=:all: scipy
		```

## Results

Notebooks output charts, model summaries, and metrics, including:

- Correlation heatmaps and distribution/relationship plots (EDA)
- Regression coefficients, confidence intervals, and diagnostics
- Clusters and centroid summaries (optionally with silhouette-like metrics)

## Contributing

Contributions are welcome:

1. Fork the repository
2. Create a feature branch
3. Commit with clear messages
4. Open a Pull Request with context and screenshots if relevant

Use Issues for bug reports and feature requests.

## Team

**Quanta Quartet** is a data science team that achieved recognition at the ASA DataQuest 2025 competition through rigorous statistical analysis and ethical consideration of sensitive topics.

### Team Members

- **Ahmed Önder Akkaya** — Design, Presentation, and GitHub Management
- **Atasagun Yılmaz** — Team Management
- **Taner Yeşilay** — Lead Data Analysis & Modeling (Analytical Framework Design, End-to-End Data Pipeline, Visualization, Statistical Inference, and Insight Generation)
- **Tuana Çevcive** — Supporting Analysis and Visualization, Presentation

### Contact & Resources

For questions or collaboration inquiries, please reach out through the repository's Issues section or contact the team leads.

**Key Resources:**
- [YouTube Presentation](https://www.youtube.com/watch?v=-r9DeI_vplI) — Full project walkthrough
- [Main Presentation Slides](Presentation/QuantaQuartet-Sunum.pdf)
- [Merged Analysis Document](Presentation/merged-quantaquartet.pdf)

---

*This project prioritizes ethical considerations when working with sensitive data on child labor. All insights and visualizations should be interpreted responsibly and in their proper social context.*
