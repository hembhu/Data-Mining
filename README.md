# Data-Mining
Spotify Songs Analysis

BACKGROUND:
Spotify is a digital music service that enables users to remotely source millions of different songs and podcasts on various record labels from a laptop, smartphone, or another device. Spotify also assigns each song a popularity score, based on the total number of clicks/listens. Predicting the popularity of the song should be a challenge and interesting topic in nowadays music field. Songs characteristic could be separated into 12 factors, which could be used for predicting the popularity of a specific song. For instance, songs' loudness or liveness could be an important effective factor for the popularity of the new song. The product manager or artist could use the factors to compose a song that fit the popular trend in that year.

THE PROBLEM:
Predicting the popularity of a song based on its characteristics could be interesting and challenge in the modern music field. Song Writers and Product Managers could use the model to predict the popularity of a new song based on its features, for instance, the acoustics could be a significant factor that affects the popularity of the song in 2018; therefore, the artists could add or reduce the acoustic elements when he or she composed the songs.

GOAL:
Building a model to successfully predict the popularity of a song based on its specific factors. Consumers can use the power of analytics to segregate songs into broader genres or categories based on the popularity or recommendations which may not belong to the same genre but have similar features that can be used to make custom playlists for the customer in his/her local machine. Recommendations for new songs from different genres/languages which have similar features such as danceability, energy, valence, etc can be made to a user depending on their listening history and preferences.

SOLUTION:
In this case, I have  proposed a solution that used the data mining techs, such as (K-Nearest Neighbor)KNN, Multilinear Regression, Random Forest, Support Vector Machines, as well as Neural Net, to build a model to predict the popularity of a song. Meanwhile, a dimension reduction method, Principal Component Analysis (PCA), had been implemented for comparing the result from the original dataset. The model is estimated via accuracy and robustness using Lift Charts and RMSE.

DATA DESCRIPTION: 
The dataset was gained from Kaggle website, named “Spotify Dataset 1921-2020, 160k+ Tracks.” The dataset file contains more than 170.000 songs collected from Spotify Web API, and also the songs were grouped by artist, year, or genre in the data section. The datasets was updated recently by Yamaç Eren Ay, the last updated time is 2020- 11-25. In this case, we select the year 2018 dataset as our case study analyzing data source.  

VARIABLE SELECTION:
Since the dataset did not contain many correlated attributes, we select 12 factors as the input variables, except the variable explicit. The reason why I did not select this variable is that from developer spotify.com we cannot find the exact definition of the factor. Therefore, Popularity was selected as the output variable, the input variables contain acousticness, danceability, instrumentalness, speechiness, liveness, energy, loudness, valence, duration_ms, tempo, key, mode.

PREPROCESSING AND DIMENTIONALITY REDUCTION

DATA CLEAN UP:
We clean up the dataset by analyzing the histogram and box plots. The original dataset’s popularity column has few data points that the popularity is equal to 0, which is much far away from the mean value from the histogram plot and box plot. It means that these points are not the real situation since the popularity of the song could not be 0 (just a thought, maybe the 0 means the song is not been published.) Therefore, we deleted these data points and make the dataset into 2000 rows and 13 columns.
After that,  PCA analysis was used  to reduce the dimension into 4 PCA factors, which captured 53.6% percent variance. The number of component (4) were selected via parallel analysis and scree plot.

RECOMMENDATION
*From the model results, the Random Forest performed best in the case since it has the smallest RMSE for the prediction model.
*Comparatively, the Neural Net and SVM performed not so well in this case. The reason this phenomenon happens is the poor feature selection. 
*Moreover, from the Lift Charts results, we could see all the model performance is not so well in this case. The reason here could be the factor selection is not as good as we thought. The factors like loudness, liveness, etc., not enough for predicting the song’s popularity.
*The poor performance for each model could be fixed and improved by adding more reasonable factors, for instance, the popularity of the composers’ as well as the singers’ reputation could be a significant effect of the popularity of a song. After optimizing the input variables, the model performance could be different.
*For further analysis, besides operating the input variables, another thing that needs to do is to change the popularity from a numerical variable into a dummy variable, like setting up a cutoff value of 66(mean of the popularity) for separating the song is popular or not. And using that as a factor to make the model for a recommendation songs model.
