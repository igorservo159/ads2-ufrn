# Study of Assortativity in a Network of Medicines and Active Ingredients :busts_in_silhouette:

## Objective: Analyze assortativity in the medicine network

This project investigates assortativity in a network of medicines and active ingredients, using data from ANVISA to test hypotheses on how regulatory category, therapeutic class, and company affiliation influence shared active ingredients. By constructing and visualizing graphs, we assess assortativity measures to determine whether medicines within the same regulatory category or therapeutic class tend to share more active components, compared to medicines from the same company. These analyses aim to reveal patterns that inform therapeutic strategies and support regulatory and pharmaceutical decision-making.

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
> Copyright (c) 2024, João Igor Ramos de Lima.  
> All rights reserved.   
> SPDX-License-Identifier: BSD-2-Clause

---

## Do medicines in the same regulatory category tend to share more active ingredients?

### Assortativity

Assortativity is a measure that indicates the tendency of nodes in a network to share similar characteristics. In the context of graphs, assortativity can be analyzed in relation to the attributes of the nodes, such as the regulatory category of medicines. If assortativity is high, it means that similar nodes tend to connect with each other, while low assortativity indicates that different nodes connect more frequently. This concept is crucial for understanding interactions in complex networks, such as that of medicines, where shared characteristics can impact the efficacy and safety of prescriptions.

### Drawing graphs

Trying to draw the complete database graph with REGISTRATION STATUS different of EXPIRED/CANCELED

![image](https://github.com/user-attachments/assets/31957735-8df1-48d8-968f-4cb6ac96134e)

Drawing the a database graph of 1000 random medicines rows with REGISTRATION STATUS different of EXPIRED/CANCELED for better vizualization

![image](https://github.com/user-attachments/assets/a3861171-abbd-46fe-9c19-1d15bb2f6de0)

### Conclusion

When calculating the assortativity of the complete graph of the medicines network from the federal government database by ANVISA based on regulatory category, while considering only medications with a valid or active registration status, we obtained the value **assortativity = 0.36022898461592506**.

Although this is not a very high value, considering that assortativity can range from 0 to 1, this graph demonstrates a certain tendency to share more active ingredients among medications within the same regulatory category. The presence of thousands of medications, and consequently thousands of nodes in the graph, reinforces this observation. This finding suggests that regulatory frameworks may influence the formulation and distribution of medications, potentially guiding prescribers in selecting therapeutic options that share similar active components. Understanding the dynamics of such relationships can provide valuable insights for regulatory authorities and pharmaceutical stakeholders, helping to optimize medication management practices and enhance patient safety.

## Do medicines of the same company tend to share more active ingredients? What about the ones that share the same therapeutic class?
- **Assortativity by Therapeutic Class**: 
  - The moderate value of **0.405** suggests that medications categorized under the same therapeutic class tend to share a greater number of active ingredients.
  
- **Assortativity by Company**: 
  - The low value of **0.030** indicates that there is no significant tendency for medications from the same company to share active ingredients.

- **Combined Assortativity**: 
  - The average value of **0.218** reflects a tendency for medicines to share active ingredients when considering either the therapeutic class or the company.

### Conclusion
The analysis reveals that medicines of the same therapeutic class are more likely to share active ingredients compared to those from the same company. This highlights the importance of therapeutic classifications in understanding the relationships among different medications, while company affiliation seems to play a lesser role in determining shared active ingredients.

