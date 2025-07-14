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

---

## Usage

1. Ensure your movie dataset (e.g., `movies.csv`) is placed in the project directory.

2. Run the Python script:

```bash
python movie_recommendation_system.py

