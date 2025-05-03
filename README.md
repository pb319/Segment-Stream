# Segment-Stream
A repository dedicated to the analysis of customer segmentation. This project aims to implement and evaluate various segmentation methodologies, drawing inspiration and techniques from current research in the field.


## Problem Statement
- A shopping mall aims to improve its marketing strategies and customer engagement.
- The mall currently lacks a deep understanding of its customers, including their diverse profiles and purchasing habits.
- There's also a need to assess the effectiveness of previous marketing campaigns.
- This lack of data-driven insights makes it difficult for the mall to make informed decisions about resource allocation and targeted promotions.

## Stakeholders Expectation

- Stakeholders expect actionable recommendations derived from the data analysis that can be directly implemented to improve marketing strategies and customer engagement.

- They anticipate measurable outcomes resulting from the project, such as increased revenue, improved customer loyalty, and a more efficient allocation of marketing resources.


## Data Collection
 [Mall Customers Segmentation](https://www.kaggle.com/datasets/abdallahwagih/mall-customers-segmentation)

### Overview

    information, annual income, and spending habits. 
    The Mall Customers Dataset provides data on 200 individuals who visit a mall, including demographic 


### Columns Description

    CustomerID: A unique identifier for each customer (integer).
    Genre: The gender of the customer (Male/Female).
    Age: The age of the customer (integer).
    Annual Income (k$): Annual income of the customer in thousands of dollars (integer).
    Spending Score (1-100): A score assigned by the mall based on customer behavior and spending patterns (integer).

The the above consolidated grouped-barplot depicts the following:
| **Features** | **Central Tendency** |**Measure of Dispersion** |
|--------------|----------------------| ------------------------ |
| **Age**  | * `Cluster-1`: demography is the `oldest` (*Median - 66 Years*)<br> <br>* `Cluster-7`: demography is the `youngest` (*Median - 23.5 Years*)   |* `Cluster-4, Cluster-6` shows hight fluctuation in age distribution (twice than the rest) 
| **Income**     | * `Cluster - 1, 3 ,5` : Exhibit `Middle-Class` behavioural patterns  <br> <br>* `Cluster - 2,4` : Exhibit `Business-Class` behavioural patterns <br> <br>* `Cluster - 6,7` : Exhibit `Economy-Class` behavioural patterns |* `Cluster- 2, 3, 4`: Exhibits high fluctuations in income while `Cluster- 1, 6, 7`: have relatively lower within group fluctuations in income. 
 **Spending**     | * `Cluster-1 (lowest), Cluster-3, Cluster-5` : These customer segments have `moderate-spending habit` <br> <br>* `Cluster - 4, 6`: Spending Habit is the `lowest (one-third of moderate cluster)`<br> <br>* `Cluster-2 (highest) ,Cluster-7`: Spending habit is `very high`  | * `Cluster-1 (lowest), Cluster-3, Cluster-5` : These Clusters exhibit comparitively lower fluctuation in spending habit<br> <br>* `Cluster-4, 6`: Lowest Spending Habit with highest fluctuation (`C.V. of 82.14%`) |


 The the above consolidated grouped-barplot depicts the following:

| **Clusters -->** | **Direct (+ve)** |**Indirect (-ve)** |**Special Observation** |
| ---------------- | ---------------- | ----------------- | ------------ |
 **Income Vs. Age**  |  Cluster- 4 | Cluster - 3, 5, 7 | Cluster- 3 [- 0.25]|
| **Spending Vs. Age**     |  Cluster - 2, 4, 5 | Cluster - 6 | Cluster- 6 [- 0.28] |
 **Spending Vs. Income**     |  Cluster - 4, 6 | Cluster - 5, 7  | Cluster- 4 [0.47]|

**[ => Note: Correlation Value < 0.1 is considered as Zero ]**
- `Cluster-1 is mostly uncorrelated with any existing featre`. Assumably, they will continue to function without any intervention and craete business.
