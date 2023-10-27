# Phase 4 Project: Music Recommendations

### Background
A certain very popular music streaming service has asked me to diversify their recommendation methods. I am working on a new feature that allows listeners to be introduced to new genres that may seem unrelated to the music they usually listen to, but that I think they will enjoy. I analyzed the features of the songs on a playlist and apply K-means clustering to group songs. Finally, I am able to classify any song without a clear genre listed into one of the five broad genres.

My employers provided me with [this](https://www.kaggle.com/datasets/iamsumat/spotify-top-2000s-mega-dataset) dataset comrpised of 15 features and 2000 rows. The 15 columns are what are bein analyzed.

Here is a snippet of the dataset. Note the features at the top and the fact that the "Top Genre" column has unconventional names.
![df](https://github.com/virgiliaantonucci/DS-Phase-4-Project/blob/main/Images/df.png)

I created a balanced dataframe with a Broad Genre column. Songs with a Top Genre that could be parsed into Metal, Rock, Pop, Standards, and Indie were kept and used.
![balaced](https://github.com/virgiliaantonucci/DS-Phase-4-Project/blob/main/Images/balanced.png)

To test the recommendations feature, I created a dataframe with ten random Indie songs as our playlist.
![playlist](https://github.com/virgiliaantonucci/DS-Phase-4-Project/blob/main/Images/playlist.png)

# Modeling
Both the elbow plot using distortion and the elbow plot using variance showed that I should use k=5 for clustering.
![distortion](https://github.com/virgiliaantonucci/DS-Phase-4-Project/blob/main/Images/distortion.png)
![vrc](https://github.com/virgiliaantonucci/DS-Phase-4-Project/blob/main/Images/vrc.png)

Here is a visualization of the songs in the balanced dataframe. You can see how the genres are visible.
![t-SNE](https://github.com/virgiliaantonucci/DS-Phase-4-Project/blob/main/Images/t-SNE.png)

Here are the recommended songs and cosine similarity to show how close they are to the original songs.
![recommended](https://github.com/virgiliaantonucci/DS-Phase-4-Project/blob/main/Images/recommended.png)

# Evaluation
If a song is added to the streaming site that does not have an easily parsable To Genre, it will get sorted into Broad Genre using its features.
The highest accuracy I was able to achieve was 0.5789 using a hypertuned Random Forest.

# Recommendations and Next Steps
A larger dataset is required. It would improve accuracy for each Broad Genre as well as allow for more genres to be added to Broad Genre.