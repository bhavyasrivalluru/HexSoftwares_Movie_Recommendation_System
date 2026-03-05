This project builds a Movie Recommendation System using Content-Based Filtering. The system recommends movies that are similar to a given movie based on their genres and descriptions.
The recommendation is generated using Natural Language Processing (NLP) techniques and Cosine Similarity.
1. Data Collection
The project uses a dataset named dataset.csv which contains information about different movies.
The dataset includes features such as: Movie ID, Movie Title, Genre, Movie Overview (description)
These attributes help the system understand the content of each movie.

2. Data Preprocessing
The dataset is loaded using Pandas and basic analysis is performed using functions like: head(), info(), columns
After analyzing the dataset, the genre and overview columns are combined into a new column called tags.
tags = genre + overview
This column represents the important information that describes each movie
A new dataframe is created containing only the required columns: id, title, tags
The unnecessary columns are removed to simplify the dataset.

3. Text Vectorization
The tags column contains text data. To allow machine learning algorithms to process this text, it is converted into numerical form using CountVectorizer from Scikit-learn.
CountVectorizer performs: Tokenization of text, Removal of common English stop words, Conversion of words into numerical vectors
The parameter max_features = 10000 limits the vocabulary size to the most important words.
This step creates a vector representation of each movie.

4. Similarity Calculation
To find similar movies, Cosine Similarity is used.
Cosine similarity measures how similar two movie vectors are based on the angle between them.
The similarity score ranges from:
1 → Highly similar movies
0 → Completely different movies
A similarity matrix is generated where each movie is compared with every other movie.

5. Movie Recommendation
When a user enters a movie title:
The system finds the index of that movie in the dataset.
It retrieves the similarity scores between that movie and all other movies.
The movies are sorted in descending order based on similarity.
The top similar movies are returned as recommendations.
The recommend() function performs this process and prints the top 5 recommended movies.
Example:
recommend("Iron Man")
The system will return movies that are most similar to Iron Man.

6. Recommendation Output
The system outputs a list of recommended movies that have similar genres and story descriptions.
This helps users discover movies they may enjoy based on their preferences.
