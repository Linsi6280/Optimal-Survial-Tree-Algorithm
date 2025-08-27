## Description
This repository contains the code and analysis for a project that compares the performance of various models for survival data analysis. The primary focus is on the Optimal Survival Tree (OST) algorithm, which is compared against the Random Survival Forest (RSF) algorithm and the traditional Cox proportional hazards model.



## Methodology
The project aims to provide a naive comparison between these three distinct methods. While tree-based methods are popular for their interpretability and stability in supervised learning, their application to survival data is less common due to the challenge of censored observations. Our analysis investigates how the recently published OST algorithm, which uses a mixed-integer optimization (MIO) approach, performs against a traditional greedy tree algorithm (RSF) and the established Cox model.

- **Models**:
  - **Cox Proportional Hazards Model**: A widely used regression model that analyzes the relationship between patient survival time and predictor variables.
  - **Random Survival Forest (RSF)**: A tree-based method that employs a top-down, greedy approach to splitting nodes.
  - **Optimal Survival Tree (OST)**: An algorithm that uses a one-step, mixed-integer optimization approach to find a globally optimal tree structure, addressing a key limitation of greedy algorithms.

- **Dataset**:
  - The study uses the Monoclonal Gammopathy of Undetermined Significance (MGUS) dataset, sourced from the survival package in R.
  - It includes data on 1,341 patients with variables such as age, sex, and the size of the monoclonal serum spike.
  - We specifically analyze the time to death.



## Key Findings
Based on our analysis, the Cox model demonstrated the best overall performance in terms of both Harrell's Concordance (C-statistic) and dynamic AUC values. The OST algorithm performed better than the RSF tree model, supporting the claim that the OST algorithm is optimal relative to traditional greedy tree-based models.

- **Concordance Statistics**: The Cox model outperformed both tree models. The OST performed better than the RSF tree.
- **Dynamic AUC**: The Cox model again yielded the best results, followed closely by the OST model. The RSF tree's dynamic AUC was notably low.


## Conclusion
We confirm the results of Bertsimas et al. in which the model yielding from the OST algorithm indeed is optimal relative to another tree-based model. We see not only the better performance in the corresponding Harrell's C statistics but also complete domination in terms of dynamic AUC values. Overall we conclude that the Cox model displays the best performance, followed by the OST, and then lastly the RSF tree model.

This comparative study is limited in scope. It considers only one dataset and a single construction of each model. A more comprehensive analysis would involve multiple datasets, varied model constructions, and additional accuracy metrics. Furthermore, issues were encountered with the `iai` package, which sometimes produced empirical CDF values instead of the expected survival probabilities, adding to the complexity of the analysis and limiting the metrics that could be evaluated.



**Authors**: Bryan Zang & Linsi Zhong
