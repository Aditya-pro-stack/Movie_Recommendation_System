# Movie Recommendation System

This project is a content-based movie recommendation system that suggests similar movies based on metadata like genres, cast, crew, and plot keywords. The system is built using Python and machine learning techniques and works on the TMDb 5000 Movie Dataset.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Libraries Used](#libraries-used)
- [How the System Works](#how-the-system-works)
- [Usage](#usage)
- [Model Explanation](#model-explanation)
- [How to Run the Project](#how-to-run-the-project)
- [Future Enhancements](#future-enhancements)

## Introduction

The aim of this project is to build a simple and effective movie recommendation system. It takes a movie title as input and returns a list of similar movies by analyzing metadata features such as genres, plot descriptions, cast, crew, and keywords.

## Dataset

We use the TMDb 5000 Movie Dataset which consists of two CSV files:
- `tmdb_5000_movies.csv`: contains information about movies, such as their budget, genres, overview, etc.
- `tmdb_5000_credits.csv`: contains the cast and crew information for each movie.

Both datasets are merged on the title field to form a unified data structure for recommendation.

## Project Structure
├── movie_recommendation_system.ipynb # Main Jupyter notebook with code ├── tmdb_5000_movies.csv # Movie metadata dataset ├── tmdb_5000_credits.csv # Cast and crew dataset ├── similarity.pkl # Precomputed similarity matrix ├── movie_list.pkl # Movie metadata and tags data ├── README.md # Project documentation

## Libraries Used

- **NumPy**: For numerical computations
- **Pandas**: For data manipulation
- **Sklearn**: For vectorization and cosine similarity
- **Ast**: To evaluate and handle stringified lists in the dataset
- **Pickle**: For saving the model and similarity matrix

## How the System Works

### Data Preprocessing:
- The movie metadata and cast/crew datasets are merged.
- Columns of interest (e.g., genres, keywords, cast, crew) are extracted.
- Text data (genres, keywords, cast, crew) is converted from JSON-like format into a list of strings.
- Important features are combined into a single column called `tags`.

### Text Vectorization:
- The `CountVectorizer` from scikit-learn is used to convert text data into a matrix of token counts.
- The maximum number of features is limited to 5000, and English stop words are removed.

### Cosine Similarity:
- Cosine similarity is computed between the vectors to determine the similarity between different movies.
- The movies with the highest similarity scores to the input movie are recommended.

## Usage

To recommend similar movies:
1. Load the datasets and precomputed models (`movie_list.pkl`, `similarity.pkl`).
2. Call the `recommend(movie_title)` function with the movie title as input.
3. The system returns 5 similar movie recommendations based on content.

### Example:
```python
recommend('Gandhi')
