# 🧪 Molecule Solubility Predictor

An AI/ML project that predicts the **water solubility of organic molecules** directly from their chemical structure — built as a hands-on exploration of cheminformatics (chemistry + machine learning).

Type in any molecule name (e.g. "aspirin", "caffeine") and get an instant prediction, its 2D structure, and a plain-English explanation of *why* it dissolves the way it does.

## 🎯 What it does

1. Takes a molecule name → looks up its structure via PubChem
2. Extracts 7 key chemistry features using **RDKit** (molecular weight, LogP, TPSA, H-bond donors/acceptors, rotatable bonds, ring count)
3. Predicts water solubility using a trained **Random Forest** model
4. Explains the prediction in plain language, based on the dominant chemistry feature (LogP)
5. Shows the molecule's 2D structure

## 📊 Results

| Model | R² Score | RMSE |
|---|---|---|
| Linear Regression | 0.758 | 1.07 |
| **Random Forest** | **0.861** | **0.81** |

**Key insight:** LogP (a measure of how much a molecule "prefers" fat/oil over water) drives **82%** of the model's predictions — this matches real chemistry, where polarity is the primary driver of aqueous solubility.

## 🧠 Dataset

Trained on the **ESOL (Delaney) solubility dataset** — ~1,100 molecules with real, lab-measured water solubility values.

## ⚠️ Limitations

This model is trained on small, organic, drug-like molecules. It does **not** produce meaningful predictions for:
- Bare elements or metals (e.g. sodium)
- Ions or inorganic salts (e.g. NaCl)
- Very large molecules (proteins, polymers)

These fall outside the training distribution — a good example of *out-of-distribution* prediction limits in ML.

## 🛠️ Built with

- **RDKit** — chemistry feature extraction & structure drawing
- **scikit-learn** — Linear Regression & Random Forest models
- **PubChemPy** — molecule name → structure lookup
- **Gradio** — interactive web interface

## 🚀 How to run

1. Open `Molecule_Solubility_Predictor.ipynb` in Google Colab
2. Run all cells in order
3. Use the Gradio interface at the bottom to search any molecule by name

## 👤 About

Built by Shashidhar as a first hands-on AI/ML project, combining a Chemistry background with practical machine learning.
