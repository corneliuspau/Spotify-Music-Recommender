# Building a Spotify Music Recommender

## Basic Overview
Music is an essential part of the college experience. Being the decicated person in charge of DJ-ing for parties, finding the right songs to play is crucial in setting the tone for the night. As a result, it is difficult to gauge what songs our group of friends want to hear. To solve this problem, we built a machine learning model that could predict what songs our friends would like. 

## Data Preparation
We made a collaborative Spotify playlist in which our friends added all their favorite songs that they would want to hear at a party. These songs are labelled as "good songs". 

![good_songs](https://i.imgur.com/yDSHDTB.png)

We then made another playlist for "bad songs" which represent songs that we wouldn't play at a party. The purpose of labelling a song as "good" or "bad" is so that the model can learn to classify between the two based on their respective features (more on this later). 

![bad_songs](https://i.imgur.com/a3X5DaP.png)

We then used Spotipy's API to extract these songs and their corresponding features and combined them into a Pandas dataframe. Spotipy is a python library for Spotify's Web API, which gives us easy access to extract music data provided by Spotify. The dataframe is a 1735 x 18 matrix that whereby each row displays an individual song and the columns show each feature.

## Spotify Song Features
Spotify's Developer Platform allows us access to each song's metadata (or audio features). These features include danceability, energy, loudness, key, and more. Each of the features are represented in a numerical format with varying values. For example, a song with a danceability of 0.735 would indicate that the song is highly danceable based on a combination of musical elements. These features gives us key information that we can use in predicting new songs that would be suitable for the party playlist.

Official documentation: https://developer.spotify.com/documentation/web-api/reference/tracks/get-audio-features/

## Goal of the project
We want to train a model with the datasets we extracted to accurately recommend new songs for us to use at parties. We decided to test these 4 classifiers to determine which one is the most optimal for our model: 

- K Nearest Neighbors Classifier
- Random Forest Classifier
- Decision Tree Classifier
- Logistic Regression 

![prediction_dataframe](https://i.imgur.com/GNpJnzp.png)

The classifiers listed above are all classification algorithms that could determine a predictive binary outcome. We decided to use the Random Forest Classifier as our model for the final prediction since it had the highest testing accuracy of 91%.

## Conclusion
To put our model to use, we compiled a playlist of songs named TESTING that we think our friends would like. Obviously, we all have different taste in music, and so we hope this model could help us accurately determine what the right songs are.



![prediction_dataframe](https://i.imgur.com/8V8r2ZQ.png)



The end result is a dataframe of all the songs from TESTING that includes a column named "prediction" which returns a binary value where 1 means the song is recommended, and 0 if not. Creating this model allowed us to save time that would otherwise be spent on manually listening to each song and determining the right songs ourselves. However, music is incredibly subjetive and cannot always be measured in a quantifiable manner. We understand that the emotions and life depicted in music is much more complicated than mere numbers on a scale, but after listening to the recommended songs, we can confidently say that it fared up to our expecations. It may not be perfect, but it improved our quality of life by reducing the amount of time spent looking for songs without sacrificing music quality.




