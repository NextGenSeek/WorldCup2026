# World Cup 2026 Prediction Model

## Overview

This project predicts international football match outcomes and scorelines using an ensemble of machine learning and statistical models.

The model combines:

* **XGBoost** for match outcome prediction (Home Win, Draw, Away Win)
* **Poisson Regression** for expected goals and scoreline probabilities
* **Elo Ratings** adjusted for tournament importance
* Recent team form and scoring trends
* Tournament importance weighting

The final predictions are generated using an optimised ensemble of XGBoost and Poisson probabilities.

---

## Features

The model uses a range of historical and team-strength features, including:

* Home and away Elo ratings
* Elo rating difference
* Elo rating trend over recent matches
* Recent form (last 5 matches)
* Average goals scored (last 10 matches)
* Average goals conceded (last 10 matches)
* Tournament importance
* Tournament type

---

## Models

### XGBoost Classifier

Predicts:

* Home Win
* Draw
* Away Win

Hyperparameters are optimised using time-series cross-validation.

### Poisson Goal Models

Separate Poisson regression models are trained for:

* Home goals
* Away goals

These models estimate expected goals and generate probabilities for all possible scorelines.

### Ensemble

The final prediction combines:

* XGBoost outcome probabilities
* Poisson outcome probabilities

The ensemble weight is automatically optimised using historical test data.

A small draw adjustment is applied to compensate for the tendency of machine learning models to underpredict draws.

---

## Data Source

Historical international match results were obtained from:

https://github.com/martj42/international_results

The dataset contains almost 50,000 international football matches, including FIFA World Cup, continental championships, qualification matches and friendlies.

---

## Disclaimer

This project is intended for educational and research purposes. Football matches are inherently unpredictable and model predictions should not be considered financial or betting advice.