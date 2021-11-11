# Recommendation Systems: Netflix Vs. Spotify 

Goal: Trying to replicate one of the features of Netflix and Spotify Recommendation Systems using Python and understand possible recommendation methods on different types of data.

# Netflix Recommendation System:
Netflix uses a variety of ways to recommend movies to its users. One of them is collaborative filtering using matrix factorization which identifies similar users and recommends content based on their behavior.
 
 **Dataset**: http://files.grouplens.org/datasets/movielens/ml-latest-small.zip

 1. The movies dataset contains the movieId and its genre and the rating dataset contains movieId and its respective rating given by any userId.
 2. We consider the movies which are already rated by users for recommendation
 3. For content-based recommendations, we combine the tags dataset and movies dataset and run matrix factorization using svd on top of it.
 4. For collaborative recommendations, we create a pivot of users and ratings and generate latent vectors on top of it
 5. For any movie, we find the cosine similarity with the rest of the movies in the dataset and return the top 10 recommendations

# Spotify Recommendation System:
One of the recommendation methods which is used by Spotify is converting raw audio data into embeddings which can then be processed using a classification algorithm to make recommendations.
 
 **Dataset**: http://storage.googleapis.com/us_audioset/youtube_corpus/v1/features/features.tar.gz

 1. demo_modify.ipynb converts .wav files to vector embeddings. It is part of IBM’s MAX audio converter package.
 2. Alternatively, there is an Audioset of already converted youtube videos which can be downloaded from the above link.
 3. Once the dataset is ready, we need to ensure we take only the audio which contains music and avoid other sounds.
 4. Then we trim the audio to only 10 seconds and store it in a json file.
 5. After preprocessing is over, we use approximate nearest neighbor algorithm(ANNOY) to return a list of audio samples for any input audio sample.
