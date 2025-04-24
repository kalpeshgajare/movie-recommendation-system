# **KNN based Movie Recommendation System**

This project implements a **Movie Recommendation System** using **Collaborative Filtering** with **Cosine Similarity**. While the current implementation is content-based, this README also outlines how collaborative filtering could be incorporated in the future.

## What is a Recommendation System?

A **Recommendation System** suggests items (like movies) to users based on various signals. There are mainly two types:
**Collaborative Filtering**:
   - Recommends movies based on **user preferences**. If User A and User B liked similar movies, a movie liked by A may be recommended to B.
   - Often implemented using user-item matrices and similarity scores (like cosine similarity).

## Algorithms Used

### ✔️KNN algorihtm
- Uses user-item rating matrix to:
- Find nearest users or items
- Recommend based on rating patterns from similar users
- Employs K-Nearest Neighbors algorithm for similarity lookup

### ✔️ Cosine Similarity

Cosine similarity is a metric used to measure how similar two items are, by comparing the angle between two vectors.
Refer [cosine similarity](https://naomy-gomes.medium.com/the-cosine-similarity-and-its-use-in-recommendation-systems-cb2ebd811ce1) for more

## 📂 Project Structure

- `Movie_Recommendation_System_Project.ipynb`: Jupyter notebook with the complete implementation.
- `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`: Datasets sourced from [Kaggle](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata).

## Features

- Merges and cleans movie metadata.
- Extracts key features: cast, crew, keywords, genres, and overview.
- Uses NLP techniques like tokenization and stemming.
- Computes similarity using the **cosine similarity** metric.
- Returns top 5 similar movies based on user input.
- Calculates accuracy by evaluating the system using known similar titles.

## How It Works

1. **Data Preprocessing**:
   - Merges two CSV files on `movie_id`.
   - Extracts relevant fields such as cast, crew, genres, keywords, and overview.
   - Cleans and combines features into a single string "tags".

2. **Feature Engineering**:
   - Applies stemming using NLTK's `PorterStemmer`.
   - Vectorizes the combined features using `CountVectorizer`.

3. **Similarity Calculation**:
   - Uses **cosine similarity** on the vectors to determine closeness between movies.
   - Recommends top 5 movies similar to the selected title.

4. **Accuracy Estimation**:
   - Though content-based systems are hard to benchmark like classification models, we estimate performance by manually validating recommendations.
   - **Similarity-based accuracy**: Checked by observing whether recommended movies belong to the same genre or have shared actors/directors as the original input.
   - Average similarity score among top 5 suggestions is used as a proxy metric.
    
Visit [Wiki](https://github.com/kalpeshgajare/movie-recommendation-system/wiki) for more
  
For example:
  
*Input: Inception  
Recommended: Interstellar, The Prestige, The Dark Knight, Memento, The Matrix  
Cosine Similarity Scores: [0.385, 0.362, 0.341, 0.329, 0.298]  
Average Score: ~0.343  
Accuracy: 77.78%*  

## Tech Stack

- Python
- Pandas
- Numpy
- Scikit-learn
- NLTK

---

## How to Run

1. Clone the repo:
 ```bash
 git clone https://github.com/kalpeshgajare/movie-recommendation-system.git
```
2. Run the notebook: Open `Movie_Recommendation_System_Project.ipynb` in Jupyter Notebook or VSCode.

## Contribution

Contributions are welcome! If you’d like to add collaborative filtering, integrate a front-end, or improve the recommendation logic, feel free to fork the repo and submit a pull request.

## 📃 License

This project is licensed under the [License](LICENSE).

