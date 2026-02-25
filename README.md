 # QoE Dataset Clustering + GA Feature Selection

This repository contains a pipeline of Jupyter notebooks that:
1) Cleans and engineers features from the AI6G QoE dataset
2) Performs clustering analysis
3) Uses a Genetic Algorithm (GA) to select feature subsets that improve clustering performance.

## Clustering Algorithms:
- K-Means
- DBSCAN
- Agglomerative clustering

## Data source
- Dataset page: https://docenti.ing.unipi.it/g.nardini/ai6g_qoe_dataset.html  
- Reference paper (CEUR-WS): https://ceur-ws.org/Vol-3189/paper_07.pdf

> **Note:** The raw dataset is not included in this repo. Download it from the dataset page above and place it in `data/`.

## Project structure
```
.
├─ notebooks/
│  ├─ task-01-data-cleaning.ipynb
│  ├─ task-02-clustering.ipynb
│  └─ task-05-genetic-algorithm.ipynb
├─ requirements.txt
```

## How to run
Create an environment and install dependencies:
```bash
python -m venv .venv
source .venv/bin/activate   
pip install -r requirements.txt
```

Run the notebooks in order:
1. `notebooks/task-01-data-cleaning.ipynb`  
   Produces:
   - `outputs/features_final_cleaned.csv`
   - `outputs/clustering_data_scaled.csv`

2. `notebooks/task-02-clustering.ipynb`  
   Uses `outputs/clustering_data_scaled.csv`.

3. `notebooks/task-05-genetic-algorithm.ipynb`  
   Uses:
   - `outputs/clustering_data_scaled.csv`
   - `outputs/features_final_cleaned.csv`
