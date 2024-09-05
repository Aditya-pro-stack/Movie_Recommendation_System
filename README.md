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
