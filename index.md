---
layout: default
---

# The Project

![cover](images/cover.png)

## Idea

The main idea was inspired by [this](https://medium.com/hci-design-at-uw/information-wars-a-window-into-the-alternative-media-ecosystem-a1347f32fd8f) Medium Article where the author, [Kate Starbird](https://medium.com/@katestarbird) analyses tweets and news sources they site. With this information she manages to build a network about the flow of information. 

So we thought, what can we find that is interesting about the tweets right after a big event, such a shooting, an attack (or maybe something not terrorism related)? 

The main purpose of this project is to build a set of tools to which anyone can feed a query to a database, so that he/she can directly return insights from it. 

In case my explanation sucks (which it probably does, here's a picture):

![process](images/process.png)

## Data

To handle data, we used several tools:

- [MongoDB](https://www.mongodb.com)  to store our data and [PyMongo](https://pypi.python.org/pypi/pymongo/) to handle it. 
- To actually receive tweets, the GetOldTweets API that can be found [here](https://github.com/Jefferson-Henrique/GetOldTweets-python).
- [NetworkX](https://networkx.github.io) for the network analysis. 
- [DeepMoji](https://github.com/bfelbo/deepmoji) for sentiment analysis and classification. 
- Other standard python libraries (numpy, matplotlib, etc.)

## Analysis

To prove the pipeline of tools, we applied them to two different events:

- The 2017 Sutherland Springs church shooting. (5th November 2017) [Notebook]()
- The 2017 Las Vegas shooting. (1st October 2017) [Notebook]()

There are many ways you can consult the analysis: 

- Browse them in a more interactive, article-like way in the sections on the left of this page. 
- Download the Notebooks, each one related to one of the events. 

## Main Findings

Throughout our analysis, we found a lot of cool stuff, here are some of the most important findings: 

!!!!!!!WRITE MOST IMPORTANT WRITINGS HERE BOYS!!!!!!!

- On the [Sentiment Analysis for the Texas Church Shooting](https://duarteocarmo.github.io/Project_Page_SG/sentiment-page), something very interesting happens with user sentiment at the 1 week mark, where the DeepMoji model helps us identify some sort of mourning, exactly one week after the event, where people start referring to the shooting in a more compassionate, less agressive  way. 









