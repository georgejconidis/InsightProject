# Project Title : Emotional Sage - Feeling Customer Satisfaction

# Tech Summary:
* #### **Natural Language Processing, Naive Bayes Multinomial Classifier, Text Pre-processing, Term Frequency Inverse Document Frequency (TF-IDF), Optimization**

# Table of Contents:
1. ### Motivation
2. ### Description
3. ### Data Sources
4. ### Data/Text Pre-processing
5. ### The Model for Sentiment Analysis
6. ### Exploratory Data Analysis
7. ### Current Status of Application
3. ### Installation
4. ### Usage
5. ### Credits


# 1. Motivation

Live Chat has become a popular way for companies to reach their customers needs. In the text environment, such as Live Chat, the customer service agent is left to discern the emotional state of the conversation based on previous experience with text message conversations. In contrast, a phone or in-person conversation would allow a customer service agent to determine the emotional state of the costumer with greater confidence via speech tonality and body language, respectively. So it is clear that the Live Chat customer service agent is not afforded an equal footing to gauge how the conversation with a customer is going, and hence may be vulnerable to having more conversations end negatively for a customer.

In recent years, Live Chat has been making use of the instant messaging platform, Twitter. The platform has a huge audience base and companies are able to reach a large fraction of their customers with little effort. The challenge for a company using Twitter, is the comments/conversations are available for the public to view (unless Private Messaging is used). This leads to a company managing the escalation and deescalation of a customer service request in the public eye. This is a uniquely challenging domain to conduct customer service and needs to be handled with as much care and diligence as possible.

# 2. Description:

Emotional Sage is a web application tool which helps customer service agents using Twitter to converse with clients. Emotional Sage monitors the real-time emotional state of a conversation and will notify the customer service agent when the conversation will likely be unresolved if measures are not taken.

# 3. Data Sets Used

There are two data sets that were used for this project:
1. Twitter US Airline Sentiment (Tweets that were labelled for their sentiment)
https://www.kaggle.com/crowdflower/twitter-airline-sentiment
2. Customer Support on Twitter (Tweets that were part of conversations between customers and customer service agents)
 https://www.kaggle.com/thoughtvector/customer-support-on-twitter

# 4. Training Emotional Sage to Detect Emotions and Text Pre-processing

The 'Twitter US Airline Sentiment' data set is used to train a Multinomial Naive Bayes Classifier. The data set contains 14,640 Tweets. The tweets are labelled as "negative", "neutral", and "positive". The "neutral" tweets have been removed and the remaining tweets have been under-sampled relative to the "positive" labels, leaving 6,250 tweets to be used for training, validation, and testing the model.

The Tweets are then pre-processed before training the classifier using the following techniques:
* Tokenization
* Stop word and Special Character removal
* Lemmatization
* Bag of Words Creation
* TF-IDF (Term Frequency - Inverse Document Frequency)

A Naive Bayes Classifier using a Multinomial distribution is trained to 82.2 % accuracy on the 'Twitter US Airline Sentiment' data set. This provides Emotional Sage with the ability to determine the sentiment of Tweets.

<!-- Here is an example of a Twitter Conversation which is emotionally classified by Emotional Sage. The Customer is plotted in <span style="color:aqua">blue</span> and the customer service agent in <span style="color:lightgreen">green</span>. -->

<!-- ![This is an example of a Twitter Conversation: Emotional Sentiment vs. Tweet Number in Chronological Order](/home/george/Documents/Insight_DS_TO20A/Projects/EmotionalDetection/data/raw/Preliminary_AgentCustomer_Emotional_Output.png)
**This is an example of a Twitter Conversation: Emotional Sentiment vs. Tweet Number in Chronological Order** -->

# 6. Exploratory Data Analysis

The 'Customer Support on Twitter' data set is used to explore the behaviour of customers and customer service agents. The analysis is focused on the global properties of conversations.

The conversations were generated by following the tweet identifiers and linking them together. Afterwards the tweets must be organized chronologically to ensure that the sentiment of a conversation can be tracked according to content and causality in future works.

The metric investigated for the MVP (Minimum Valuable Product) was the sum of a conversations negative tweets divided by the total number of tweets in the conversation. This is referred to as the Negativity Score. These Negativity Scores are investigated to forecast when a conversation is trending towards an unresolved outcome.

Conversations are labelled according to the sentiment of the final tweet by the customer. That is, whether or not the customer left with a positive or negative customer experience the conversation is labelled as resolved (positive) or unresolved (negative). These labels have been validated by using a Kuiper test on the resolved and unresolved distributions of the Negativity Values for conversations with 5 tweets. The results of the Kuiper test are: a D-statistic of 0.48 and a probability of both distributions been drawn from the same sample of 9.3e-53. Therefore, we find that the two distributions are distinct, implying that the labelling method is validated.


# 7. Current Status

The current status of the web-app is to display pre-existing Twitter conversations between customer service agents and customers which have been analyzed by Emotional Sage.

## Notice

Currently the app is in beta testing. Currently the app has been disabled for maintenance but when it is up and running you can find it at www.DatSci.xyz.


# 8. Credits:

Created and Developed By: George James Conidis

This was done during his Insight Data Science Fellowship (Toronto, Canada).
