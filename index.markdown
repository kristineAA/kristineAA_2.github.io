---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: "Fraudules Transactions in The United States"
---

In order to investigate trends around credit card fraud, a data set containing information about 1.3 million credit card transactions in the US, as well as age, gender and location of the people who have been victims for the fraud credit card transmissions. Furthermore it contains attributes with information about the timestamp of the transaction, the credit card number used for the transaction, the name of the merchant where the transaction occurred and the category of the merchant (e.g., grocery, entertainment, gas).

Using this data, we seek to determine whether distinct patterns emerge in credit card fraud incidents. Specifically, we aim to investigate if there are any characteristics identifying who is more frequently targeted and whether fraud occurrences spike during the holiday season. 


## Fraud occurrences during the holiday season

For instance, West Midlands Police recently published an article titled *“Make sure you have a #FraudFreeXmas: Watch out for these 12 fraud types this Christmas”*[1], which notes that fraudsters often exploit the festive mood to deceive unsuspecting individuals. Although this insight comes from a UK source, our analysis will explore if such trends are also evident in the US.

<figure style="width: 80%; margin: auto;">
    <img src="Assets/calendar_plot_fraun.png" alt="Calender_Plot_fraud" style="width: 100%;" />
    <figcaption>Figure 1: Calendar heatmaps showing daily counts of fraudulent transactions in 2019 and 2020. The color intensity indicates the number of fraud cases per day, with red denoting higher activity. Notable spikes in late December suggest increased fraud risk around the holiday season, especially on December 23.</figcaption>
</figure>

An examination of the calendar plot for fraudulent transactions above reveals two standout days in December with notably high fraud counts compared to many days with little or no activity. This pattern suggests that, much like trends observed by UK authorities, fraudsters in the US may be capitalizing on the festive season. However, a comprehensive calendar plot of all transactions, which can be seen below, shows that December inherently experiences a higher volume of activity relative to other months. As a result, while the absolute number of fraudulent transactions rises during December, the proportion of fraud relative to the overall transaction volume might remain constant. A particularly striking spike on December 23 may indicate that last-minute shoppers—under pressure from holiday deadlines—could be less vigilant, rendering them more susceptible to fraud.

<figure>
  <img src="Assets/calendar_plot_all_transactions.png" alt="Calender_Plot_all" />
  <figcaption>Figure 2: Calendar heatmaps showing daily counts of all transactions in the dataset in 2019 and 2020. The plots reveal a naturally higher transaction volume in December, particularly around the holidays, which may explain the observed increase in fraudulent activity during this period..</figcaption>
</figure>

Given the presence of random fraud spikes and a dataset spanning only 17 months, it is challenging to draw definitive conclusions about seasonal trends based solely on specific dates. Therefore, it is worthwhile to explore additional dimensions. One approach is to analyze which fraud categories predominate over the course of the year and, more specifically, which types peak during the Christmas season.

<figure>
    <iframe src="Assets/transactions_by_month_and_category.html" width="100%" height="600" style="border:none;"></iframe>
    <figcaption>Figure 3: Monthly transaction volumes by category from January 2019 to May 2020. The stacked bar chart shows that transactions are broadly distributed across categories, with a significant spike in December 2019. Categories like grocery_pos and shopping_net consistently contribute a large share, aligning with patterns seen in fraudulent activity. </figcaption>
</figure>

<div style="display: flex; gap: 20px;">
  <figure style="flex: 1;">
    <iframe src="Assets/transactions_by_month_and_category.html" width="50%" height="600" style="border:none;"></iframe>
    <figcaption>Figure 3a: Monthly transaction volumes by category from January 2019 to May 2020. The stacked bar chart shows that transactions are broadly distributed across categories, with a significant spike in December 2019. Categories like grocery_pos and shopping_net consistently contribute a large share, aligning with patterns seen in fraudulent activity. </figcaption>
  </figure>

  <figure style="flex: 1;">
    <iframe src="Assets/fraud_transactions_by_month_and_category.html" width="50%" height="600" style="border:none;"></iframe>
    <figcaption>Figure 3b: Monthly fraudulent transaction volumes by category from January 2019 to May 2020. The chart highlights that grocery_pos, shopping_net, and shopping_pos consistently dominate fraudulent activity across months, rather than being limited to seasonal spikes.</figcaption>
  </figure>
</div>

Above, an initial interactive plot suggests that overall transactions are fairly evenly distributed across 13 categories. Yet, the bar chart below focusing on fraudulent transactions highlights that the grocery_pos and shopping_net categories stand out. When examining a dedicated interactive plot of fraudulent transactions, it becomes clear that the main categories are grocery_pos, shopping_net, and shopping_pos. Although one might infer that increased gift or grocery shopping during the holidays drives these spikes, which could confirm the idea that a trend of fraud occurs more in the holidays, further analysis shows that these categories not only dominate in December but are consistently prevalent throughout the year. 

<figure>
  <img src="Assets/fraud_transactions_by_category.png" alt="Fraud_by_Category" />
  <figcaption>Figure 4: Bar chart showing the number of fraudulent transactions by merchant category. Grocery_pos and shopping_net lead by a significant margin, indicating these categories are prime targets for fraud regardless of season, with other categories like misc_net and shopping_pos also showing notable counts. </figcaption>
</figure>


## Victim characteristics
In a study conducted by the Victim Commissioner titled *"Who Suffers Fraud?" Understanding the Fraud Victim Landscape*[2], several characteristics were identified as potential risk factors that increase an individual's vulnerability to fraud in the UK. These factors include age, socio-economic status, relationship status, ethnicity, life events, immigration, technology usage, social networks, previous victimization, and a range of psychological variables.

