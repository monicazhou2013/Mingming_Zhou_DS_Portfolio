
# Movie Recommendation System (ALS + TMDB Posters)

**Databricks Notebook:**  
https://dbc-a83b6333-0c2f.cloud.databricks.com/editor/notebooks/3300119515183161?o=7474643825711867#command/7835941542853496

## Summary
This project builds a movie recommendation system using explicit user ratings. It includes exploratory analysis, collaborative filtering with matrix factorization (ALS), evaluation, and a poster-enriched recommendation showcase using TMDB metadata.

**Model metric:** ALS achieved **RMSE = 0.8768** on a held-out test set.

## Contents
- EDA: rating distribution, user activity, long-tail item popularity, cold-start quantification
- Data cleaning & filtering (e.g., remove movies with < 5 ratings)
- ALS training and evaluation (RMSE)
- Poster enrichment using TMDB (offline script)
- Final showcase output (titles + poster URLs)
- Conclusion and future work

## How to Run
1. Open the Databricks notebook (link above) and run sections in order.
2. Run TMDB enrichment (local / Google Colab) to produce `tmdb_posters.csv`.
3. Upload `tmdb_posters.csv` back to Databricks and join with `links` to construct poster URLs.

## Notes
- Databricks notebook access may require workspace permissions.
- Poster enrichment is separated from modeling due to SQL-only environment constraints.

## Future Work
- Run ALS Top-N inference in an all-purpose Spark environment
- Add ranking metrics: Precision@K / Recall@K / NDCG
- Hyperparameter tuning (rank, regParam)
- Temporal splits and time-aware modeling
