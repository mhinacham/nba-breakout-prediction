# NBA Breakout Prediction

A machine learning project that analyzes historical NBA player performance to identify and rank young players with breakout potential.

The project uses NBA player-season data from 1998–2025 to examine player development patterns, build predictive models, and evaluate whether historical performance and year-over-year trajectory can help identify future breakout players.

## Project Objective

The goal of this project is to answer:

**Can historical player performance and development trajectory be used to identify young NBA players who are likely to break out the following season?**

Rather than treating the model as a definitive prediction system, the project focuses on its usefulness as a **candidate-ranking and decision-support tool**.

## Methodology

The analysis includes:

1. Data cleaning and preprocessing of historical NBA player statistics
2. Exploratory analysis of breakout patterns by age and playing time
3. Construction of a quantitative breakout definition
4. Feature engineering using player performance and development trajectory
5. Logistic Regression and Random Forest modeling
6. Time-based evaluation using future seasons
7. Historical backtesting of player rankings

Key features include:

- Age
- Games played and games started
- Minutes per game
- Points, rebounds, and assists
- Shooting efficiency
- Steals, blocks, and turnovers
- Year-over-year changes in production and playing time

## Model Performance

Adding player trajectory information improved the model's ability to distinguish future breakout players.

| Model | ROC-AUC |
|---|---:|
| Baseline Model | 0.678 |
| Trajectory Model | 0.695 |

The trajectory-based model improved ROC-AUC from **0.678 to 0.695** on the same evaluation sample.

## Historical Backtest

A historical backtest was used to evaluate how effectively the model ranked players who actually broke out the following season.

| Ranking Cutoff | Actual Breakouts Captured | Recall |
|---|---:|---:|
| Top 5 | 2 / 12 | 16.7% |
| Top 10 | 3 / 12 | 25.0% |
| Top 20 | 5 / 12 | 41.7% |
| Top 25 | 7 / 12 | 58.3% |
| Top 50 | 10 / 12 | 83.3% |

These results suggest that the model provides useful signal for narrowing a large player pool into a smaller group of breakout candidates.

## Key Findings

- Young-player breakout prediction contains measurable predictive signal.
- Player age, role, playing time, production, efficiency, and recent development trajectory provide useful information.
- Logistic Regression performed competitively with a more complex Random Forest model.
- Adding year-over-year trajectory features improved predictive performance.
- The model is more useful as a **ranking system** than as a definitive yes/no predictor of player development.

## Repository Structure

```text
nba-breakout-prediction/
├── data/
│   ├── raw/
│   └── processed/
├── figures/
├── notebooks/
│   └── breakout_analysis.ipynb
├── src/
├── README.md
└── .gitignore
```

## Tools

- Python
- pandas
- NumPy
- scikit-learn
- Matplotlib
- Jupyter Notebook

## Limitations and Future Work

Future versions of the model could incorporate advanced metrics, player position, team context, injuries, roster changes, and more detailed measures of opportunity.

Additional modeling approaches and rolling-season backtests could also be used to evaluate how consistently the ranking system performs across different NBA seasons.