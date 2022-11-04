# TweetAMovie-Dataset

## Summary 

Metric | Value
--- | ---
Number of unique movies                 | 6041
Number of rating                       | 6015
Minimum rating value                    | 0.0
Maximum rating value                    | 10.0
Number of genres                    | 23
Release year range                       | 1946-2021
Minimum votes value      | 218
Maximum votes value      | 2164069
Minimum number of genre/movie | 1
Maximum number of genre/movie | 3
Number of tweets | 368726
Number of well-structured tweets | 4370
Number of unstructured tweets | 364356
Language     | English

## Data Collection Process 

TweetAMovie is a new movie rating and temporal popularity dataset from IMDb and Twitter. This dataset contains 6015 average ratings ranging between 1 and 9.4 on 6041 movies and 23 genres. Each movie belongs to at least one genre and at most three genres. We collected the most popular movie list for six weeks. In total, TweetAMovie includes 368726 English tweets composed of 4370 well-structured tweets and 364356 unstructured tweets. Our dataset comprises three files: MovieReg.csv, MovieTPop.csv, and Tweets.csv, which store movie regular features, temporal popularity of movies, and tweets-related features. We adopted an IMDb identifier as a movie id to facilitate additional metadata enrichment.

This dataset is the result of research conducted by [Bushra Alhijawi](https://scholar.google.com/citations?user=uvyM6rwAAAAJ&hl=ar) and has been presented in the Sixth International Congress on Information and Communication Technology. Kindly cite the [corresponding paper](https://link.springer.com/chapter/10.1007/978-981-16-2377-6_12) if you make use of this dataset. 

Bibtex: *@inproceedings{alhijawi2022prediction,
  title={Prediction of Movie Success using Twitter Temporal Mining},
  author={Alhijawi, Bushra and Awajan, Arafat},
  booktitle={Proceedings of Sixth International Congress on Information and Communication Technology},
  pages={105--116},
  year={2022},
  organization={Springer}
}*

## MovieReg.csv

MovieReg.csv is collected from IMDb on 2/12/2019. This file contains information about movies, including Movie Id (tconst), Movie Title (primaryTitle), Release Year (releaseYear), Average Rating (rating), Number of Votes (numVotes), and Genres (genre).

## MovieTPop.csv

MovieTPop.csv stores the Top-100 popular movie data. We collected the Top-100 popular movie list, which is weekly updated within the period 2/12/2019 and 13/1/2020. Each row in this file after the header row represents one movie, and has the following
format:
- Movie Id (tconst).
- Top-100 Movie list on 2/12/2019 (p1).
- Top-100 Movie list on 16/12/2019 (p2).
- Top-100 Movie list on 23/12/2019 (p3).
- Top-100 Movie list on 30/12/2019 (p4).
- Top-100 Movie list on 6/1/2020 (p5).
- Top-100 Movie list on 13/1/2020 (p6).

## Tweets.csv

The data stored in Tweets.csv are collected from Twitter. TweetAMovie includes well-structured and unstructured tweets. 
- The structured tweets were obtained by querying a series of regular expressions, including "I rated" and hashtag "#IMDb" (e.g., "I rated Fast & Furious Presents: Hobbs & Shaw (2019) 8/10 #IMDb"). 
- The unstructured tweets are extracted by querying the movie title. 
We faced a challenge when the movie title consisted of words that may be used in several contexts in which unrelated tweets are retrieved. For example, for the movie "They Live" we obtained the tweet "they said this? IN 2020???? what universe do they live in???", which is unrelated to the movie. Therefore, we validated the tweet using [IBM Watson Natural Language Understanding (IBM-W-NLU)](https://www.ibm.com/cloud/watson-natural-language-understanding) service by extracting its category to ensure that the TweetAMovie dataset includes only movie-related tweets.

Each row in this file after the header row represents one tweet, and has the following format:
- Movie Id (tconst).
- Tweet Id (tweetID).
- Tweet text (tweet).
- Number of retweets (retweets).
- Number of favorites (favorites).
- Number of replies (replies).
- Posting Time (time).
- Hashtags included in the Tweet (hashtags).
- Sentiment score of the Tweet (SentimentScore).
- Sentiment label of the Tweet (label).

## Use Cases 

TweetAMovie dataset can be used to develop techniques for different applications such as: 
- Recommender system.
- Review-based rating prediction.
- Popularity prediction.
- Temporal popularity prediction.
- Sentiment Analysis.

<!--## Publications using TweetAMovie
- [Prediction of Movie Success using Twitter Temporal Mining] (https://link.springer.com/chapter/10.1007/978-981-16-2377-6_12)-->

