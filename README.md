# Movie Recommendation System

A content-based movie recommendation system built using Python. It uses metadata like genres, keywords, cast, tagline, and director to recommend similar movies. 

**This project was developed as part of my internship at Elevate Labs.**

## Features

- Content-based filtering using movie metadata.
- Metadata used: genres, keywords, tagline, cast, and director.
- Missing values handled automatically.
- TF-IDF Vectorization of text features.
- Cosine Similarity to calculate movie closeness.
- Fuzzy string matching to handle typos in user input.
- Returns top 30 similar movies for any given title.

## Tech Stack

- Python
- pandas
- scikit-learn
- difflib
