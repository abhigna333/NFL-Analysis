# NFL Prediction Algorithm

A machine learning–based approach for predicting NFL game outcomes and developing a probabilistic betting strategy.

## Overview

This project predicts whether the **home team will win an NFL game** using historical game, team, quarterback, weather, and betting data.

The project evaluates four models:

- Decision Tree
- Logistic Regression
- XGBoost
- Random Forest

The best-performing models are combined into a calibrated ensemble to generate win probabilities and make betting decisions.

## Methodology

1. **Data Preprocessing**
   - Merge NFL game, team, and betting datasets.
   - Encode categorical and binary features.
   - Handle missing values and construct relative team/quarterback features.

2. **Feature Selection**
   - Use **Recursive Feature Elimination (RFE)** to identify useful features.

3. **Model Training & Tuning**
   - Compare Decision Tree, Logistic Regression, XGBoost, and Random Forest.
   - Tune selected models using **Bayesian optimization with Hyperopt**.

4. **Ensemble**
   - Combine the selected models using a **soft Voting Classifier**.
   - Apply **isotonic probability calibration**.

5. **Betting Strategy**
   - Bet on the home team when predicted probability ≥ 60%.
   - Bet on the away team when predicted probability ≤ 40%.
   - Otherwise, no bet is placed.

## Results

The final model was evaluated on **251 unseen games from the 2019 NFL season**.

| Metric | Result |
|---|---:|
| Possible Games | 251 |
| Bets Placed | 198 |
| Bets Won | 162 |
| Win Percentage | **81.82%** |

## Repository Structure

```text
NFL-Prediction/
├── Data/
│   ├── nfl_games.csv
│   ├── nfl_teams.csv
│   └── spreadspoke_scores.csv
├── NFL Analysis.ipynb
└── README.md
````

## Technologies

Python · Pandas · NumPy · Scikit-learn · XGBoost · Hyperopt · Jupyter Notebook

## Running

```bash
git clone https://github.com/abhigna333/NFL-Analysis.git
cd NFL-Analysis
pip install pandas numpy matplotlib scikit-learn xgboost hyperopt
jupyter notebook
```

Open `NFL Analysis.ipynb` and run the notebook sequentially.

## Disclaimer

Results are based on historical data and do not guarantee future betting performance.

```
```
