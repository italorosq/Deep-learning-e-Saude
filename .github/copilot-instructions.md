# Copilot Instructions

## Project Overview

This repository is a **Deep Learning and Health** project focused on classifying medical transcriptions into medical specialties using Natural Language Processing (NLP) and machine learning. The project explores and compares text classification models (e.g., Naive Bayes variants) applied to real-world clinical data.

## Repository Structure

- `Notebooks/` — Jupyter notebooks containing the full analysis and model training pipeline (`notebookprincipal.ipynb`)
- `Database/` — CSV datasets used by the notebooks:
  - `mtsamples.csv` — Medical transcription samples with fields: `description`, `medical_specialty`, `sample_name`, `transcription`, `keywords`
  - `Disease precaution.csv` — Disease precaution data

## Tech Stack

- **Language:** Python 3
- **Environment:** Jupyter Notebook
- **Core libraries:**
  - `pandas`, `numpy` — data loading and manipulation
  - `matplotlib`, `seaborn` — data visualization
  - `spacy` (model: `en_core_web_sm`) — NLP text preprocessing (lemmatization, stop-word removal)
  - `scikit-learn` — TF-IDF vectorization, Naive Bayes classifiers (`MultinomialNB`, `ComplementNB`), model evaluation, cross-validation, GridSearchCV
  - `imbalanced-learn` (`imblearn`) — class imbalance handling (`RandomUnderSampler`)

## Key Conventions

- Notebooks use Portuguese comments and chart titles (e.g., `'Distribuição das Top 10 Especialidades Médicas'`).
- Text preprocessing is done via a `limpar_texto` function that lowercases, lemmatizes, and removes stop words and punctuation using spaCy.
- Dataset paths in the notebook are absolute Windows paths — when contributing, update them to relative paths (e.g., `../Database/mtsamples.csv`).
- Model evaluation uses `StratifiedKFold` with 30 splits across 100 random train/test splits (`GridSearchCV` per run) to ensure robust results.

## Development Notes

- Load datasets relative to the repository root: `../Database/<filename>.csv` from within `Notebooks/`.
- When adding new classifiers or experiments, follow the existing pattern of storing results in a list and exporting to CSV.
- Prefer `classification_report` from scikit-learn for model evaluation output.
