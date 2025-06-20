# Movie Recommendation System

This project demonstrates a personalized movie recommendation system using the [MovieLens 100K dataset](https://grouplens.org/datasets/movielens/100k/). It leverages collaborative filtering and hybrid modeling techniques to recommend movies based on user preferences.

---

## Project Overview

- **Goal**: Build a movie recommender system that provides accurate and relevant movie suggestions to users.
- **Dataset**: MovieLens 100K, including `ratings.csv`, `movies.csv`, and `tags.csv`.

---

## Business Understanding

Modern streaming platforms must recommend content users will enjoy to drive engagement. This system is built to simulate such a platform by learning from historical ratings and genres.

---

## Data Understanding & Cleaning

- **Ratings**: 100,836 entries from 610 users and 9,724 movies.
- Cleaned and merged `ratings.csv` with `movies.csv` to produce a structured dataset.
- Removed unused columns such as timestamps.

---

## Data Preparation

- Transformed data using the Surprise `Reader` object.
- Used an 80/20 train-test split to evaluate performance.

---

## Modeling

Implemented two collaborative filtering models using the Surprise library:

| Model     | RMSE   | MAE   |
|-----------|--------|-------|
| **SVD**   | 0.8368 | 0.6395 |
| KNNBasic  | 0.8844 | 0.6753 |

➡️ **SVD outperformed KNNBasic** on both metrics.

---

## Top Recommendations (User 555)

1. Alien (1979) — ⭐ 4.55  
2. Raiders of the Lost Ark (1981)  
3. Clockwork Orange, A (1971)  
4. Star Wars: Episode V - The Empire Strikes Back (1980)  
5. Terminator 2: Judgment Day (1991)  

---

## Insights

- Drama, Comedy, and Thriller are the most frequently rated genres.
- Hybrid models combining collaborative and content-based filtering improve cold-start performance.
- Regular model retraining is important to capture evolving user behavior.

---

## Recommendations

- Deploy SVD-based recommender as the core engine.
- Introduce hybrid filtering for improved cold-start handling.
- Periodically retrain the model on new data.
- Consider expanding with additional features (e.g., tags, demographics).

---


