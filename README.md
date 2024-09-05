Movie Recommendation System
This project is a content-based movie recommendation system that suggests similar movies based on metadata like genres, cast, crew, and plot keywords. The system is built using Python and machine learning techniques and works on the TMDb 5000 Movie Dataset.

Table of Contents
Introduction
Dataset
Project Structure
Libraries Used
How the System Works
Usage
Model Explanation
How to Run the Project
Future Enhancements
Introduction
The aim of this project is to build a simple and effective movie recommendation system. It takes a movie title as input and returns a list of similar movies by analyzing metadata features such as genres, plot descriptions, cast, crew, and keywords.

Dataset
We use the TMDb 5000 Movie Dataset which consists of two CSV files:

tmdb_5000_movies.csv - contains information about movies, such as their budget, genres, overview, etc.
tmdb_5000_credits.csv - contains the cast and crew information for each movie.
Both datasets are merged on the title field to form a unified data structure for recommendation.

Project Structure
plaintext
Copy code
├── movie_recommendation_system.ipynb  # Main Jupyter notebook with code
├── tmdb_5000_movies.csv               # Movie metadata dataset
├── tmdb_5000_credits.csv              # Cast and crew dataset
├── similarity.pkl                     # Precomputed similarity matrix
├── movie_list.pkl                     # Movie metadata and tags data
├── README.md                          # Project documentation
Libraries Used
NumPy: For numerical computations
Pandas: For data manipulation
Sklearn: For vectorization and cosine similarity
Ast: To evaluate and handle stringified lists in the dataset
Pickle: For saving the model and similarity matrix
How the System Works
Data Preprocessing:

The movie metadata and cast/crew datasets are merged.
Columns of interest (e.g., genres, keywords, cast, crew) are extracted.
Text data (genres, keywords, cast, crew) is converted from JSON-like format into a list of strings.
Important features are combined into a single column called tags.
Text Vectorization:

The CountVectorizer from scikit-learn is used to convert text data into a matrix of token counts.
We limit the maximum number of features to 5000 and remove stop words in English.
Cosine Similarity:

Cosine similarity is computed between the vectors to determine the similarity between different movies.
The movies with the highest similarity scores to the input movie are recommended.
Usage
To recommend similar movies:

Load the datasets and precomputed models (movie_list.pkl, similarity.pkl).
Call the recommend(movie_title) function with the movie title as input.
The system returns 5 similar movie recommendations based on content.
Example:
python
Copy code
recommend('Gandhi')
Output:

css
Copy code
Gandhi, My Father
The Wind That Shakes the Barley
A Passage to India
Guiana 1838
Ramanujan
Model Explanation
Feature Extraction:

The tags column consists of the movie's overview, genres, keywords, top 3 cast members, and director.
These features provide a comprehensive representation of the movie for comparison with other movies.
CountVectorizer:

Tokenizes the tags and creates a word frequency matrix.
Cosine Similarity:

Measures the angle between two vectors (movies) in a multi-dimensional space.
Movies with similar tags will have higher cosine similarity scores, leading to better recommendations.
How to Run the Project
Prerequisites
Python 3.x
Jupyter Notebook
Necessary libraries (NumPy, Pandas, Scikit-learn, Pickle)
Steps
Clone or download this repository.
Open the Jupyter Notebook movie_recommendation_system.ipynb.
Ensure that the dataset files (tmdb_5000_movies.csv, tmdb_5000_credits.csv) are in the same directory.
Run the notebook cells to preprocess data, build the recommendation system, and test the recommendations.
Use the recommend() function to get movie recommendations.
Pickle Files:
To avoid recomputation:

movie_list.pkl contains the preprocessed data and tags.
similarity.pkl contains the precomputed similarity matrix.
Future Enhancements
Improvement in Feature Weighting: Consider assigning different weights to genres, cast, and crew based on importance.
Hybrid Model: Combine collaborative filtering with content-based filtering for more personalized recommendations.
User Interface: Build a front-end UI for easier interaction.