Utilizing the provided dataset, we can now assess whether these characteristics similarly act as risk factors in the US context. In particular, our investigation will focus on examining gender, age, and place of residence as potential indicators of an increased risk of experiencing fraud.

### Age-Group
When analyzing fraud incidents across different age groups, the data clearly indicates that older individuals are at a greater risk of becoming fraud victims. For example, nearly 1% of transactions made by individuals aged 86–100 are fraudulent, compared to less than 0.5% for those aged 36–55. This disparity strongly suggests that age is a significant risk factor, with older people being more vulnerable to fraud than their middle-aged counterparts.

| Age group | Transactions | Fraudulent transactions | % fraudulent transactions |
|-----------|--------------|--------------------------|----------------------------|
| 19 – 25   | 18,140       | 118                      | 0.650%                     |
| 26 – 35   | 178,660      | 1,088                    | 0.601%                     |
| 36 – 45   | 286,324      | 1,273                    | 0.445%                     |
| 46 – 55   | 288,973      | 1,233                    | 0.427%                     |
| 56 – 65   | 188,480      | 1,403                    | 0.744%                     |
| 66 – 75   | 135,539      | 907                      | 0.669%                     |
| 76 – 85   | 74,397       | 517                      | 0.695%                     |
| 86 – 100  | 67,891       | 66                       | 0.916%                     |

### Gender
The left plot on below displays the number of fraudulent transactions by gender and reveals an almost equal distribution between males and females. This suggests that, in absolute terms, fraudulent activity does not heavily favor one gender over the other. In contrast, the right plot shows the distribution of non-fraudulent transactions by gender, and it indicates that the overall dataset includes slightly more female transactions—exceeding male transactions by just over 100,000.
This discrepancy implies that, while the raw numbers of fraud cases are similar between genders, men might be proportionately more vulnerable to fraud given that they represent a smaller share of the overall transaction volume.

<figure>
  <img src="Assets/gender_dist.png" alt="Fraud_by_gender" />
  <figcaption>Figure 5: Comparison of fraudulent and non-fraudulent transactions by gender. While fraudulent transactions are nearly equal between males and females, non-fraudulent transactions are more common among females. This suggests men may be disproportionately targeted by fraud relative to their overall transaction activity. </figcaption>
</figure>

### Place of living
To assess whether geographical location influences the risk of fraud victimization, we examined a map visualizing fraudulent transaction occurrences which can be seen below. The map suggests that the East Coast experiences more fraud incidents compared to the West Coast. However, there are limitations to this visualization. For instance, when multiple fraudulent transactions occur in one location, they may not be distinctly visible. Additionally, the map does not adjust for variations in population size across different areas, which could affect the interpretation of these trends.

<figure>
    <iframe src="Assets/map.html" width="100%" height="600" style="border:none;"></iframe>
    <figcaption>Figure 6: Map of fraudulent transaction occurrences across the United States. The concentration of red markers suggests higher fraud activity on the East Coast, though interpretation is limited by marker overlap and lack of normalization for population density. </figcaption>
</figure>

Examining the percentage of fraudulent transactions by state in the below table provides a clearer perspective. Our analysis reveals that the states with the highest fraud percentages are Delaware, Rhode Island, Alaska, Nevada, Colorado, and Tennessee, while those with the lowest percentages are Hawaii, Montana, Connecticut, and Idaho. This finding contradicts the initial map's impression—which appeared to show higher fraud concentrations exclusively along the East Coast—as it shows that high percentages also occur on the West Coast, and some Eastern states may even have lower rates. This inconsistency highlights the importance of considering state-specific factors, such as overall transaction volume and population, to fully understand the geographic trends in fraud.

| State code | State         | % Fraudulent | Transactions | Fraudulent transactions |
|------------|---------------|---------------|--------------|--------------------------|
| DE         | Delaware      | 100.00%       | 9            | 9                        |
| RI         | Rhode Island  | 2.84%         | 528          | 15                       |
| AK         | Alaska        | 1.77%         | 2036         | 36                       |
| NV         | Nevada        | 0.87%         | 5381         | 47                       |
| CO         | Colorado      | 0.85%         | 13217        | 113                      |
| TN         | Tennessee     | 0.83%         | 16773        | 140                      |
| HI         | Hawaii        | 0.29%         | 2443         | 7                        |
| MT         | Montana       | 0.28%         | 11243        | 32                       |
| CT         | Connecticut   | 0.22%         | 7351         | 16                       |
| ID         | Idaho         | 0.21%         | 5302         | 11                       |

## Final thoughts
Throughout our analysis, it became clear that the dataset's limited time span of 17 months is insufficient to draw definitive conclusions about seasonal trends, even though some data points allow for initial observations about event-specific patterns. In particular, we cannot conclusively confirm or refute whether holiday periods are associated with higher fraud rates. 

However, the dataset does contain enough transactional data to identify potential risk factors, such as age, gender and place of living.


# Literature
* [1] Sarah Poppleton, Kitty;  Lymperopoulou, Julian Molina; "Who suffers fraud? Understanding the fraud victim landscape"; 13/10/2021; https://victimscommissioner.org.uk/document/who-suffers-fraud-understanding-the-fraud-victim-landscape/
* [2] West Midlands Police; "Make sure you have a #FraudFreeXmas: Watch out for these 12 fraud types this Christmas"; 18/12/2024; https://www.westmidlands.police.uk/news/west-midlands/news/news/2024/december/make-sure-you-have-a-fraudfreexmas-watch-out-for-these-12-fraud-types-this-christmas/
