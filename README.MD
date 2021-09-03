# Building a Spotify Music Recommender

## Basic Overview
Music is an essential part of the college experience. Being the decicated person in charge of Djing for parties, finding the right songs to play is crucial in setting the tone for the night. As a result, it is difficult to gauge what songs our group of friends want to hear. To solve this problem, we built a machine learning model that could predict what songs our friends would like. 

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
We want to train a model with the datasets we extracted to accurately recommend new songs for us to use at parties. We decided to test these 4 classifiers to determine which is the one is the most optimal for our model: 
- SVM 
- Random Forest Classifier
- Decision Tree Classifier
- Logistic Regression 

## Conclusion
We ended up using RandomForestClassifier because it had the highest testing accuracy of ~85%





