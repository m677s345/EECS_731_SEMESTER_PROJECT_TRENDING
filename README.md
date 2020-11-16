# EECS_731_SEMESTER_PROJECT_TRENDING
This repo serves as the hub for code from this project on analyzing trending YouTube videos. Regression, Clustering, Anomaly detection and Time series forecasting has been performed on the data.

Clustering (Madhumithra SK): Data cleaning was done prior to clustering which involved removing of columns including rating disabled, comments disabled, thumbnail_link, description, title, video_id. The clustering was performed on the data using DBScan and KMeans algorithm. The percentage like, dislike, comment were obtained using the values of likes, dislikes and comments and dividing them by view count. These along with the category ID were used to perform k-means clustering. The optimal value k=4 was obtained from elbow method and Silhoutte coefficient. Four clusters were found in the result. Tag count was obtained by counting the number of tags present in each row for each trending video. Also using the same percentage like, dislike and comment, and tag count instead of category ID, clustering using DB Scan was done. This also resulted in four clusters.

Regression (Emily Mikeska): Random Forest and Gradient Boosting regression models were trained and evaluated on the Time series data. As I discovered, Random Forest was not well suited for the problem of predicting popular categories of videos. Gradient Boosting regression performed better, but could still be improved. Both models predicted the most popular category ID based on the channel ID, view count, number of likes and dislikes, comment count, publish date, and trending date. To improve over the base model, I focused on optimizing the hyperparameters so that the models could be as accurate as possible with the data provided. The training data was spanned August 3, 2020 to mid October 15, 2020 and the test data spanned  from October 15, 2020 to Octoboer 27, 2020. 

Time Series Forecasting (Matt Stalcup): For time series forcasting modeling done on the YouTube trending dataset we first gathered information on tags and titles that could be useful in determining popularity. Using a word cloud to take the most frequently mentioned words in both the titles and tags of trending videos we were able to create a useful visualization of the distribution of tags over the timeframe we studied. We were able to pice together some relationships between tags like two part names and make and model numberd. We took the most popular tags and used them to interface with the google trends API. Google Trends was able to give us time series data for the tag outside of when it was trending. If we were to only use the data in the trending dataset the time series information would be binary in either is it trending or not. Using Trends we are able to see the relative popularity of the searched term over time. The trends data gives us the ability to train a time series forcasting model on the tags. The daily data that we got worked well for the ARMA model that we fit but not so well with the three fold cross validation model simply because there were very few datapoints. To see the model succede we would need to have a longer time frame with more datapoints. When compaired to the real search values for the forcasted popularity of a search term we see a good amount of disagreement in the general trend that is due to another spike in searches because of some additional content popularizing the search. Such annomalies are the target of the anomally detection portion of the project. However, we are able to successfully fit a model to the trends data for the youtube dataset and predict the relatve popularity of the tags.
