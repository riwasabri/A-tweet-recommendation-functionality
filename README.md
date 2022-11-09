# NLP
For full presentation, click [here].(https://github.com/riwasabri/NLP/blob/master/NLP-%20Presentation%20.pdf)

## **Design** 


In the current Twitter UI, when a user clicks on a tweet Twitter recommends 'Relevant People'. This 
consists of the author of the tweet and anyone mentionned in the tweet, see below. 
![NLP- Presentation 1](https://user-images.githubusercontent.com/31965719/200192546-d1696051-8d06-434b-b76f-d02a7b2891d6.jpeg)

The goal of this project is to use NLP to create a tweet recommendation system that
would recommend 2-3 similar tweets to a given tweet. This would allow users to
explore relevant tweets, expanding reach beyond the tweet and its author.

## **Data**

The data is collected using sns scrape. I collected data for two distinct topics:
nightmares and caviar delivery app customer complaints.

Each dataset is 1000+ rows and each consists of a tweet and its corresponding
information (number of likes, user id,etc…). 

For the purpose of this project only the tweet field is used to focus on NLP.

## **Algorithm**

**Cleaning & Pre-Processing:**
* Removed Hyperlinks, Non alpha characters, hashtags (most of them were
stopwords), emojis (none were really informative when it came to the tweet),
mentions.

**Dimensionality Reduction**

Tested out several vectorizers combines with Dimensionality Reduction techniques and
determined which one the use based on recommendations outputs for each:

* Different vectorizers: CountVectorizer vs TfidfVectorizer. I tuned the
min_df parameter of the vectorizer to filter out words that didn’t occur in more
than 1% of the dataset; this helped get rid of nonsensical words like ‘ahhh’ or
‘agghh’. I also tuned the max_df to filter out words that occur too much like
“dream” or “sleep” and don’t add any value to the topic modeling.
* Combined with different dimensionality reduction techniques: PCA, LSA, NMF
and LDA.
* Different numbers for topic components (ranging from 3 to 10).


**Recommender with Cosine Similarity**
* Used cosine similarity to build the content recommender

## **Tools**
* Pandas and Numpy for data exploration and pre-processing
* Scikit Learn, NLTK, Regex, Gensim for pre-processing
* Sckikit Learn for Topic Modeling
* Cosine Similarity for Recommendation System

