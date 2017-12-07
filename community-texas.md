---
layout: community-texas
---

# Community Analysis

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

{% include partition-texas.html %}
