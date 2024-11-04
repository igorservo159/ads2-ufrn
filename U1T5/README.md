# Evaluating Mobility Near UFRN for Bike Sharing Dock Stations Placement :busts_in_silhouette:

## Objective: Analyze mobility for optimal placement of bike-sharing dock stations around UFRN

### Student: João Igor Ramos de Lima :mortar_board:

### Algorithms and Data Structure II (DCA3702)

---

## Project Description

This project aims to evaluate mobility around UFRN to determine optimal locations for installing bike-sharing dock stations. The analysis will focus on identifying key neighborhoods around the university that could benefit from such stations and assessing strategic placement options.

## Key Question
**Where are the optimal locations for dock-station placement?**

One way to answer it is to take into account the following network statistics:

### Centrality Metrics

- **Degree Centrality:** Number of connections of each neighborhood node.
- **Closeness Centrality:** Calculates the average distance from each node to all other nodes, assessing overall accessibility.
- **Betweenness Centrality:** Analyzes each neighborhood's position on the shortest paths, determining areas of intermediation.
- **Eigenvector Centrality:** Assesses each node's influence based on the importance of its neighbors.

### CDF and PDF Analysis of Node Degrees

This statistical approach will evaluate the distribution of connections, providing insights into connectivity patterns.
  
### Multivariate Centrality Analysis

A comprehensive, multivariable analysis will assess the interplay among different centrality metrics.

### Core/Shell

Who constitutes the core and shell of the network?

---

## Implementing UFRN Mobility Graph Network

To address the problem, we can start creating a network graph representing the UFRN area, including nearby neighborhoods such as Candelária, Lagoa Nova, Capim Macio, and Nova Descoberta. We can achieve this using the **OSMnx** library in Python.

```python

import osmnx as ox
import networkx as nx

ufrn_box = -5.82846, -5.84804, -35.21549, -35.19446

ufrn = ox.graph_from_bbox(bbox=ufrn_box, network_type='bike')

fig, ax = ox.plot_graph(ufrn, bgcolor='white', node_color='red', edge_color='black', node_size=10, edge_linewidth=0.8)

```

![UFRN Bike Network Graph](./ufrn_network.png)

### Answering the Key Question with Centrality Metrics

To address the question, we analyze the **top central nodes** in the network using four centrality metrics: **Degree**, **Closeness**, **Betweenness**, and **Eigenvector**. By focusing on the top nodes for each metric, we can identify key nodes and intersections between these metrics.

The steps involve calculating each centrality measure and selecting the top 10 nodes for each. Intersections between metrics highlight nodes that exhibit high centrality in multiple measures, indicating their prominent role in network connectivity.

```python
import matplotlib.pyplot as plt
import matplotlib.patches as mpatches

degree_centrality = nx.degree_centrality(ufrn)
closeness_centrality = nx.closeness_centrality(ufrn)
betweenness_centrality = nx.betweenness_centrality(ufrn)
eigenvector_centrality = nx.eigenvector_centrality(ox.convert.to_digraph(ufrn), max_iter=1000)

top_10_degree = set(sorted(degree_centrality, key=degree_centrality.get, reverse=True)[:10])
top_10_closeness = set(sorted(closeness_centrality, key=closeness_centrality.get, reverse=True)[:10])
top_10_betweenness = set(sorted(betweenness_centrality, key=betweenness_centrality.get, reverse=True)[:10])
top_10_eigenvector = set(sorted(eigenvector_centrality, key=eigenvector_centrality.get, reverse=True)[:10])

top_degree_closeness = top_10_degree & top_10_closeness
top_degree_betweenness = top_10_degree & top_10_betweenness
top_degree_eigenvector = top_10_degree & top_10_eigenvector
top_closeness_betweenness = top_10_closeness & top_10_betweenness
top_closeness_eigenvector = top_10_closeness & top_10_eigenvector
top_betweenness_eigenvector = top_10_betweenness & top_10_eigenvector
top_all_metrics = top_10_degree & top_10_closeness & top_10_betweenness & top_10_eigenvector

node_colors = []
node_sizes = []

for node in ufrn.nodes:
    if node in top_all_metrics:
        node_colors.append('black')
        node_sizes.append(250)
    elif node in top_degree_closeness:
        node_colors.append('cyan')
        node_sizes.append(200)
    elif node in top_degree_betweenness:
        node_colors.append('purple')
        node_sizes.append(200)
    elif node in top_closeness_betweenness:
        node_colors.append('orange')
        node_sizes.append(200)
    elif node in top_degree_eigenvector:
        node_colors.append('pink')
        node_sizes.append(200)
    elif node in top_closeness_eigenvector:
        node_colors.append('brown')
        node_sizes.append(200)
    elif node in top_betweenness_eigenvector:
        node_colors.append('lime')
        node_sizes.append(200)
    elif node in top_10_degree:
        node_colors.append('blue')
        node_sizes.append(100)
    elif node in top_10_closeness:
        node_colors.append('red')
        node_sizes.append(100)
    elif node in top_10_betweenness:
        node_colors.append('green')
        node_sizes.append(100)
    elif node in top_10_eigenvector:
        node_colors.append('yellow')
        node_sizes.append(100)
    else:
        node_colors.append('grey')
        node_sizes.append(10)

fig, ax = ox.plot_graph(
    ufrn,
    bgcolor='white',
    node_color=node_colors,
    edge_color='black',
    node_size=node_sizes,
    edge_linewidth=0.8,
    show=False,
    close=False
)

legend_handles = [
    mpatches.Patch(color='blue', label='Top Degree Centrality'),
    mpatches.Patch(color='red', label='Top Closeness Centrality'),
    mpatches.Patch(color='green', label='Top Betweenness Centrality'),
    mpatches.Patch(color='yellow', label='Top Eigenvector Centrality'),
    mpatches.Patch(color='cyan', label='Top Degree & Closeness'),
    mpatches.Patch(color='purple', label='Top Degree & Betweenness'),
    mpatches.Patch(color='orange', label='Top Closeness & Betweenness'),
    mpatches.Patch(color='pink', label='Top Degree & Eigenvector'),
    mpatches.Patch(color='brown', label='Top Closeness & Eigenvector'),
    mpatches.Patch(color='lime', label='Top Betweenness & Eigenvector'),
    mpatches.Patch(color='black', label='Top Degree, Closeness, Betweenness & Eigenvector')
]

plt.legend(
    handles=legend_handles, 
    loc='upper right', 
    fontsize='x-small',  
    frameon=True, 
    markerscale=0.7
)
plt.show()
```
![Centrality Metrics](./centrality_metrics.png)
