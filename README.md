# Dataset: Brazilian 2018 elections on Twitter
This is a collection of Twitter messages (tweets) posted between 2018-07-05 and 2018-10-28, covering discussion related to the Brazilian presidential, senate, upper house of congress and state governor elections of 2018.

The original focus of the collection is *textual analysis*, and in particular *bot detection / classification*. Therefore, the data is anonymized (no user ids or screen names, except for mentions). Furthermore, metadata is included to help contextualize the tweets and also to facilitate common tweet processing tasks, such as hashtag extraction.

A set of descriptive statistics about the dataset is also provided, to enable quick evaluation of suitability for any given study.

## Structure
The dataset contains three files, as follows:
* br_elections_2018.tsv.bz2: contains the tweets and most metadata associated with each message.
  - id: unique message identifier (not the Twitter one).
  - lang: language of the message (en or pt).
  - text: the raw message text (UTF-8).
  - class_id: the classification identifier, referencing the corresponding botometer scores on the br_elections_2018_classif.tsv.bz2 file.
  - created_at: date and time the tweet was posted.
  - count: number of times the message was repeated (reposted).
  - hashtags: list of unique hashtags found in the message.
  - mentions: list of unique mentions found in the message.	
  - rt: whether the tweet is a retweet (1) or not (0).

* br_elections_2018_classif.tsv.bz2: contains the bot classification scoring by the [botometer](https://botometer.osome.iu.edu/) (Davis et. al)
  - class_id: unique classification score identifier.
  - english: the English language score for the likelihood of the user that posted the message being a bot. This score is more accurate for english language messages.
  - universal: the universal score for the likelihood of the user that posted the message being a bot. Less accurate, but applies to any language.

* br_elections_2018_stats.json: contains a set of descriptive statistics about the dataset. A single object JSON file.
  - freq_per_day: number of tweets for each day in the collection interval (key = yyyy-mm-dd).
  - num_orig: number of original messages.
  - num_retweets: number of retweets, including duplicates.
  - total_tweets: total number of tweets, including duplicates.
  - fraction_classif: fraction of tweets that received a bot classification score from the botometer,
  - distr_retweets: distribution parameters (mean, stddev) for the number of retweets on each message as a random variable.
  - freq_lang: number of tweets per language, including duplicates.
  - freq_hashtags: number of ocurrences for each hashtag in the collection.
  - freq_mentions: number of ocurrences for each mention in the collection.


## Publications
* TBA


## References
* Clayton A. Davis, Onur Varol, Emilio Ferrara, Alessandro Flammini, and Filippo Menczer: *[BotOrNot: A System to Evaluate Social Bots](https://dl.acm.org/doi/10.1145/2872518.2889302)*. Proceedings of the 25th International Conference Companion on World Wide Web, pp 273–274, 2016.
