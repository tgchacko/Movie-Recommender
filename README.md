# Movie-Recommender

## Table of Contents

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[Data Description](#data-description)

[Tools](#tools)

[EDA Steps](#eda-steps)

[Data Preprocessing Steps and Inspiration](#data-preprocessing-steps-and-inspiration)

[Recommendation Techniques](#recommendation-techniques)

[Assumptions](#assumptions)

[Evaluation Metrics](#model-evaluation-metrics)

[Results](#results)

[Recommendations](#recommendations)

[Limitations](#limitations)

[Future Possibilities of the Project](#future-possibilities-of-the-project)

[References](#references)


### Project Overview

This project involves creating a movie recommender system using various recommendation algorithms. The system includes simple recommenders, content-based filtering, and collaborative filtering techniques to provide movie recommendations.

### Data Sources

The project utilizes two datasets:
1.	**[Ratings Dataset (ratings_small.csv)](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset)**: Contains user ratings for collaborative filtering.
- Entries: 100,004
- Columns: userId, movieId, rating
2.	**Movie Metadata and Credits Datasets**: Contains movie metadata and credits for content-based and simple recommenders.
- [tmdb_5000_movies.csv](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)
- [tmdb_5000_credits.csv](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)


### Data Description

#### Ratings Dataset

- userId: Unique identifier for each user.
- movieId: Unique identifier for each movie.
- rating: Rating given by the user to the movie.

#### Movies Dataset

- budget: Budget of the movie.
- genres: List of genres associated with the movie.
- homepage: URL of the movie's homepage.
- id: Unique identifier for each movie.
- keywords: Keywords related to the movie.
- original_language: Original language of the movie.
- original_title: Original title of the movie.
- overview: Brief description of the movie plot.
- popularity: Popularity score of the movie.
- production_companies: Production companies involved in making the movie.
- production_countries: Countries where the movie was produced.
- release_date: Release date of the movie.
- revenue: Revenue generated by the movie.
- runtime: Duration of the movie.
- spoken_languages: Languages spoken in the movie.
- status: Release status of the movie.
- tagline: Tagline of the movie.
- title: Title of the movie.
- vote_average: Average rating of the movie.
- vote_count: Number of votes received by the movie.

#### Credits Dataset

- movie_id: Unique identifier for each movie.
- title: Title of the movie.
- cast: List of main cast members.
- crew: List of crew members.

### Tools

- Python: Data Cleaning and Analysis

    [Download Python](https://www.python.org/downloads/)

- Jupyter Notebook: For interactive data analysis and visualization

    [Install Jupyter](https://jupyter.org/install)
 
**Libraries**

Below are the links for details and commands (if required) to install the necessary Python packages:

Below are the links for details and commands (if required) to install the necessary Python packages:
- **pandas**: Go to [Pandas Installation](https://pypi.org/project/pandas/) or use command: `pip install pandas`
- **numpy**: Go to [NumPy Installation](https://pypi.org/project/numpy/) or use command: `pip install numpy`
- **matplotlib**: Go to [Matplotlib Installation](https://pypi.org/project/matplotlib/) or use command: `pip install matplotlib`
- **seaborn**: Go to [Seaborn Installation](https://pypi.org/project/seaborn/) or use command: `pip install seaborn`
- **scikit-learn**: Go to [Scikit-Learn Installation](https://pypi.org/project/scikit-learn/) or use command: `pip install scikit-learn`
- **surprise**: Go to [Surprise Installation](https://pypi.org/project/scikit-surprise/) or use command: pip install scikit-surprise`

### EDA Steps

- Data loading and initial exploration
- Data cleaning and manipulation
- Checking for missing values and duplicates
- Merging the movies and credits datasets

### Data Preprocessing Steps and Inspiration

- **Handling Missing Values**: Identified and handled missing values in the dataset.
- **Merging Datasets**: Merged the movies and credits datasets on the id column.
- **Feature Extraction**: Extracted relevant features such as cast, crew, genres, and overview for content-based filtering.
- **Creating Weighted Ratings**: Calculated weighted ratings for movies using the IMDB formula.

### Recommendation Techniques

- **Simple Recommender - IMDB Weighted Rating**: Uses a formula to calculate weighted ratings based on average rating, number of votes, and a minimum vote threshold.

- **Simple Recommender - Trending Movies**: Recommends trending movies based on popularity.

- **Content-Based Filtering**:
1) **Overview Based**: Recommends movies based on plot similarity using TF-IDF and cosine similarity. TF-IDF (Term Frequency-Inverse Document Frequency) is a statistical measure used to evaluate the importance of a word in a document relative to a collection of documents.
2) **Credits, Genres, and Keywords Based**: Recommends movies based on similarity in cast, crew, genres, and keywords using CountVectorizer and cosine similarity. Count Vectorize converts a collection of text documents to a matrix of token counts, helping in text analysis and feature extraction.

- **Collaborative Filtering**: Singular Value Decomposition (SVD): Uses matrix factorization to predict user ratings for movies based on past user ratings.

### Assumptions

- Ratings provided by users are reliable.
- User preferences are consistent over time.
- Movies with higher ratings are preferred by users.

### Evaluation Metrics for SVD

- **MAE (Mean Absolute Error)**: Measures the average magnitude of errors in a set of predictions, without considering their direction.
- **RMSE (Root Mean Squared Error)**: Measures the square root of the average squared differences between predicted and observed values.

### Results

### For IMDB Dataset:

#### Simple Recommender - IMDB Weighted Rating

**Findings: Weighted ratings calculated using IMDB formula, top 20 movies sorted by score.**

![Results](https://i.postimg.cc/sfHT6h4v/Screenshot-2024-05-27-at-18-48-24-movie-recommender-Jupyter-Notebook.png)

#### Simple Recommender - Trending Movies:

**Findings: Top 10 movies sorted by popularity.**

![Results](https://i.postimg.cc/fbx9d6Bx/Screenshot-2024-05-27-at-18-50-24-movie-recommender-Jupyter-Notebook.png)

#### Content-Based Filtering - Overview Based

**Findings: Recommends movies based on plot similarity using TF-IDF and cosine similarity.**

![Results](https://i.postimg.cc/ZnqHVTQk/Screenshot-2024-05-27-at-18-52-37-movie-recommender-Jupyter-Notebook.png)

#### Content-Based Filtering - Credits, Genres, and Keywords Based

**Findings: Recommends movies based on similarity in cast, crew, genres, and keywords using CountVectorizer and cosine similarity.**

![Results](https://i.postimg.cc/2SCQwjL0/Screenshot-2024-05-27-at-18-53-40-movie-recommender-Jupyter-Notebook.png)

### For Ratings Dataset:

#### Collaborative Filtering - SVD
**Findings: Predicted user ratings for movies using SVD with evaluation metrics MAE and RMSE.** 

![Results](https://i.postimg.cc/yNyYTB9y/Screenshot-2024-05-27-at-18-56-59-movie-recommender-Jupyter-Notebook.png)

**Findings: Top 10 recommended movies for a given user(Example - user 1)**

![Results](https://i.postimg.cc/1Rj7Jjpk/Screenshot-2024-05-27-at-18-58-42-movie-recommender-Jupyter-Notebook.png)

### Recommendations

- Further data collection and feature engineering could improve the recommendation accuracy.
- Regularly updating the model with new movie data can help maintain recommendation relevance.
- Implementing user feedback mechanisms to continuously improve recommendations.

### Limitations

- The dataset may contain biases that could affect the recommendations.
- The recommendation performance is limited by the quality and quantity of the available data.


### Future Possibilities of the Project

- Exploring additional recommendation algorithms and ensemble methods.
- Implementing deep learning models for better performance.
- Developing real-time recommendation systems based on user interactions.

### References

- [Scikit-learn documentation](https://scikit-learn.org/stable/)
- [Surprise documentation](https://pypi.org/project/scikit-surprise/)
- [Recommender Systems by Charu C. Aggarwal](http://pzs.dstu.dp.ua/DataMining/recom/bibl/1aggarwal_c_c_recommender_systems_the_textbook.pdf)
