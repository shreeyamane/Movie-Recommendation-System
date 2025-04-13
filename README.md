# Movie-Recommendation-System

Movie Recommendation System

This project is a Movie Recommendation System that combines Collaborative Filtering and Content-Based Filtering techniques to suggest movies to users. The system is built using Python libraries like Surprise and Scikit-learn. It includes features such as predicting movie ratings, generating personalized movie recommendations, and saving the trained model for future use.
Table of Contents

    Project Overview
    Features
    Dataset Used
    Libraries Used
    Installation
    How to Use
    Code Walkthrough
    Outputs
    Future Enhancements

Project Overview

This recommendation system predicts how much a user will like a movie based on historical ratings and suggests top-rated movies that the user hasn't seen yet. It leverages:

    Collaborative Filtering: Using Singular Value Decomposition (SVD) to predict user preferences.
    Content-Based Filtering: Using genres to compute similarities between movies.

Features

    Rating Prediction: Predicts a user's rating for a specific movie.
    Top N Recommendations: Recommends the top N movies for a user.
    Model Persistence: Saves the trained model as a file for reuse.
    Interactive Dataset Handling: Merges movie details with user ratings for a complete dataset.

Dataset Used

The project uses the MovieLens 20M Dataset, which contains:

    Movies: Details like movieId, title, and genres.
    Ratings: User ratings with userId, movieId, and rating.

Libraries Used

    Core Libraries:
        pandas, numpy – Data manipulation and numerical computations.

    Recommendation Libraries:
        Surprise – Collaborative filtering using SVD.
        Scikit-learn – Content-based filtering.

    Visualization (Optional):
        matplotlib, seaborn.

Installation

Clone this repository:

git clone https://github.com/shreeyamane/Movie-Recommendation-System.git

Navigate to the project directory:

cd movie-recommendation-system

Install the required libraries:

pip install -r requirements.txt

Sample requirements.txt:

pandas
numpy
surprise
scikit-learn
matplotlib
seaborn

How to Use

Run the Python Script: Use the following command to execute the script:

python movie_recommendation.py

    Key Functions:
        Predict Rating: Modify user_id and movie_id in the script to predict ratings for specific movies.
        Get Recommendations: Use the recommend_movies() function to generate personalized recommendations.

    Saved Files:
        Trained model: svd_model.pkl
        Processed datasets: movies.csv and ratings.csv.

Code Walkthrough
1. Data Preprocessing

    Movies Dataset:
        Select relevant columns (movieId, title, genres).
        Replace missing values and format genres for processing.

    Ratings Dataset:
        Merge with movies dataset for enriched data.

2. Collaborative Filtering

    Convert the ratings into Surprise's Dataset format.
    Train-Test Split (80%-20%).
    Train the SVD model on the training data.

3. Content-Based Filtering

    Uses TfidfVectorizer to process genres and calculate cosine similarity.

4. Recommendation System

    Filters unrated movies for the user.
    Predicts ratings for these movies.
    Recommends the top N movies based on predicted ratings.

5. Model Persistence

    Saves the trained SVD model as svd_model.pkl for reuse.
