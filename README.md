# Spotify Tracks — EDA & ML Project

Exploratory data analysis and machine learning on the Spotify Tracks Dataset from Kaggle. This README contains everything needed to reproduce the results from scratch.

## Project Structure

```
├── data/
│   └── raw/
│       └── dataset.csv          # Place downloaded data here
├── notebooks/                   # Jupyter notebooks (or .py scripts)
├── requirements.txt
├── .env.example
└── README.md
```

---

## Requirements

- Python 3.9+
- A free [Kaggle account](https://www.kaggle.com) to download the data

---

## Setup

**1. Clone the repo**
```bash
git clone https://github.com/popokeyry/dsc148_final_project.git
cd dsc148_final_project
```

**2. Create and activate a virtual environment**
```bash
python -m venv venv
source venv/bin/activate        # Mac/Linux
venv\Scripts\activate           # Windows
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```
---

## Data

**Source:** [Spotify Tracks Dataset – Kaggle](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset)

**Download steps:**
1. Go to the link above and click **Download**
2. Unzip the file
3. Place `dataset.csv` inside the `data/raw/` folder

Your structure should look like:
```
data/raw/dataset.csv
```

The dataset contains 114,000 tracks across 114 genre categories with 20 columns — audio features (danceability, energy, tempo, valence, etc.) and a popularity score from 0–100.
 
---
 
## How to Run
 
There is a single notebook. Run all cells **top to bottom**:
 
```bash
jupyter notebook final_notebook_walkthrough.ipynb
```
 
| Section | What it does |
|---------|-------------|
| 1. Setup | Imports libraries |
| 2. Load Data | Reads `dataset.csv`, previews shape and columns |
| 3–N. EDA | Distributions, correlations, hypothesis tests |
| Feature Engineering | Log-transforms duration, encodes categoricals |
| Model Training | Ridge regression and LightGBM with early stopping |
| Evaluation | RMSE, MAE, R² + predicted vs actual + residual plots |
| Ablation Study | Retrains LightGBM 5× with feature groups removed |
 
---
 
## Outputs
 
All figures and results are saved automatically to the `figures/` folder (created on first run):
 
- `fig1` through `fig7` — PDF plots (distributions, correlations, residuals, feature importance, genre error)
- `ablation_results.csv` — table of ablation metrics
---
 
## Reproducing Results
 
- Random seed is set to **100** throughout (`SEED = 100`)
- No GPU required — runs on CPU
- Python version: **3.12**
