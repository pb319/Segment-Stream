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

<!-- ### Project Workflow Summary -->

<!-- | Section Name                     | Detailed Carried Out Tasks                                                                 | Rationale                                                                                  |
|----------------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
| Introduction                     | Defined customer segmentation goals and its business value                                 | Establish context and importance of segmentation for strategic marketing                  |
| Objective                        | Set goals to identify customer segments based on income and spending score                | Focus efforts on actionable features relevant to business outcomes                        |
| Data Description                 | Listed and explained each feature in the dataset                                           | Understand available information and its relevance for clustering                         |
| Exploratory Data Analysis (EDA) | Checked missing values, performed univariate and bivariate analysis                        | Detect anomalies, understand distributions, and identify patterns                         |
| Feature Selection                | Selected 'Annual Income' and 'Spending Score' for clustering                              | These features are most indicative of financial behavior and purchasing patterns          |
| Optimal Cluster Selection        | Applied Elbow Method and Silhouette Score                                                  | Determine the ideal number of clusters to ensure model accuracy and interpretability      |
| K-Means Clustering               | Implemented K-Means algorithm with `k=7`, plotted clusters visually                        | Segment customers into behaviorally similar groups for actionable insights                |
| Cluster Interpretation           | Described behavioral characteristics of each of the 7 clusters                            | Translate statistical groupings into business-friendly segments                           |
| Statistical Inference & Testing | Conducted ANOVA, t-tests, and chi-square tests to validate cluster differences             | Ensure segments are statistically meaningful, not random groupings                        |
| Business Implications            | Mapped each cluster to a targeted business strategy                                        | Enable tailored marketing and customer relationship strategies                            |
| Conclusion                       | Summarized findings and validated impact of segmentation                                   | Reinforce business value and effectiveness of analytical approach                         |
| Future Work                      | Proposed improvements like multivariate clustering, use of other algorithms, dashboards   | Guide continued development for more robust and operationalized segmentation              | -->



## Customer Segment Analysis
![Image](https://github.com/user-attachments/assets/b7a39b45-9abd-41f3-a9ec-1289e7fd7ec0)
The the above consolidated grouped-barplot depicts the following:

| **Features** | **Central Tendency** |**Measure of Dispersion** |
|--------------|----------------------| ------------------------ |
| **Age**  | * `Cluster-1`: demography is the `oldest` (*Median - 66 Years*)<br> <br>* `Cluster-7`: demography is the `youngest` (*Median - 23.5 Years*)   |* `Cluster-4, Cluster-6` shows hight fluctuation in age distribution (twice than the rest) 
| **Income**     | * `Cluster - 1, 3 ,5` : Exhibit `Middle-Class` behavioural patterns  <br> <br>* `Cluster - 2,4` : Exhibit `Business-Class` behavioural patterns <br> <br>* `Cluster - 6,7` : Exhibit `Economy-Class` behavioural patterns |* `Cluster- 2, 3, 4`: Exhibits high fluctuations in income while `Cluster- 1, 6, 7`: have relatively lower within group fluctuations in income. 
 **Spending**     | * `Cluster-1 (lowest), Cluster-3, Cluster-5` : These customer segments have `moderate-spending habit` <br> <br>* `Cluster - 4, 6`: Spending Habit is the `lowest (one-third of moderate cluster)`<br> <br>* `Cluster-2 (highest) ,Cluster-7`: Spending habit is `very high`  | * `Cluster-1 (lowest), Cluster-3, Cluster-5` : These Clusters exhibit comparitively lower fluctuation in spending habit<br> <br>* `Cluster-4, 6`: Lowest Spending Habit with highest fluctuation (`C.V. of 82.14%`) |


#### Useful Insigts from Consolidated Description
![Image](https://github.com/user-attachments/assets/2e67594c-ef16-4ade-8fbe-3ce2656df678)
 The the above consolidated grouped-barplot depicts the following:

| **Clusters -->** | **Direct (+ve)** |**Indirect (-ve)** |**Special Observation** |
| ---------------- | ---------------- | ----------------- | ------------ |
 **Income Vs. Age**  |  Cluster- 4 | Cluster - 3, 5, 7 | Cluster- 3 [- 0.25]|
| **Spending Vs. Age**     |  Cluster - 2, 4, 5 | Cluster - 6 | Cluster- 6 [- 0.28] |
 **Spending Vs. Income**     |  Cluster - 4, 6 | Cluster - 5, 7  | Cluster- 4 [0.47]|

**[ => Note: Correlation Value < 0.1 is considered as Zero ]**
- `Cluster-1 is mostly uncorrelated with all existing featre`. Assumably, they will continue to function without any intervention and craete business.

- `Cluster-6`(Lowest Income Group but the Stediest) : With Increasing Age, Spending Decreases. While with increasing Income, Spending inceases. Income and Age seem to be uncorrelated.

- `Clsuter-4`(Business Class but the fluctuating income): Income, Age, and Spending Increases Alongside. Correlation Income and Spending is highest .

- `Cluster-5, 7(-ve income effect)`: Depicts inverse relationship among Income and Spending, i.e. with increase in income, spending decreases. 

- `Cluster- 2`: Exihibits increase in spending with increase in Age. 


#### Statistical Inference and Log-Log Model Analysis
<br/>


![Image](https://github.com/user-attachments/assets/4843d2f0-d319-40a2-b710-61a0db402263)


<br/>

##### `Log-Log Regression Model` Suggest the Following :
- Overall Model Addequacy (`Prob (F-statistic) < 0.05`): Hence Null Hypothesis (all coefficients are zero) is rejected.
- The featured (Logarithmic Transformation) log-log model can explain 16.5% of the total variation in spending score (`Adj. R-squared = 0.165`).
- `Log(Annual Income)` has found to be a significant predictor (`P>|t| = 0.013`).
-  Final Thought: **1 % increase** in `Annual Income` may lead to **2.42 % increase** in `Avg. Spending Score`.



<!-- ### Cluster Interpretation & Business Implications

| Cluster | Income Level | Spending Behavior | Age Group           | Interpretation                       | Business Implication                                              |
|---------|--------------|-------------------|----------------------|--------------------------------------|-------------------------------------------------------------------|
| 1       | High         | High              | 30s–40s              | Loyal or premium customers           | Target with loyalty programs and premium offers                  |
| 2       | Low          | Low               | 40s–50s              | Price-sensitive customers            | Offer discounts and budget-friendly options                      |
| 3       | High         | Low               | 40s–50s              | Require better engagement            | Engage through personalized recommendations                      |
| 4       | Low          | High              | Teens–20s            | Impulsive or young shoppers          | Create promotional campaigns and trendy product offerings        |
| 5       | Average      | Average           | 30s                  | Mainstream customers                 | Maintain steady engagement and upsell opportunities              |
| 6       | High         | Medium            | 30s–40s              | Upsell opportunity segment           | Nurture with exclusive bundles or perks to raise spending        |
| 7       | Medium       | Low               | 50+                  | Disengaged or indifferent segment    | Conduct re-engagement campaigns to boost activity                | -->
