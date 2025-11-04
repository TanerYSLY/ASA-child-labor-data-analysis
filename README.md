> **Ownership & Contributions**
> This is a collaborative repository regarding the American Statistical Association's International Dataquest 2025.
> The project was built largely by **Taner Yeşilay** : **data acquisition & cleaning → EDA & visualization → feature engineering → modeling & evaluation**.
> Team member Ahmed Önder Akkaya carried out the desing and presentation. 
> Contributors provide documentation, reporting, and minor fixes via PRs.

# ASA Child Labor Data Analysis

## Introduction

This repository provides an end-to-end analysis of indicators related to child labor using Jupyter Notebooks. It covers exploratory data analysis (EDA), regression modeling, and clustering. All datasets are stored in the repository root for convenience.

Please check out our official presentation for this project on YouTube, presented by our team member Ahmed Önder Akkaya: https://www.youtube.com/watch?v=-r9DeI_vplI

## Table of Contents

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
├─ 01_04_combined_analysis.ipynb
├─ 02_regression.ipynb
├─ 03_reg2.ipynb
├─ 03_reg3.ipynb
├─ 04_Clustering.ipynb
├─ analyze data.csv
├─ asa_under14_dataset.csv
├─ clustering_data.csv
├─ QuantaQuartet-Sunum.pdf
└─ video explaination.pdf
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


