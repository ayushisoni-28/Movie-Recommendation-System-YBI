# Movie Recommendation System

This project creates a movie recommendation system using a dataset of movies and their associated features. The system uses text feature extraction and cosine similarity to find and recommend movies similar to a user's favorite movie.

## Requirements

- Python 3.x
- pandas
- numpy
- scikit-learn

You can install the required libraries using pip:

```bash
pip install pandas numpy scikit-learn
```
## Dataset
The dataset is imported from a CSV file located at the following URL:
https://github.com/YBIFoundation/Dataset/raw/main/Movies%20Recommendation.csv

The dataset contains the following columns:

- `Movie_Title`: Title of the movie
- `Movie_Genre`: Genre of the movie
- `Movie_Keywords`: Keywords associated with the movie
- `Movie_Tagline`: Tagline of the movie
- `Movie_Cast`: Main cast of the movie
- `Movie_Director`: Director of the movie

## Feature Selection
The features used for the recommendation are:

- `Movie_Genre`
- `Movie_Keywords`
- `Movie_Tagline`
- `Movie_Cast`
- `Movie_Director`

These features are concatenated into a single string for each movie.

## Text Conversion to Tokens
1. Load the dataset from the CSV file.
2. Select the relevant features (`Movie_Genre`, `Movie_Keywords`, `Movie_Tagline`, `Movie_Cast`, `Movie_Director`) and fill any missing values with empty strings.
3. Concatenate these features into a single string for each movie to create a unified text representation of each movie.
4. Use TF-IDF (Term Frequency-Inverse Document Frequency) vectorization to convert the concatenated text data into tokens (numerical representations).

## Similarity Score Calculation
1. Use cosine similarity to calculate the similarity score between the TF-IDF vectors of the movies.
2. Cosine similarity measures how similar two vectors are, ranging from -1 to 1, where 1 means identical, 0 means no similarity, and -1 means completely opposite.

## Movie Recommendation
1. Prompt the user to input their favorite movie name.
2. Use the `difflib` library to find the closest matching movie title from the dataset.
3. Find the index of the closest match movie in the dataset.
4. Calculate the similarity scores for all movies with respect to the user's favorite movie.
5. Sort the movies based on their similarity scores in descending order to get the most similar movies at the top.

## Display Recommendations
1. Print the top 30 recommended movies based on the similarity scores.
2. Optionally, prompt the user again to input their favorite movie name and display the top 10 recommended movies based on the similarity scores.

## License
This project is licensed under the MIT License.
