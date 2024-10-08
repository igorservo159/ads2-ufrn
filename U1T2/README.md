# UFRN co-authorship Network :busts_in_silhouette:

## Objective: Create and manipulate a co-authorship network using real data extracted from the Scopus platform

### Student: João Igor Ramos de Lima :mortar_board:

### Algorithms and Data Structure II (DCA3702)

**Getting UFRN articles data :globe_with_meridians:**

Searching in [Scopus](https://www.elsevier.com/products/scopus) database of articles and citations, I got the scopus.csv file containing information about articles published by authors from UFRN. The data was filtered by the fields of **computer science**, **engineering**, and **mathematics**, focusing on the following topics: **neural networks**, **artificial intelligence**, and **machine learning**.

The .csv file includes the following columns:
- Author names
- Unique author identifiers
- Article title
- Year of publication

<center><img width="max-width" src="imgs/scopus_csv.png"></center>


**Testing NetworkX [:thought_balloon:](networkX_test.ipynb)**

Down bellow we have an example of a graph developed using only networkX python library.

<center><img width="max-width" src="imgs/networkX_test.png"></center>

**Coauthorship Network [:globe_with_meridians:](Coauthorship_Network.ipynb)**

Using the scopus.csv file, we can creat a graph with python with the following piece of [code](Coauthorship_Network.ipynb).

<center><img width="max-width" src="imgs/carbon.png"></center>

Completed graph of the whole .csv file using nxviz python library for graph visualization.
<center><img width="max-width" src="imgs/graph.png"></center>

> Graph density: 0.012327998680085795

> Number of authors: 551

Subgraph using only nodes that have at least 20 neighbors. It can be useful to find the reaserchers at UFRN that have a notable (20+ contributions) network in articles of a specific field of study.
<center><img width="max-width" src="imgs/subgraph.png"></center>

> Subgraph density: 0.39572192513368987

> Number of authors: 34

It is possible to observe a notable increase in the density of the subgraph compared to the original graph. This happens because the subgraph contains only nodes with 20 or more neighbors, unlike the original graph, which has nodes with very few neighbors. Thus decreasing the value of the network density.

Therefore, since this is a dense subgraph, we have information about authors with significant participation in articles and academic works by other researchers.