# NeuroPharm: AI Platform for Drug Discovery

## Project Overview

NeuroPharm is an end-to-end AI platform designed to accelerate drug discovery by predicting molecular interactions with target proteins. This project focuses on using machine learning and molecular docking techniques to identify potential drug candidates for specific protein targets, with a current focus on EGFR (Epidermal Growth Factor Receptor).

The platform streamlines the drug discovery process by:
1. Processing molecular data from public databases
2. Generating meaningful features from chemical structures
3. Training AI models to predict bioactivity
4. Validating predictions through molecular docking simulations

## Project Structure

```
├── CONCEPT/               # Project concept and overview
│   └── concept.ipynb
├── EDA/                   # Exploratory Data Analysis
│   └── eda.ipynb
├── PREPROCESSING & MODELLING/  # Data preprocessing and model training
│   ├── proprocessing.ipynb
│   └── proprocessing_model_evaluation.ipynb
├── DOCKING/               # Molecular docking simulations
│   └── docking.ipynb
├── data/                  # Dataset files
│   ├── EGFR_bioactivity.csv
│   ├── EGFR_bioactivity_cleaned.csv
│   ├── X_train_smiles.csv
│   ├── X_valid_smiles.csv
│   ├── X_test_smiles.csv
│   ├── y_train.csv
│   ├── y_valid.csv
│   ├── y_test.csv
│   └── pdb/               # Protein structure files
├── model/                 # Trained models
│   └── xgb_model.json     # XGBoost model
└── requirements.txt       # Project dependencies
```

## Key Features

- **Molecular Representation**: Converts chemical structures (SMILES) into machine-readable formats using Morgan Fingerprints and Graph-based representations
- **Machine Learning Models**: Implements baseline models and advanced Graph Neural Networks (GNNs) for bioactivity prediction
- **Molecular Docking**: Validates AI predictions through physics-based simulations of protein-ligand interactions
- **End-to-End Pipeline**: Provides a complete workflow from data preparation to model evaluation

## Setup Environment

### For Linux/macOS

```bash
# 1) Create virtual environment
python3 -m venv ./venv

# 2) Activate virtual environment
source ./venv/bin/activate

# 3) Upgrade pip and essential packages
./venv/bin/python -m pip install --upgrade pip setuptools wheel

# 4) Install dependencies
./venv/bin/pip install -r requirements.txt
```

### For Windows (PowerShell)

```powershell
# 1) Create virtual environment
python -m venv .\venv

# 2) Activate virtual environment
.\venv\Scripts\Activate.ps1    # (or .\venv\Scripts\activate.bat for cmd)

# 3) Upgrade pip and essential packages
.\venv\Scripts\python.exe -m pip install --upgrade pip setuptools wheel

# 4) Install dependencies
.\venv\Scripts\pip.exe install -r requirements.txt
```

## Important Notes & Tips

- **torch-geometric** often requires platform-specific wheels. If using CUDA, install according to PyG's official instructions matching your torch and CUDA versions. If unsure, use CPU wheels.
- **rdkit-pypi** provides a quick way to install RDKit via pip; for better performance/compatibility, consider using conda if you encounter issues.
- **AutoDock Vina and OpenBabel** are not pure pip packages — follow their official installation instructions and ensure vina & obabel are in your PATH:
  - macOS: `brew install vina open-babel`
  - Ubuntu: `sudo apt install autodock-vina openbabel` (or download releases from official sites)
- If using a container/server without GUI, ensure native dependencies (libglu, etc.) are installed for visualization tools.

## Usage

1. Start with the concept notebook to understand the project's scope and approach
2. Explore the EDA notebook to understand the dataset characteristics
3. Run the preprocessing notebooks to generate features and train models
4. Use the docking notebook to validate predictions with molecular docking

## Dependencies

The project relies on several specialized libraries for cheminformatics, machine learning, and molecular modeling:

```
# Core data science
numpy
pandas
matplotlib
seaborn
tqdm

# Cheminformatics & bio
rdkit-pypi
biopython
chembl_webresource_client

# Machine learning
torch
scikit-learn
scipy
xgboost
transformers

# Molecular visualization
nglview
deepchem
```

## License

[Add appropriate license information here]

## Contributors

[Add contributor information here]