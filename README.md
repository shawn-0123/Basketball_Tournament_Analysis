# Wharton Data Science Competition
Selected as competition international finalists (Top 5 / 500 Teams)

This repository contains our work for the Wharton Data Science Competition. To maintain a clean and organized workflow, please follow the Git conventions below.

---

## 📓 Notebooks

The analysis lives in `notebooks/`, split into six focused steps. Run them in order — each one
reads the artifacts the previous one wrote into `processed_data/`.

| Notebook | What it does | Writes |
| --- | --- | --- |
| [`01_preprocessing_and_feature_engineering`](notebooks/01_preprocessing_and_feature_engineering.ipynb) | Loads the raw CSVs, log-transforms skewed columns, min-max scales the stats, derives shooting percentages / point differential / win flag | `games_2022_processed.csv` |
| [`02_team_aggregation_and_elo_ratings`](notebooks/02_team_aggregation_and_elo_ratings.ipynb) | Aggregates the game log to one row per team, runs the Elo system (K = 20) over the season, builds the combined ranking score | `team_agg.csv`, `elo_ratings.json`, `regional_games_with_elo.csv` |
| [`03_matchup_dataset_and_xgboost_model`](notebooks/03_matchup_dataset_and_xgboost_model.ipynb) | Builds the 2,514-game home-vs-away difference dataset, grid-searches and trains the XGBoost classifier (accuracy 0.803, AUC 0.880) | `xgb_win_model.json` |
| [`04_east_regional_predictions`](notebooks/04_east_regional_predictions.ipynb) | Predicts win probabilities for the ten East Regional matchups and charts them | — |
| [`05_regional_ranking_kmeans_clustering`](notebooks/05_regional_ranking_kmeans_clustering.ipynb) | Tiers the North Region teams with K-means (k = 4) and ranks them by distance to centroid | — |
| [`06_kmeans_illustration`](notebooks/06_kmeans_illustration.ipynb) | Standalone explainer figure for K-means; uses synthetic data and depends on nothing else | — |

`WHSDSC_complete_code.ipynb` is the original single-file version, kept for reference.
Raw data lives in `COMPETITION_DATA/`; `processed_data/` is generated and git-ignored.

---

## 📌 Repository Conventions

### 🔧 Git Workflow

#### 1. Cloning the Repository
  ```bash
  git clone https://github.com/shawn-0123/Basketball_Tournament_Analysis
  cd Basketball_Tournament_Analysis
  ```

#### 2. Adding & Committing Changes

Follow this structure when committing changes:

**Commit Message Format**
`git commit -m "[Action] Brief description of the change"`
-   `Add` → For new files or features
-   `Update` → For modifying existing files
-   `Remove` → For deleting files
-   `Fix` → For bug fixes

#### 3. Pushing Changes

After committing, push your changes to the remote repository:
  ```bash
  git push origin main
  ```
