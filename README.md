## ISentia Machine Learning Challenge

## Problem Description

For this challenge, we got two splits of data as Train.zip and Test.zip. Current problem we try to solve, currently we have large dataset consists of news articles from mutliple sources. General process is quite manual where someone has to go through each news articles and label them as defined categories which is quite a tedious process.
Thus, using machine learning, we proposed a new method to use machine learning to define Topics of news articles based on trends and patterns. For this excercise, we will use Gensim, NLTK, and Spatiy as part of Topic Modeling to split news report data into different topics.
Topic Modeling As the name suggests, it is the process of automatically identifying topics present within text objects and inferring hidden patterns exhibited by a text corpus, which contributes to better decision making.  
Topic modeling is different from rule-based text mining approaches that use regular expressions or dictionary-based keyword search techniques. This is an unsupervised approach used to find and observe groups of words (called "topics") within large clusters of text. 
Topics can be defined as "repeating patterns of  terms that co-occur within a corpus.
We have a dataset consisting of news articles, and our task is to assign topics to these articles. We will design a simple tf-idf vectorisation and Lemmatisation followed by Latesnt Sementic Anlaysis (LSA) and LDA(Latent Dirichlet Allocation) to lead to better Topics. 
Evaluation Metrics of Topics will be achieved using Coherence Score and Perplexity along with visualisation of Top Topics using WordCloud.

# Project Plan

The project steps for applying topic modeling to the news headlines dataset can be as follow:

1. Exploratory Data Analysis: The next step is analyzing the data to understand the distribution of headlines over time. The frequency of different words and phrases, and other patterns in the data. Also, you can visualizing the data using charts and graphs to gain insights into the data.
2. Data Pre-processing: The first step is cleaning and preprocessing the text to remove stop words, punctuation, etc. It also involves tokenization, stemming, and lemmatization to standardize the text data and make it suitable for analysis.
3. Topic Modeling: The core of the project is applying techniques such as LDA. Then, identify the main topics and themes in the news headlines dataset. It requires selecting the appropriate parameters for the topic modeling algorithms. For example, the number of topics, the size of the vocabulary, and the similarity measure.
4. Topic Interpretation: After identifying the main topics, the next step is interpreting the topics and assigning human-readable labels to them. It includes analyzing the top words and phrases associated with each topic and identifying the main themes and trends.
5. Evaluation: The final step involves evaluating the performance of the topic modeling algorithms. Then, comparing them based on metrics such as coherence score and perplexity. Identifying the limitations and challenges of the topic modeling approach and proposing possible solutions.






















