---
layout: post
title: Word2Vec Application
date: 2019-10-01
---

### An Introduction to My Word2Vec Application

At China Media Cloud, I've worked on multiple applications involving Word2Vec models. The basic idea behind Word2Vec is to represent words with vectors in order to use mathematical properties of vectors to perform calculations with words. The majority of my work on Word2Vec models is done with Python's CoreNLP, developed by Stanford University, and Gensim, an awesome package for Word2Vec modeling.

Some of the things I did was:
  * Identify customer business need that can be fulfilled with Word2Vec models.
  * Collect training data with internal APIs and data of my company.
  * Preprocess, format, and label data for training.
  * Use Gensim to train Word2Vec models.
  * Incorporate Word2Vec models into Smart Editor web application.

Before any programming, I was asked to research common NLP models, packages, and their applications with a senior engineer. We had meetings with product managers, clients, and tech VP of the company to discuss how we can incorporate NLP technologies into out existing products for more functionalities and services. After settling down to a few packages, namely CoreNLP for Entity Recognition, Part-Of-Speech Identification, and Gensim for Word2Vec, I started to work on the training data.

If there's one thing I've learned from the projects, that is the training data is utterly important in any machine learning/deep learning tasks. I spent a major chunk of my time working on the cleaning (getting rid of the scrambled words and characters), parsing (easy for english, but can be very tricky for non-space-separated languages, such as Chinese or Japanese), and formatting (often involving some yield function to reduce memory use) the textual data in order to make the training easier.

To put it very simple, a Word2Vec model is a neutral network that translates words into vectors. A simple, but not that simple, introduction to Word2Vec can be found [here](https://skymind.ai/wiki/word2vec). Word2Vec is a great idea in terms of computability because computers can work with vectors and numbers much more easily and effectively than strings of characters. My work involves training multiple Word2Vec models with the training data I prepared in advance, and utilize the models for higher-level tasks.

Because the fact that the model generates a spacial distribution of the words during training, it can compute the synonym or antonym with some simple matrix computation. While the model technically can't understand the semantic meanings, it can find relationships of a word to other words. With this technique, we've built a relevance-reveal system where the user will get a radar map of relative words with relevance level for his/her selection. Several models were trained for different news categories to improve their accuracies. For example, an ESPN sports editor wants to write about basketball. He selects the word "Los Angeles Lakers" for a search, and the sports news Word2Vec model (trained with sports news) will return a list of relative keywords such as "LeBron", "Kobe", or "Rockets" and their associated relevance level to help the editor to expand his writing. The models were loaded in the server, and updated from time to time with newly collect news data. I also wrote RESTful APIs for this function and added a censor mechanism to filter return values per client requests.

Another application of the Word2Vec models is the News Classifier that I worked on. The Word2Vec model acts as the embedding layer (which transform string of characters into vectors) of the News Classifier CNN and works very well because it was trained with the news data that were to be classified by the classifier and adjusted accordingly. I will write more about the News Classifier later.


Last Modified: 10-15-2019
