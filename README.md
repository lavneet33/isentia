# ISentia Machine Learning Challenge

## Problem Description

For this challenge, we got two splits of data as Train.zip and Test.zip. Current problem we try to solve, currently we have large dataset consists of news articles from mutliple sources. General process is quite manual where someone has to go through each news articles and label them as defined categories which is quite a tedious process.
Thus, using machine learning, we proposed a new method to use machine learning to define Topics of news articles based on trends and patterns. For this excercise, we will use Gensim, NLTK, and Spatiy as part of Topic Modeling to split news report data into different topics.
Topic Modeling As the name suggests, it is the process of automatically identifying topics present within text objects and inferring hidden patterns exhibited by a text corpus, which contributes to better decision making.  
Topic modeling is different from rule-based text mining approaches that use regular expressions or dictionary-based keyword search techniques. This is an unsupervised approach used to find and observe groups of words (called "topics") within large clusters of text. 
Topics can be defined as "repeating patterns of  terms that co-occur within a corpus.
We have a dataset consisting of news articles, and our task is to assign topics to these articles. We will design a simple tf-idf vectorisation and Lemmatisation followed by Latesnt Sementic Anlaysis (LSA) and LDA(Latent Dirichlet Allocation) to lead to better Topics. 
Evaluation Metrics of Topics will be achieved using Coherence Score and Perplexity along with visualisation of Top Topics using WordCloud.

## Project Plan for Topics Modelling of News Articles and Training Supervised Classifier using LDA Feature Vectors

The project steps for applying topic modeling to the news headlines dataset can be as follow:

1. Exploratory Data Analysis: The next step is analyzing the data to understand the distribution of headlines over time. The frequency of different words and phrases, and other patterns in the data. Also, you can visualizing the data using charts and graphs to gain insights into the data.
2. Data Pre-processing: The first step is cleaning and preprocessing the text to remove stop words, punctuation, etc. It also involves tokenization, stemming, and lemmatization to standardize the text data and make it suitable for analysis.
3. Topic Modeling: The core of the project is applying techniques such as LDA. Then, identify the main topics and themes in the news headlines dataset. It requires selecting the appropriate parameters for the topic modeling algorithms. For example, the number of topics, the size of the vocabulary, and the similarity measure.
4. Topic Interpretation: After identifying the main topics, the next step is interpreting the topics and assigning human-readable labels to them. It includes analyzing the top words and phrases associated with each topic and identifying the main themes and trends.
5. Evaluation: The final step involves evaluating the performance of the topic modeling algorithms. Then, comparing them based on metrics such as coherence score and perplexity. Identifying the limitations and challenges of the topic modeling approach and proposing possible solutions.

Current Model Process Defined as:

## Loading the data
## Clean the Data
Transforming text into something an algorithm can digest it a complicated process. We cannot feed the data as it is, some preprocessing needs to be done. In this task we will be doing some preprocessing to convert our data in a form that we can feed our model with.
## Handling the Stop-words
Text may contain stop words like ‘the’, ‘is’, ‘are’. Stop words can be filtered from the text to be processed. There is no universal list of stop words in nlp research, however the nltk module contains a list of stop words. We will remove these stopwords in this task.
## Lemmatization
## TF-IDF Vectorization
Apart from Count vectorizer an alternative to calculate word frequencies , and by far the most popular method is called TF-IDF. This is an acronym than stands for “Term Frequency – Inverse Document” Frequency which are the components of the resulting scores assigned to each word.
##Topic modelling using LSA
Latent Semantic Analysis, or LSA, is one of the foundational techniques in topic modeling. The core idea is to take a matrix of what we have — documents and terms — and decompose it into a separate document-topic matrix and a topic-term matrix.
## Topic Modelling using Gensim's LDA
One of the drawbacks of LSA is that though it is really fast, its effectiveness in finding good topics is not great. One assumption that LSA makes is that the topics are orthogonal to each other, while Latent Dirichlet Allocation (LDA) relaxes this assumption. Moreover, LDA generalizes the way the documents are generated and this modelling assumption leads to better topics. Let us first understand intuitively how LDA works.
## Choosing the Number of Topics for LDA
Run LDA on your corpus with different numbers of topics and see if word distribution per topic looks sensible. Gensim also provides a Hierarchical Dirichlet Process (HDP) class [5]. HDP is similar to LDA, except it seeks to learn the correct number of topics from the data; that is, you don’t need to provide a fixed number of topics. 
## Creating a LDA Model
## Evaluation Metrics of Topics will be achieved using Coherence Score and Perplexity along with visualisation of Top Topics using WordCloud.
## Converting Topics to Feature Vectors
The ultimate goal is not only to see how this performs in a train/test CV split of the current data, but whether the topics have hit on something fundamental that translates to unseen test data in the future
## Converting Unsupervised Output to a Supervised Problem by Training a Supervised Classifier and validating on Test Dataset
## Performance Metrics of Supervised Classfier as F1 Scores, Recall, ROC 

# Challenge Limitations
I am not able to extract labels as annotated labels from text file, due to Regex Expressions. Need more time to extract so as to train Supervised classifier where X= news_df.col and Y = news.df.Target. Currently, I managed to convert LDA feature vectors into X but unable to extract labels from file.
Optimisation can be done to make LDA Topics more accurate for Top 5 or Top 10

# Run Process
Please upload train.txt in your Google Drive if you runing Notebook in Google Colab or Jupyter Notebook. Run first line of code to mount google drive and define path as /content/Isentia
There might be some packages required for NLTK, please download as mentioned in script.

## How do you evaluate the accuracy and correctness of your model(s)?
Evaluation metrics like Coherence Score and Perplexity need to be optimised to improve accuracy. For supervised learning on LDA feature vectors, standard machine learning metrics like F1 Scores, Recall and ROC with MSE and AUC need to be evaluated.

## What could you do to improve the accuracy of your model?
I have not tested using Spacy and Bigrams models, but can be compared with LDA and LSI. Generative Neural Networks has been heavily used as Generative AI as more accurate models then LDA, but K-Fold validation is required if improving the accuracy of current model. Manual validation can be done using stratified sampling on generated Topics to match Manual Annotation of Topics.
There are several optimization procedures, one of them is Variational Expectation Maximization (VEM). It is a statistical method used to estimate the parameters of a probabilistic model. It is an extension of the Expectation Maximization (EM) algorithm that allows for the use of approximate inference techniques. The second is known as Gibbs sampling, which is a method based on Markov Chain Monte Carlo (MCMC). It is a family of statistical algorithms that use Markov Chains to generate a sequence of samples from a probability distribution. It is a powerful technique used for Bayesian inference and parameter estimation in complex models.

## How would you serve your model(s) in production?
There are process set up in Cloud Services, like Airflow and MLFlow for making and running models in production. Suggest to run Beta version with less data in prod, and aquire weights of model to marry up with test or production data so as to save time on resources and faster performance. Also, dump or pickle the model prediction using Postman APIs so can be easy callout from any SAAS services.

## - Imagine that there are future requirements that ask you to add a new class/topic/pattern? What would re-training look like? Are there any concerns? How would you avoid these concerns?
There is always model drift where new data adds with different patterns and trends, thus starting point is always to set up data pipeline to check data distribution and data quality. If there any delta, then re rerun the training model to capture model drift and validate with delta difference in performance accuriacies.























