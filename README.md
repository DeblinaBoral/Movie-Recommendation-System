# Movie Recommendation System

This project is a **Content-Based Movie Recommendation System** built using Python. It uses metadata such as genres, keywords, tagline, cast, and director to recommend similar movies based on a given title. The system applies TF-IDF vectorization and cosine similarity to compute recommendations.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Example](#example)
- [Dependencies](#dependencies)
- [License](#license)

---

## Overview

A content-based recommendation system suggests movies similar to the one the user likes by analyzing textual metadata. This project demonstrates how to preprocess text features, vectorize them, compute similarity, and generate recommendations in real time using Python.

---

## Features

- Uses metadata: `genres`, `keywords`, `tagline`, `cast`, `director`
- Cleans and preprocesses missing or null values
- Combines metadata into a unified text format
- Applies TF-IDF Vectorization for feature extraction
- Uses Cosine Similarity to compute closeness between movie descriptions
- Handles fuzzy string matching to accept flexible user input
- Recommends top 10 most similar movies

---

## Installation

Clone the repository and install required packages:

```bash
git clone https://github.com/your-username/movie-recommendation-system.git
cd movie-recommendation-system
pip install -r requirements.txt

Usage
Ensure your movie dataset (e.g., movies.csv) is placed in the project directory.

Run the Python script:

python recommend.py
Enter a movie name when prompted:


Enter your favorite movie: Iron Man 2
Get a list of similar movie recommendations.

How It Works
1. Load Dataset
import pandas as pd
df = pd.read_csv('movies.csv')
2. Select Metadata Features
features = ['genres', 'keywords', 'tagline', 'cast', 'director']
for feature in features:
    df[feature] = df[feature].fillna('')
3. Combine Features into a Single String
def combine_features(row):
    return ' '.join(row[feature] for feature in features)

df['combined'] = df.apply(combine_features, axis=1)
4. Vectorize Using TF-IDF
from sklearn.feature_extraction.text import TfidfVectorizer
vectorizer = TfidfVectorizer()
tfidf_matrix = vectorizer.fit_transform(df['combined'])
5. Compute Cosine Similarity
from sklearn.metrics.pairwise import cosine_similarity
similarity = cosine_similarity(tfidf_matrix)
6. Get Movie Recommendation
import difflib
movie_titles = df['title'].tolist()
movie_input = input("Enter your favorite movie: ")
matches = difflib.get_close_matches(movie_input, movie_titles)
chosen_movie = matches[0]

index = df[df['title'] == chosen_movie].index[0]
similarity_scores = list(enumerate(similarity[index]))
sorted_scores = sorted(similarity_scores, key=lambda x: x[1], reverse=True)

print("Top 30 recommendations:")
for i in range(1, 31):
    print(df['title'][sorted_scores[i][0]])
Example
Input:
Enter your favorite movie: Iron Man 2
Output:
Top 10 recommendations:
Iron Man
Iron Man 3
The Avengers
Avengers: Age of Ultron
...

scikit-learn

Install them using:

pip install pandas scikit-learn

License
This project is licensed under the MIT License. See the LICENSE file for details.
