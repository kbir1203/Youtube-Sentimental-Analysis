# Youtube-Sentiment-Analysis
Working:

The user enters the url of the youtube video,whose 'average sentiment' has to be determined.
'Cleaning' of the url string is done to obtain the 'video_id' of the video.
The video_id is then given as an input to Google's v3 API, which is used to fetch 100 'most relevant' (Youtube has its own algorithm to determine whether a comment is 'relevant' or not) comments on the youtube video whose url has been given by the user.
Once the comments are fetched, they are appended to a dataframe using pandas library.
Then, all the comments are cleaned (e.g. any 'mention' or a 'link' is replaced by '@' or 'http-link' respectively).
After this, each comment is fed into the NLTK (Natural Language Toolkit) library's 'SentimentIntensityAnalyzer' method, which gives us the 'compound polarity score'. The compound polarity score or 'sentiment score' ranges from -1 to +1, the higher the 'sentiment score' the positive the comment is.
After receiving the sentiment score of all comment, "average sentiment score" is calculated.
This, 'average sentiment score' is then binned into one of the nine categories (in ascending of the sentiment score): 'Extremely Negative' (very close to -1), 'Very Negative', 'Negative', 'Neutral-Negative', 'Neutral', 'Neutral-Positive', 'Positive', 'Very Positive' and 'Extremely Positive' (close to +1). Now, the final sentiment along with the 'Average sentiment score' is returned and displayed to the user.
Time taken to process one request (processing top 100 relevant comment and returning final sentiment and average sentiment score) is around 2 seconds to 5 seconds.
