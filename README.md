
# Movie Recommendation System (ALS -> Two - Tower -> RAG ChatBot)

**Movie Recommendation:**  

**01_ALS_Baseline**
https://dbc-a83b6333-0c2f.cloud.databricks.com/editor/notebooks/3300119515183161?o=7474643825711867#command/7835941542853496

**02_Two_Tower**
https://dbc-a83b6333-0c2f.cloud.databricks.com/editor/notebooks/2414811799385756?o=7474643825711867#command/5383454029142809

## 🎯 Recommendations Showcase for Target User 198 (Top 10)

| | | | | |
|---|---|---|---|---|
| ![](https://image.tmdb.org/t/p/w500/w9RaPHov8oM5cnzeE27isnFMsvS.jpg) | ![](https://image.tmdb.org/t/p/w500/ea6HPVTlGa0MmtTrPud0UnP9wh.jpg) | ![](https://image.tmdb.org/t/p/w500/kOymD1rChAMykmDVEzJpIh4OYS7.jpg) | ![](https://image.tmdb.org/t/p/w500/cVUDMnskSc01rdbyH0tLATTJUdP.jpg) | ![](https://image.tmdb.org/t/p/w500/v49q7AMR3pB4M762woWB1NYMCLF.jpg) |
| ![](https://image.tmdb.org/t/p/w500/ihWF0uY1xnKqw9YK7ZHNLUZOhcO.jpg) | ![](https://image.tmdb.org/t/p/w500/wZ0l6or5juuVWqDkLEgaghs4f9l.jpg) | ![](https://image.tmdb.org/t/p/w500/9qAy6UWVw44dGrsyKrdEMt5qIUM.jpg) | ![](https://image.tmdb.org/t/p/w500/3Gkb6jm6962ADUPaCBqzz9CTbn9.jpg) | ![](https://image.tmdb.org/t/p/w500/1OCHR9z9k7go669AsShOkTj4CFb.jpg) |

## ❤️ User 198 — Favorite Movies (Top 5)

| | | | | |
|---|---|---|---|---|
| ![](https://image.tmdb.org/t/p/w500/wby9315QzVKdW9BonAefg8jGTTb.jpg) | ![](https://image.tmdb.org/t/p/w500/x2drgoXYZ8484lqyDj7L1CEVR4T.jpg) | ![](https://image.tmdb.org/t/p/w500/vN5B5WgYscRGcQpVhHl6p9DDTP0.jpg) | ![](https://image.tmdb.org/t/p/w500/crzoVQnMzIrRfHtQw0tLBirNfVg.jpg) | ![](https://image.tmdb.org/t/p/w500/kf1Jb1c2JAOqjuzA3H4oDM263uB.jpg) |
| **Favorite 1** | **Favorite 2** | **Favorite 3** | **Favorite 4** | **Favorite 5** |

## Summary
This project implements both a matrix-factorization (ALS) baseline and a neural two-tower recommender trained with BPR to demonstrate different recommendation paradigms.
The ALS project includes exploratory analysis, collaborative filtering with matrix factorization (ALS), evaluation (**Model metric:** ALS achieved **RMSE = 0.8768** on a held-out test set), and a poster-enriched recommendation showcase using TMDB metadata.
The two-tower model is to demonstrate a modern retrieval-oriented recommender architecture. The model learns to rank relevant items higher rather than predict explicit ratings. Training converged steadily (BPR loss ↓ from 0.69 to 0.16 over 10 epochs).


## Contents
- EDA: rating distribution, user activity, long-tail item popularity, cold-start quantification
- Data cleaning & filtering (e.g., remove movies with < 5 ratings)
- ALS training and evaluation (RMSE)
- Poster enrichment using TMDB (offline script)
- Final showcase output (titles + poster URLs)
- Conclusion and future work

## How to Run
1. Open the Databricks notebook (links above) and run sections in order.
2. Run TMDB enrichment (local / Google Colab) to produce `tmdb_posters.csv`(in 01_ALS_Baseline).
3. Upload `tmdb_posters.csv` back to Databricks and join with `links` to construct poster URLs(in 01_ALS_Baseline).

## Notes
- Databricks notebook access may require workspace permissions.
- Poster enrichment is separated from modeling due to SQL-only environment constraints.

## Future Work
- Run ALS Top-N inference in an all-purpose Spark environment
- Add ranking metrics: Precision@K / Recall@K on both models
- Make models comparison
