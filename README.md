# Segment-Stream
A repository dedicated to the analysis of customer segmentation. This project aims to implement and evaluate various segmentation methodologies, drawing inspiration and techniques from current research in the field.

https://github.com/user-attachments/assets/57d1c1fe-3678-4573-bf1f-78648e3d3174

[🪝 Here is the Full Design](https://www.canva.com/design/DAGmeqOusx0/OXPSrhnimQZHigSzUTiVmA/edit?utm_content=DAGmeqOusx0&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

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
<br/>

![Image](https://github.com/user-attachments/assets/c6f1cae8-62fb-4f8b-8d79-981751c2de16)
[🪝 Here is the Full Design](https://www.canva.com/design/DAGmpDv_064/PeRNqrCQQSNzv4SGSGkQfw/edit?utm_content=DAGmpDv_064&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
<br/>
The the above consolidated grouped-barplot depicts the following:


| **Features**   | **Central Tendency**                                                                                                                                                                                                                   | **Measure of Dispersion**                                                                                                              |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Age**        | * `Cluster-1`: Demography is the `oldest` (*Median – 66 years*)  <br><br> * `Cluster-7`: Demography is the `youngest` (*Median – 23.5 years*)                                                                                        | * `Cluster-4`, `Cluster-6` show high fluctuation in age distribution (twice as much as the rest)                                      |
| **Income**     | * `Cluster-1, 3, 5`: Exhibit `Middle-Class` behavioural patterns  <br><br> * `Cluster-2, 4`: Exhibit `Business-Class` behavioural patterns  <br><br> * `Cluster-6, 7`: Exhibit `Economy-Class` behavioural patterns                      | * `Cluster-2, 3, 4`: Exhibit high fluctuations in income  <br><br> * `Cluster-1, 6, 7`: Have relatively lower within-group fluctuations |
| **Spending**   | * `Cluster-1 (lowest)`, `Cluster-3`, `Cluster-5`: These customer segments have `moderate-spending habits`  <br><br> * `Cluster-4, 6`: Spending habit is the `lowest` (one-third of moderate cluster)  <br><br> * `Cluster-2 (highest)`, `Cluster-7`: Spending habit is `very high` | * `Cluster-1, 3, 5`: Exhibit comparatively lower fluctuation in spending habits  <br><br> * `Cluster-4, 6`: Lowest spending with highest fluctuation (`C.V. of 82.14%`)     |

<br/>


#### Consolidated Correlation Heatmap :
![Image](https://github.com/user-attachments/assets/f1b74e8e-8c8b-478e-89f5-a83de1e2bbba)
[🪝 Here is the Design](https://www.canva.com/design/DAGnBlflQg4/fmdvmUXg8K6l1Wes5l8fEg/edit?utm_content=DAGnBlflQg4&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
#### Data Interpretation:
 The the above consolidated grouped-barplot depicts the following:



| **Clusters →**          | **Direct (+ve)**       | **Indirect (–ve)**       | **Special Observation**          |
|-------------------------|------------------------|---------------------------|----------------------------------|
| **Income vs. Age**      | Cluster-4              | Cluster-3, 5, 7           | Cluster-3 [–0.25]                |
| **Spending vs. Age**    | Cluster-2, 4, 5        | Cluster-6                 | Cluster-6 [–0.28]                |
| **Spending vs. Income** | Cluster-4, 6           | Cluster-5, 7              | Cluster-4 [0.47]                 |

**Note:** Correlation values < 0.1 are considered as zero.
<br/>
<br/>
- `Cluster-1` is mostly uncorrelated with all existing features. Assumably, they will continue to function without any intervention and create business.

- `Cluster-6` (Lowest Income Group but the Steadiest): With increasing Age, Spending decreases. While with increasing Income, Spending increases. Income and Age seem to be uncorrelated.

- `Cluster-4` (Business Class but the fluctuating income): Income, Age, and Spending increase alongside. Correlation between Income and Spending is highest.

- `Cluster-5, 7` (–ve income effect): Depicts inverse relationship between Income and Spending, i.e., with increase in income, spending decreases.

- `Cluster-2`: Exhibits increase in spending with increase in Age.


<br/>


#### Statistical Inference and Log-Log Model :
<br/>


![Image](https://github.com/user-attachments/assets/4843d2f0-d319-40a2-b710-61a0db402263)



#### Data Interpretation: 
`Log-Log Regression Model` Suggest the Following :
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


## Cluster Interpretation and Business Recommendation
https://github.com/user-attachments/assets/4fc06be9-ada1-468a-8f20-ef170b76c946

### Cluster-Level Summary

| **Cluster** | **Demographic & Profile**                                                                 | **Insights**                                                                                   | **Business Recommendation**                                                                 |
|-------------|--------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
| **Cluster-1** | Oldest (Median Age = 66), Middle-Class Income, Lowest Spending                           | Uncorrelated with all features, Stable                                                         | Minimal intervention; focus on retention and elder care offerings                           |
| **Cluster-2** | Younger age, Business-Class Income, Very High Spending                                    | Spending ↑ with Age; Positive correlation with Age                                             | Premium/luxury product offerings; ideal for aspirational targeting                           |
| **Cluster-3** | Middle-Class Income, Moderate Spending, Younger demographic                               | Income vs Age shows indirect (–ve) correlation                                                 | Offer mid-range product bundles; observe for future upscaling                                |
| **Cluster-4** | Older age, Business-Class Income, High Spending, High Variability in Age & Income         | Strongest +ve correlation between Income & Spending                                            | Priority segment for loyalty programs, exclusives, and high-value campaigns                 |
| **Cluster-5** | Middle-Class Income, Moderate Spending                                                    | Income vs Spending shows negative (–ve) correlation                                            | Introduce value-based promotions and financial advisory services                             |
| **Cluster-6** | Economy-Class Income, Lowest Spending, High Fluctuations in Age & Spending                | Age ↑ → Spending ↓; Income ↑ → Spending ↑; Income & Age uncorrelated                          | Low-cost offerings; monitor for cost sensitivity; stabilize fluctuations                     |
| **Cluster-7** | Youngest (Median Age = 23.5), Economy-Class Income, Very High Spending                    | Income vs Spending shows negative (–ve) correlation                                            | Target for youth-focused campaigns; leverage impulse behavior via digital channels           |



### Business Recommendations

| **Strategy Area**               | **Recommendation**                                                                                       |
|--------------------------------|----------------------------------------------------------------------------------------------------------|
| **Segmented Marketing**         | Customize messages per cluster (e.g., luxury to Cluster-4, budget to Cluster-6)                          |
| **Product Offering**            | Use subscription models, exclusive bundles for high-spenders (Cluster-2, 4, 7)                           |
| **Customer Lifecycle**          | Engage Cluster-7/2 early for long-term loyalty; retain Cluster-1 with age-appropriate services           |
| **Risk Minimization**           | Monitor high fluctuation clusters (4, 6) for churn or income-spending shifts                            |
| **Data-Driven Personalization** | Use log-log regression insight: 1% income ↑ ⇒ 2.42% spending ↑; micro-target income tiers                |

<br>

⚠️ [Check Out Analysis and Reporting Notebook](https://github.com/pb319/Segment-Stream/blob/main/DataAnalysis.ipynb)

> **Note**: All recommendations are grounded in the observed descriptive statistical and correlation-based cluster insights. As far as hypothesis testing is concerned, only data related to **Cluster-4** is found to be statistically significant.


## Practical Usecase
-  Let's assume, we have the data: Age=25, Income=60k$, Spending Score=55
- How we can assign a cluster to the customer??

⚠️ [Check Out Usecase-Prediction Notebook](https://github.com/pb319/Segment-Stream/blob/main/Predict.ipynb)


## Getting Started


Clone this repository to your local machine :
   ```sh
 git clone https://github.com/pb319/Segment-Stream.git
   ```

Set Up a Virtual Environment :
```sh
python3 -m venv env
source env/bin/activate  # For Linux/macOS
```

```sh
python -m venv env
env\Scripts\activate   # For Windows
```

Install Dependencies :
```sh
pip install jupyter notebook
jupyter notebook #running jupyter notebook
```
<br> 

