# Spotify Popularity Prediction

A machine learning project to predict Spotify track popularity using audio features, genre information, and artist-level signals.

## Overview

This project explores the relationship between audio characteristics and track popularity on Spotify. Through comprehensive exploratory data analysis (EDA) and multiple modeling approaches, we investigate:

- How well audio features alone can predict popularity
- The contribution of genre classification to popularity prediction
- The impact of artist-level information on model performance
- Model generalization to unseen artists

## Dataset

The dataset contains Spotify track metadata including:
- **Audio features**: danceability, energy, loudness, speechiness, acousticness, instrumentalness, liveness, valence, tempo, duration
- **Musical characteristics**: key, mode, time signature
- **Metadata**: track name, artist name, album name, genre, explicit content flag
- **Target variable**: popularity score (0-100)

## Methodology

### Data Exploration
- Initial data quality assessment (missing values, duplicates, data types)
- Target variable distribution analysis
- Numeric feature exploration and correlation analysis
- Artist-level frequency and popularity analysis
- Multicollinearity detection

### Data Preprocessing
- Feature type identification (numeric, categorical, binary)
- Standard scaling for numeric features
- One-hot encoding for categorical features
- Artist-grouped data splitting to prevent data leakage

### Modeling Approach

#### Baseline Models
- **Model 0**: Global mean predictor (baseline)

#### Audio + Genre Models
- **Model 1**: Ridge Regression with L2 regularization
  - Hyperparameter tuning via cross-validation
  - Handles multicollinearity among audio features
  
- **Model 2**: Random Forest Regressor
  - Captures nonlinear relationships and feature interactions
  - Robust to multicollinearity

#### Artist-Level Signal Experiment
- **Ablation study**: Comparing models with and without artist encoding
- **Leakage-safe target encoding**: Artist popularity prior with smoothing
- **Dual evaluation**: Random split vs. artist-grouped split
- Quantifies the marginal contribution of artist identity

## Key Findings

- Audio features alone show modest predictive power (R² ≈ 0.17)
- Ridge and Random Forest achieve similar performance on audio+genre features
- Artist-level information significantly improves prediction accuracy
- Model performance differs substantially between random and grouped splits, indicating strong artist-driven effects

## Repository Structure

```
spotify-popularity-prediction/
├── spotify-popularity-prediction.ipynb  # Main analysis notebook
├── README.md                            # This file
└── .gitignore                          # Git ignore rules
```

## Requirements

- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- scipy

## Usage

1. Clone the repository
2. Install required packages: `pip install pandas numpy matplotlib seaborn scikit-learn scipy`
3. Open `spotify-popularity-prediction.ipynb` in Jupyter Notebook
4. Run cells sequentially to reproduce the analysis

## Results

The notebook includes:
- Comprehensive EDA with visualizations
- Model comparison tables
- Residual analysis plots
- Feature importance analysis
- Ablation study results comparing feature sets

## Author

EE 344 Final Project

## License

This project is for educational purposes.
