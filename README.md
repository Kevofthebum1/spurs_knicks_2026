# Spurs vs. Knicks 2026 NBA Finals Win Prediction

## Project Overview

This project uses historical NBA game data to predict NBA game outcomes, with a focus on the 2026 NBA Finals matchup between the San Antonio Spurs and the New York Knicks.

The goal of this project is to build a machine learning model that can estimate whether a team will win a game using pre-game information such as home-court advantage, season record, recent team performance, opponent strength, rest days, and rolling performance trends.

## Research Question

Can historical NBA team statistics and recent performance trends be used to predict NBA game winners and apply those predictions to the Spurs vs. Knicks 2026 NBA Finals matchup?

## Dataset

The dataset used in this project comes from Kaggle:

**Historical NBA Data and Player Box Scores**
https://www.kaggle.com/datasets/eoinamoore/historical-nba-data-and-player-box-scores

Main files used:

* `TeamStatistics.csv`
* `Games.csv`

The dataset includes historical NBA team statistics, game results, scores, team box scores, and game-level information.

## Project Workflow

The notebook follows these main steps:

1. Import NBA data using KaggleHub
2. Load team statistics and game-level datasets
3. Merge the datasets using `gameId`
4. Clean missing values and handle invalid values
5. Create a binary target variable for wins and losses
6. Engineer pre-game prediction features
7. Train and compare multiple machine learning models
8. Evaluate model performance
9. Apply the best model to the Spurs vs. Knicks matchup

## Feature Engineering

To avoid data leakage, the model does not use post-game information such as final score, point differential, quarter-by-quarter scoring, or in-game statistics as direct prediction features.

Instead, the project uses pre-game and historical features, including:

* Home-court advantage
* Season wins and losses
* Season win percentage
* Opponent season win percentage
* Rest days
* Back-to-back game indicator
* Rolling 5-game performance averages
* Rolling 10-game performance averages
* Recent win percentage
* Recent point differential
* Opponent comparison features

These features help the model compare how each team has been performing recently against the strength of its opponent.

## Models Tested

The following machine learning models were tested:

* Logistic Regression
* Random Forest Classifier
* Gradient Boosting Classifier
* HistGradientBoosting Classifier

## Results

The baseline model started with simple features such as home-court advantage and season record. Additional rolling performance and opponent comparison features improved the model’s performance.

| Model                | Accuracy |
| -------------------- | -------: |
| Logistic Regression  |      64% |
| Random Forest        |      68% |
| Gradient Boosting    |      69% |
| HistGradientBoosting |      72% |

The best-performing model was the **HistGradientBoosting Classifier**, which achieved approximately **72% accuracy**.

## Key Takeaways

* Basic features like home-court advantage and season record provide a useful baseline.
* Rolling 5-game and 10-game averages improved the model by capturing recent team performance.
* Opponent comparison features helped the model better understand matchup strength.
* HistGradientBoosting performed best among the models tested.
* NBA game prediction is challenging because outcomes can be affected by injuries, rotations, rest, coaching decisions, and shooting variance.

## Limitations

This model should be viewed as a statistical prediction tool, not a guaranteed forecast.

Some limitations include:

* Player injuries were not included.
* Betting odds were not included.
* Player-level matchup data was not included.
* Future games may require manually created prediction rows if they are not already available in the dataset.
* Sports outcomes are naturally unpredictable, so accuracy has practical limits.

## Tools Used

* Python
* pandas
* NumPy
* scikit-learn
* KaggleHub
* Matplotlib
* Jupyter Notebook

## Repository Structure

```text
spurs_knicks_2026/
│
├── README.md
├── requirements.txt
├── .gitignore
│
└── notebooks/
    └── 2026_NBA_Playoffs_Spurs_vs_Knicks_Win_Prediction_REWORKED.ipynb
```

## How to Run This Project

1. Clone this repository.

```bash
git clone https://github.com/YOUR_USERNAME/spurs_knicks_2026.git
```

2. Install the required Python packages.

```bash
pip install -r requirements.txt
```

3. Open the final notebook.

```text
notebooks/2026_NBA_Playoffs_Spurs_vs_Knicks_Win_Prediction_REWORKED.ipynb
```

4. Run the notebook from top to bottom.

The dataset is loaded using KaggleHub, so a Kaggle account or Kaggle API setup may be required depending on the environment.

## Author

Kevin Luu
