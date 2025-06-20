MovieLens Movie Recommendation System

Overview

This project builds a personalized movie recommendation system using the MovieLens 100K dataset from the GroupLens research lab. It employs collaborative and hybrid filtering to recommend the Top 5 movies per user, aiming to boost engagement on streaming platforms.

Business Context

Streaming platforms face user overwhelm due to vast content libraries, leading to reduced watch time and churn. This system delivers personalized recommendations to enhance user satisfaction and retention.

Key Questions





Can user rating patterns predict future preferences?



Does model-based (SVD) or memory-based (KNN) collaborative filtering perform better?



Can the system generate high-quality Top 5 recommendations?

Dataset

The MovieLens 100K dataset includes:





ratings.csv: 100,836 ratings (userId, movieId, rating (0.5–5.0), timestamp).



movies.csv: 9,742 movies, with movieId, title, and genres.

Filtered to users with ≥20 ratings and movies with ≥50 ratings, yielding 41,360 ratings.

Methods

Data Preprocessing





Loaded and cleaned datasets (no missing values, no duplicates, valid ratings).



Filtered active users and popular movies.



Converted timestamps to datetime; split ; split genresintolists.

Exploratory Analysis





Found users favor highly-rated movies in Drama, Comedy, and Thriller genres.



Active users and popular movies provide strong signals for recommendations.

Modeling





Collaborative Filtering:





SVD: Model-based, using Singular Value Decomposition.



KNNBasic: Memory-based, using cosine similarity.



SVD outperformed KNNBasic (RMSE: 0.8368 vs. 0.8844; MAE: 0.6395 vs. 0.6753).



Hybrid Filtering:





Combined SVD with genre-based cosine similarity.



Addressed cold-start issues for new users.



Blended scores with alpha=0.7 (70% CF, 30% content-based).

Recommendations





Generated Top 5 recommendations using SVD and hybrid models.



Hybrid example for User 1: Shawshank Redemption (1994), Dr. Strangelove (1964), Godfather (1972), Graduate (1967), Cool Hand Luke (1967).



Hybrid model added diversity (e.g., North by Northwest).

Results





SVD offers accurate, scalable recommendations.



Hybrid filtering improves diversity and handles cold-start users.



System aligns recommendations with user preferences.




Conclusion

The system combines collaborative and hybrid filtering to deliver personalized movie recommendations, addressing user engagement challenges effectively.
