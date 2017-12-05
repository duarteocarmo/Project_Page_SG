---
layout: network
---

# The Networks

### Generating networks from tweets
From the tweets we collected we are going to generate 2 of different networks that we will be using throughout the rest of the analysis. In either network, the *nodes* are going to be the users that have been tweeting about the event using one of the predefined hashtags.   
For the first network, the *edges* will be constructed through mentions in these tweets. So, when a tweet mentions another user that is also a *node* in the network, there will be an *edge* between these two *nodes*. We will refer to this network as `mention_graph`.   
For the second network, we define the *edges* between *nodes* if they share a common hashtag, not including the query hashtags. For example, if two tweets from different *nodes* use the hashtag **#GunSense**, we will create an *edge* between them. We will refer to this network as `hashtag_graph`.

{% include mention_graph.html %}
