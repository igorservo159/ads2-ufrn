# Creating an OSMnx Network of Natal-RN City :busts_in_silhouette:

This notebook generates a network for the city of Natal, RN, using OSMnx and conducts an analysis based on various network metrics. These metrics provide insights into the city's connectivity, accessibility, and overall network structure.

## Objective: Analyze assortativity in the medicine network

### Student: João Igor Ramos de Lima :mortar_board:

### Algorithms and Data Structure II (DCA3702)


## Metrics Analyzed

- **Cycles**: Identifies cycles in the network, representing closed loops that indicate areas with higher local connectivity.

- **Average Shortest Path Length**: Calculates the average distance of the shortest paths between nodes, which reflects general accessibility across the network.

- **Diameter of Network**: Measures the longest shortest path within the network, indicating the maximum distance between any two nodes.

- **Shortest Path Length**: Determines the shortest paths between specific nodes or regions, useful for analyzing direct accessibility.

- **Connected Components**: Examines isolated sub-networks within the larger network, helping identify disconnected or less accessible areas.

- **Giant Connected Component**: The largest connected sub-network, representing the main area of high connectivity within the city.

- **Number of Connected Components**: Counts the total disconnected segments in the network, highlighting isolated regions.

- **BFS (Breadth-First Search)**: Explores the network level-by-level from a starting node, useful for assessing reachable areas from a specific point.

- **DFS (Depth-First Search)**: Traverses the network by going as deep as possible from a starting node, providing insights into possible paths and clusters.

- **SCC (Strongly Connected Components)**: Identifies clusters of nodes where every node is reachable from any other node within the component, indicating areas of high interconnectivity.

- **WCC (Weakly Connected Components)**: Highlights components where each node is accessible by ignoring direction, providing a sense of general connectivity.

- **Clustering Coefficient**: Measures the degree to which nodes in the network tend to cluster together, suggesting how well-connected neighborhoods or regions are.

This analysis provides valuable information for urban planning, transportation management, and improving access within the city.

## What is OSMnx?

OSMnx is a powerful Python library that allows users to download, model, and analyze street networks and other geospatial data from OpenStreetMap (OSM). It simplifies the process of working with OSM data by providing tools to create network graphs, visualize them, and calculate various metrics related to connectivity and accessibility. OSMnx is widely used in urban planning, transportation studies, and geographic analysis, enabling researchers and practitioners to gain insights into urban mobility and infrastructure through detailed network analysis.

### Creating a Simple Network

It is quite simple to create a network for almost any location accessible via OpenStreetMap. 

To get started, simply import the `osmnx` library along with `networkx`, and generate a directed multigraph (which may have more than one edge connecting the same two nodes) using the `graph_from_place` function from OSMnx, passing the name of the place as an argument. You can then visualize the graph using the `plot_graph` function.

```python
import osmnx as ox
import networkx as nx

place_name = "Natal, RN, Brazil"
G = ox.graph_from_place(place_name, network_type='drive')

ox.plot_graph(G)

![Natal Network](./natal_network.png)


