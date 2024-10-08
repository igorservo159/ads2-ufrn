# Co-authorship Network :busts_in_silhouette:

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

<center><img width="max-width" src="imgs/networkX_test.png"></center>

**Coauthorship Network [:globe_with_meridians:](Coauthorship_Network.ipynb)**


Complete graph of the whole .csv file
<center><img width="max-width" src="imgs/graph.png"></center>

> Graph density: 0.012327998680085795

> Number of authors: 551

Subgraph using only articles that have at least 20 authors involved
<center><img width="max-width" src="imgs/subgraph.png"></center>


> Subgraph density: 0.39572192513368987

> Number of authors: 34
