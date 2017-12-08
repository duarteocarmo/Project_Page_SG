---
layout: community-texas
---

# Community Analysis
### #texasshooting

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



{% include partition-texas.html %}

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

It is interesting
to see that the highest degree nodes in the `hashtag_graph`'s partitions are
not necessarily
accounts with many followers. The links in this network are much more
'democratic', where anyone who uses a lot of prevalent hashtags can becomes
a well connected node in the graph. This is different from the `mention_graph`
where a user only gets mentioned a lot if he is well known and thus likely
to have many followers.

###  Hashtag Heatmap

To drill down further on what plays in the communities found in either network,
we will look at the hashtags are used in these communities and how they relate
to each other. A *heatmap* shows the number of occurrences of the top hashtags in
each community. The brighter the color, the more prevalent that hashtag is in
the tweets from that community and by extension from the users. This gives us
an idea about the ideas or opinions of these users. The data is a little sparse
for some communities since they are small and there are not that many hashtags,
but we can see some interesting patterns emerge in the ones that do have data.

#### Mention Graph
We have communities 16 and 17 mentioning **#guncontrol**, **#gunsense**,
**#guncontrolnow**, **#gunviolence** and **#stopgunviolence**,
which are all hashtags related to the camp
that wants to limit guns in America. Partitions 3 and 5 and 19 mention in **#texas**
combination with news outlets **#kens5eyewitness**, **#ksatnews** and **#usatoday**,
seemingly neutral. There are a bunch of more republican oriented hashtags
floating around, **#trump**, **#maga** (Make America Great Again), **#2a** (2nd amendment
which protects gun owners), **#tcot** (top conservatives on twitter),
**#msm** (mainstream media) and **#nra** (national rifle association -
lobby group for gun carry rights), which seem a little more used by
the partitions 12, 13, 9, 10, 5 and 6.

<p align="center">
 <img src="images/mention_hashtag_heatmap_tx.png"/>
</p>

####  Hashtag Graph
This *heatmap* is bit sparser, but some interesting things can be found still.
Partition 0 has high occurences of the hashtags **#guncontrol**, but in
combination with **#trump**, **#2a** and **#nra**, which are all very much pro
gun carrying. This could mean the hashtag is used within a whole different
context, where the people in this community talk about *gun control* in a negative
sense. Also, they talk about **#mentalhealth**, which could be a way to divert
to a conversation where guns are not the problem, but *mental health*. The other
communities that display noticable correlation seem to follow similar patterns
or have very neutral hashtags.

<p align="center">
 <img src="images/hashtag_hashtag_heatmap_tx.png"/>
</p>

### Emoji Hashtag Matrix

As we can see above, the use of a hashtag can be fairly ambiguous. People can
use a certain hashtag and be either pro or against it, or use the hastag in a
sarcastic or ironic way. To add a bit more context
we thought it would be interesting to look at what sentiments or thoughts
are associated with the hashtags in each community. For this, we used
[DeepMoji \[2\]](references) again. These researchers from MIT, among other
universities, have constructed a way to train neural networks on text with emojis
that let them predict a series of emojis from a sentence. The project is freely
available on github including the pretrained models, which can quite articulately describe the
sentiment or feeling of that piece of text. We decided to correlate
the hashtags used in every community with the emojis returned from DeepMoji
 to get a more refined image of the opinions
that are prevalent in these communities.

Below, the results of this correlation are displayed in a emoji / hashtag
matrix for the communities. De rows represent the different
communities in the networks and the columns the most common hashtags in these
networks. In the cells the most common emojis found through DeepMoji prediction
are displayed. The smallest communities and some trivial hashtags have
been left out for clarity.

#### Mention Graph

<p align="center">
 <img src="images/deepmoji_hashtag_mention.png"/>
</p>

From the table above, it is clear that some communities have more unified
feelings about certain topics than others. Most homogenic would be community 6,
which has either negative or positive emojis for most hashtags. They are big
fans of **#2a** (second amendment) but not so much of **#guncontrol**. They
display rather positive emotions for **#maga** (make america great again),
**#msm** (mainstram media, but used by far right),  **#nra** (the national rifle
association) and **#tcot** (top conservative on twitter). They seem rather
divided on **#trump** with both clapping and crying emojis. Interesting to see that
the most connected users in this community are ABC News and CBS News.

Similar emojis appear for community 9, except that an angry emoji appears
alongside all other ones. Maybe the language used in this community has a lot
of anger in it. Community 2 seems to condone **#gunviolence** and in favor of
**#guncontrolnow**.

#### Hashtag Graph

Unfortunately, the emoji / hashtag matrix for the hashtag graph is very
incoherent. All cells with emojis seem to express contradicting feelings. It
is included for completeness. The hashtag network's communities are small and
there was less data for this event in the data base to find the hashtags from.

<p align="center">
 <img src="images/deepmoji_hashtag_hashtag.png"/>
</p>

## Conclusion

Overall, we have found some interesting results from the community analysis on
both networks, but for the `mention_graph` it was definitely more insightful than
for the `hashtag_graph`. Since the partition is based of modularity of the
separate communities, it makes sense that a more 'hierarchical' and well defined
like the `hashtag_graph`. This showed in terms of the type of users made up the
big nodes in the network, as well as the more coherent partitions found in the
`mention_graph`.

A big probelm with comminity detection is the validation of the communities,
especially if they get large. The hahstag emoji matrix seems to be an interesting
tool to do this. However, we see that many communities have mixed emojis per hashtag.
This could
point to divided communities but could also be a result of data sparsity, inaccuracy
of the model or the fairly simple way the emojis were counted and averaged out.
More than a definite end result, this matrix should be seen as a proof of
concept which should be perfected to give accurate results.
