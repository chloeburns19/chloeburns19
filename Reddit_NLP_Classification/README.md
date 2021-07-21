# Project 3 - Subreddit Classification


## Problem Statement:
If I'm a retail worker at Best Buy, and have a great story from work that I want to share, where should I post it on Reddit? Create a model that classifies posts from r/TalesfromRetail and r/TalesfromTechSupport.


## Repo Details:

Notebook 01 contains web scraping of SubReddit posts and exporting to a csv file
Notebook 02 contains NLP EDA, modeling, and model evaluation.
The 'data' folder contains the corpus of SubReddit posts in a csv file ('posts.csv')

## Data Dictionary:

This is the data dictionary for the posts.csv corpus.

|Feature|Type|Description|
|subreddit|string|Title of the subreddit the post is from|
|title|string|title of the post|
|selftext|string|text of post|
|author|string|author username of post|
|created_utc|float|epoch time of post|


## Notebook 01 - Data Imports
Using the PushShift API, I created a function that scraped 10,000 posts from each subreddit and combined them in a dataframe. 



## Notebook 02 - NLP - Modeling
1. NLP Processing
- Employed tfidfvectorizer

2. Modeling
- compared multinomial naive bayes and logistic regression models

4. Evaluation
- logistic regression performed better
- false predictions contained non-retail and non-tech support posts

## Conclusions and Next Steps
- We created a model that accurately predicts which subreddit a given post comes from, and generalizes well to new data.
- In our sample case, the Best Buy retail worker post was classified as TalesfromRetail.
- The model could also be used to define other edge cases (i.e. tech lead at Target, Home Depot tool associate, etc.)
- I would want to conduct further analysis on the top words that predict each subreddit to understand context and _format_ of posts
    - NOTE: r/TalesfromTechSupport top predictor was 'gt', which formats blockquotes in posts. Interesting insight.
- I could also look at title, author behavior, length of posts, and other variables to improve model.


 



