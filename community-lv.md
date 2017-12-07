---
layout: network-lv
---

# Community Analysis (Las Vegas)

The next step in our analysis is to define communities in our network and
see what these communities revolve around.First, we will look into the
sizes of the communities and the biggest accounts in the biggest communities,
to get a sense for the kind of accounts we find.
Then, we will look into the most common hashtags used in every community in
the mention graph, to get a feeling for the topics that live in every community.

We use the [Louvain method \[1\]](references) for community detection with
the following [implementation](https://github.com/taynaud/python-louvain) in
Python.

## Plots

Below two plots are displayed of the communities found with the Louvain
algorithm, with a legend table that shows some info on the most connected
node in this community, under the assumption that this will tell us something
about the community as a whole.



{% include partition-lv.html %}

## Analysis
We can see that for the mention graph, the communities have for the biggest part
centred themselves around major news outlets. We see
[@FoxNews](https://www.twitter.com/FoxNews)
and [@ABCNews](https://www.twitter.com/ABCNews),
but also local news stations as
[@dallasnews](https://www.twitter.com/dallasnews) and their reporters, like
[@lmcgaughy](https://www.twitter.com/lmcgaughy). For the hashtag graph, seem a bit more random.
We do, however recognize the twitter accounts of
[Sputnik News](https://www.twitter.com/SputnikInt), a Russion state
controlled media outlet, linked to fake news on
[multiple occasions](https://en.wikipedia.org/wiki/Fake_news_website), and
[marypatriotnews.com](https://www.twitter.com/marypatriotnews)
which is a hyper conservative outlet to say the least.

### Hashtag Heatmap

As
