# right-article-right-reader

## Intro:
IBM has been kind enough to share their anonymized user data describing the interactions users have with the library of articles available on the IBM Watson Studio platform.  Our goal is to construct a recommendation system that improves the quality of article recommendations.  

We explore several systems in this experimentation, mostly based on the idea that a user's past interactions are indicative of their future needs.  The first of these is presented in section III where user recommendations are based on the similarity between users based on their article interactions.  The second of these, in section IV, uses a singular value decomposition (SVD) approach to parametrize the space of all users, giving an alternate measure of their similarity.

## Opportunity:

![](https://github.com/manifolded/right-article-right-reader/blob/main/images/movie_database_cartoon.jpg?raw=true)

In section IV we are encouraged to think up our own content-based recommendation system.  I explored using word-frequency vectors to measure the similarity between articles instead of between users.  This analysis was based on using tf-idf scores for each of the word-tokens appearing in the body of the article.  The resulting vectors of tf-idf scores can be compared via a dot product (defined as you would a covariance).  The `TfidfVectorizer` computes these vectors normalized such that these dot products have a peak value of 1.  Scores close to 1 are considered to have an exceptionally high similarity.

Recommending new articles to a user based on the similarity between articles is accomplished by selecting those articles closest to those with which the user has already interacted.

## Reproducing The Analysis

The entire analysis is contained in `Recommendations_with_IBM.ipynb` which you can open using Jupyter and Python 3.8. 

However the data on which that analysis relies is not included in this repo.  You will need to source the `articles_community.csv` and `user-item-interactions.csv` files from IBM or Udacity.  This repo only contains those that represent my own work.

## Acknowledgements
Thanks to IBM for providing the data, and Udacity for introducing me to the techniques. Cheers.


