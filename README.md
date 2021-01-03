# Emote-Controlled
Twitch chat emotion prediction through Sentimental Analysis on Twitch Chat Data 


# Using Classifiers
The code for querying our three classifiers are present in AverageBasedClassifier.py, DistributionBasedClassifier.py, and CNNBasedClassifier.py, respectively. After installing the required packages given in requirements.txt you can run python3 AverageBasedClassifier.py to replicate the sentiment analysis results from the paper on the test set. The same applies to the other classifiers as well. 
Each of the three classifiers has a classify_df method that classifies a Pandas DataFrame containing a message column that includes the texts to be classified. This can be used to easily estimate the sentiment of a batch of chat messages.

# Data
We provide all the data we used in this work, including unlabeled Twitch comment data for three months, a small labeled dataset of Twitch comments, as well as the lexica we used or created for our classifiers.

## Lexica
In our work, we used three sentiment lexica:

Emoji Sentiment Lexicon by Kralj Novak et al.
VADER Sentiment Lexicon by Hutto and Gilbert
A Self-Labeled Emote Lexicon
The emote lexicon was built by conducting a survey among active Twitch users. We let them label the 100 most used emotes at the time of writing the paper.
All three lexica are available in two versions: an average based version including only a value between -1 (very negative) and 1 (very positive) and a distribution based version that gives a distribution across the classes positive, neutral, and negative. You can find them as .tsv files in lexica.

## Labeled Twitch Data
For evaluating the performance of our prediction models, we sampled 2000 Twitch comments from very active Twitch channels. We then let three annotators assess the sentiment of each comment. Please refer to the paper for more information on the sampling and labeling process. 
The labeled dataset can be found as a .csv file in data.

## Unlabeled Twitch Data
We also provide three months of all Twitch comments. These are not labeled and mostly suited for analyzing the language used on Twitch. You can find the files in the Downloads section. The .csv files do not have a header row, but the structure is similar to the labeled dataset: date,channel,game,user,mod,subscriber,message.

Note: Usernames are anonymized and replaced with ids. These ids are coherent across all data files so you still can track the commenting history of users.
