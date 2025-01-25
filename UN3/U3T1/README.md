# Visualizing Bitcoin's Global Narrative :busts_in_silhouette:

## An Interactive Graph Network Using NLP

The world of cryptocurrency, led by Bitcoin, is ever-evolving, with news and updates shaping its narrative daily. To better understand the intricate web of discussions surrounding Bitcoin, I embarked on a project that combines the power of Natural Language Processing (NLP) and graph visualization. Here is a detailed look at how I used The Guardian API, *spaCy* NLP tools, the *NetworkX* Python library, and *Gephi's Sigma Explorer* plugin to create an interactive graph network from Bitcoin-related articles.

> ## Federal University of Rio Grande do Norte  
> ## Technology Center  
> ### Department of Computer Engineering and Automation  
> #### Course: **Algorithms and Data Structure II (DCA3702)**  
> #### Author: **João Igor Ramos de Lima :mortar_board:**
>
> This repository contains solutions to the tasks and exercises assigned in the Algorithms and Data Structure II (DCA3702) course.
>
> ### Contact
> [igorservo159@gmail.com](mailto:igorservo159@gmail.com)
>
> This project is licensed under the [MIT License](../../LICENSE)  
> © 2024 João Igor Ramos de Lima.  
> SPDX-License-Identifier: MIT

![Bitcoin Network DALL-E](./imgs/bitcoinDALL-E.webp)

> Generated with DALL-E

## 🌍 Practical Applications

The potential applications of this project are vast and varied, including:
- **Financial Institutions**: Providing insights for banks and investment firms to track trends and narratives impacting the cryptocurrency market.
- **Regulators and Governments**: Helping government bodies monitor and respond to shifts in public perception of Bitcoin and related regulations.
- **Academic Community**: Acting as a starting point for in-depth studies in economics, political science, and technology, offering an interactive lens into Bitcoin’s evolving narrative.

## 📖 Project Overview

The goal of this project was to explore the complex relationships and trends within the Bitcoin ecosystem as reflected in the news. By extracting and analyzing data from articles published by The Guardian, I aimed to identify key entities, topics, and their connections, creating a dynamic and interactive graph visualization available [here](https://igorservo159.github.io/Bitcoin_News_Articles_Network/).

To achieve this, I utilized several specialized Python libraries to streamline processing and visualization tasks:
- **scikit-network**: Provided powerful tools for graph-based data analysis and visualization.
- **python-dotenv**: Ensured secure handling of sensitive API keys.
- **spaCy**: Facilitated natural language processing tasks such as tokenization, tagging, and entity recognition.
- **NetworkX** and **Gephi**: Managed graph structures and visualization.

## 💻 Data Source: The Guardian API

The Guardian API was chosen for its high-quality, reliable journalism. It provides an efficient way to search for articles by keywords, filter by publication dates, and retrieve metadata such as titles, publication dates, and content summaries. With an API key, users can customize their queries to focus on specific sections, tags, or other criteria. In this project, parameters such as:

- **q**: Keyword query (e.g., “Bitcoin”)
- **section**: To filter by categories like “economy.”
- **tag**: For more specific topics (e.g., “technology/bitcoin”)
- **order-by**: To sort articles by publication date

helped ensure relevant and timely results.

**Example query URL:** 

```python
https://content.guardianapis.com/search?tag=technology%2Fbitcoin&order-by=newest&page-size=200&q=bitcoin&api-key=test
```
