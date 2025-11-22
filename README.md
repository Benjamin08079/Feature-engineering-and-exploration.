# Feature-engineering-and-exploration.
Feature engineering and exploratory data analysis (EDA) using a real-world subset of the MovieLens dataset. Includes data cleaning, feature creation, and insights that support building recommendation systems.

# Feature Engineering and Exploratory Data Analysis on MovieLens Dataset

This project performs **data preparation**, **feature engineering**, and **exploratory data analysis (EDA)** on a real-world portion of the **MovieLens dataset**, a widely used dataset for research in recommendation systems.  
The goal is to transform raw data into meaningful features, explore patterns in movie and user behavior, and lay the foundation for future recommendation system development.

## Dataset Acknowledgment
This project uses a subset of the MovieLens dataset for educational and research purposes. 
Original data © GroupLens Research, University of Minnesota.

Dataset: https://files.grouplens.org/datasets/movielens/ml-latest-small.zip

### Citation
If using this dataset in academic or research work, please cite:

> F. Maxwell Harper and Joseph A. Konstan. 2015.  
> *The MovieLens Datasets: History and Context.*  
> ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4: 19:1–19:19.  
> https://doi.org/10.1145/2827872

## Tools & Technologies
Python, Pandas, Matplotlib, etc.

## Project Workflow

### ** Step 1: Data Preparation**
- Loaded four MovieLens CSV files:
  - `ratings`
  - `movies`
  - `tags`
  - `links`
- Merged datasets on **movieId** to create a unified DataFrame.
- Converted timestamps into datetime format for time-based analysis.
- Checked for:
  - Missing values  
  - Duplicate rows  

#### Data Cleaning Decisions
- Missing `tag` values → replaced with **"No Tag"**
- Missing `tmdbId` values → replaced with **"Unknown"**
- No duplicate rows were detected.


### **Feature Engineering**
The following engineered features were created to enhance the dataset:

- **release_year** – extracted from movie titles  
- **num_genres** – number of genres assigned to each movie  
- **movie_avg_rating** – overall average rating per movie  
- **movie_rating_count** – total number of ratings a movie received  
- **user_avg_rating** – mean rating given by each user  
- **user_rating_count** – number of movies rated per user  
- **tag_presence_flag** – indicates whether a movie has associated user tags  

These features help uncover trends in user behavior, movie characteristics, and popularity.

### ** Exploratory Data Analysis (EDA)**
EDA was carried out to explore rating distributions, genre trends, user activity levels, and correlations among engineered features.

#### Key Insights
- Most ratings fall between **3.0 and 4.5**, showing generally positive user feedback.
- **Drama, Comedy, and Action** are the most frequent genres.
- **Documentaries and Dramas** receive the highest average ratings.
- A small number of users contribute a large portion of ratings (long-tailed user activity).
- Movies with multiple genres tend to attract more ratings.
- Ratings increased over the years, showing platform growth.

## How This Supports Future Recommendation Systems

### **Collaborative Filtering Benefits**
- `user_avg_rating` helps normalize rating biases.
- `user_rating_count` and `movie_rating_count` help identify active users and popular movies.
- These features strengthen similarity-based recommendations.

### **Content-Based Filtering Benefits**
- `num_genres` captures movie diversity for similarity matching.
- `release_year` helps recommend movies from preferred eras.
- `movie_avg_rating` boosts selection of high-quality titles.

### **Hybrid Systems**
Combining collaborative and content-based features overcomes limitations of both approaches and improves personalization.

## Repository Contents
- `feature_engineering_exploration.ipynb` — full notebook containing all steps  
- `data/` folder (not included in repo if large) containing the CSV files  

## Running the Project
1. Clone the repository  
2. Install dependencies:
```bash
pip install pandas numpy matplotlib seaborn jupyter

## Dataset License Notice
This project uses a subset of the MovieLens dataset.  
The dataset is provided by the GroupLens Research Group at the University of Minnesota  
and is licensed for research and educational purposes.  
This project is non-commercial and does not imply endorsement by GroupLens or the University of Minnesota.

