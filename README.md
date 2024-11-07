# **Anomaly Prediction in Electricity Consumption Using Machine Learning**

**Project Overview**
---
_This project focuses on detecting and predicting anomalous electricity consumption patterns at the postcode level in the United Kingdom using advanced machine learning techniques. The study aims to provide insights that can help energy providers, policymakers, and urban planners optimize energy distribution and management. By leveraging historical consumption data and demographic statistics, the models developed in this study offer a more granular and precise understanding of electricity usage anomalies_

**Table of content**
-  [Background and Motivation](#background-and-motivation)
- [Objectives](#objectives)
- [Research Questions](#research-questions)
- [Scope and Limitations](#scope-and-limitations)
- [Methodology](#methodology)
- [Data Sources](#data-sources)
- [Results and Discussion](#results-and-discussion)
- [Error Analysis](#error-analysis)
- Future Work
- How to Run the Project
- Acknowledgements
- Author

### Background and Motivation
---
Understanding electricity consumption patterns is crucial for effective energy management and policy-making. Anomalies in electricity usage can indicate problems such as infrastructure inefficiencies, faulty equipment, or potential fraudulent activities. By predicting and addressing these anomalies proactively, energy companies can optimize resources and prevent costly issues.

Traditional methods have limitations, especially at granular levels like postcodes. Therefore, this project applies machine learning techniques to analyze and predict unusual consumption patterns while considering demographic and geographic factor

---

### Objectives

- Develop machine learning models to detect and predict anomalies in electricity consumption at the postcode level.
- Compare the performance of different outlier detection and prediction models.
- Identify the key factors that contribute to anomalous electricity consumption patterns.
- Analyze the impact of demographic features on electricity consumption predictions.
---

### Research Questions

- How effective are different outlier detection methods (Local Outlier Factor, Isolation Forest, and Ensemble Method) in identifying anomalous electricity consumption patterns?
- Which predictive model performs best for predicting anomalous electricity consumption?
- What features are most important in predicting electricity consumption anomalies?
- How do demographic factors influence anomaly predictions?
---

### Scope and Limitations

#### Scope
- Focuses on postcode-level analysis in the UK.
- Utilizes Economy 7 Meters data alongside UK Census demographic data.
- Applies machine learning algorithms to detect and predict electricity usage anomalies.

#### Limitations
- Results may not generalize to other countries.
- Relies on the accuracy of publicly available datasets from 2022.
- Predictions may not hold if there are significant shifts in electricity consumption trends.
- Privacy concerns may limit the granularity of the data.
---

### Methodology
The project follows a systematic approach:

- Data Collection: Using two datasets—postcode-level electricity consumption data and UK Census demographic data.
- Outlier Detection and Predictive Modelling: Using a combination of machine learning algorithms to detect and predict anomalies.
- Performance Evaluation: Comparing models using metrics like accuracy, precision, recall, and F1 score.
---

### Data Sources

- [Postcode Level Economy 7 Electricity 2022](https://assets.publishing.service.gov.uk/media/65b0d21ef2718c0014fb1be6/Postcode_level_economy_7_electricity_2022.csv): Contains information on electricity consumption at the postcode level, including meter counts, total consumption in kWh, and average consumption.
- [Census Postcode Estimates Table](https://www.nomisweb.co.uk/output/census/2011/Postcode_Estimates_Table_1.csv): Includes demographic data such as population, gender distribution, and number of households.
---

### **Results and Discussion**
---
## **[Link to the experiment code](https://github.com/Nedu-InfoSoft/Electricity_Consumption_Project/blob/main/EDA.ipynb)**
## **[Link to the experiment code](https://github.com/Nedu-InfoSoft/Electricity_Consumption_Project/blob/main/Analysis%20and%20Results.ipynb)**
## **[Link to full project report](https://github.com/Nedu-InfoSoft/Electricity_Consumption_Project/blob/main/Ezenwajiaku_CJ_14227905_2024.pdf)
#### **Outlier Detection Results**

The study utilized three different outlier detection methods: Local Outlier Factor (LOF), Isolation Forest, and an Ensemble Method. The findings are summarized below:

![Image](https://github.com/Nedu-InfoSoft/Electricity_Consumption_Project/blob/main/images/Performance1.jpg)

![Image](https://github.com/Nedu-InfoSoft/Electricity_Consumption_Project/blob/main/images/Agreement.jpg)

![Image](https://github.com/Nedu-InfoSoft/Electricity_Consumption_Project/blob/main/images/outlier%20plot.jpg)

- Local Outlier Factor (LOF): This method detected only 10% of the outliers, showing limited effectiveness, particularly for subtle anomalies. LOF struggled with areas that exhibited dense data clusters, often misclassifying nuanced variations as normal consumption patterns.

- Isolation Forest: Achieved a high success rate, identifying 99.6% of the injected anomalies. Its strength lies in its ability to handle high-dimensional data effectively. However, it showed limitations in distinguishing localized density differences, sometimes overlooking subtle local anomalies.
- Ensemble Method: This approach combined the strengths of LOF and Isolation Forest, successfully detecting 100% of the outliers. The Ensemble Method was able to capture both global and local anomalies, making it the most comprehensive and effective technique.

#### Implications

- Efficiency in Anomaly Detection: The superior performance of the Ensemble Method implies that energy companies could use a similar approach for more accurate anomaly detection. This could lead to more efficient monitoring and management of the electricity grid, reducing operational costs and preventing issues before they escalate.
- Targeted Interventions: The ability to identify localized anomalies allows for targeted interventions, such as addressing faulty meters or infrastructure issues in specific areas, thus improving the reliability and stability of the electricity supply.
- Revenue Protection: By detecting potential cases of electricity theft or tampering, energy providers can protect their revenue streams and reduce losses.
---

#### **Predictive Modelling Results**

The project also explored predictive models to forecast future anomalies:

![Image](https://github.com/Nedu-InfoSoft/Electricity_Consumption_Project/blob/main/images/Results.jpg)

- Random Forest: Emerged as the most effective model, achieving high accuracy and demonstrating robustness in handling complex, non-linear relationships between features. It consistently provided reliable predictions and highlighted important features like population density and electricity consumption per household.
- Decision Trees and KNN: While these models performed reasonably well, they were less robust than Random Forest. Decision Trees were more prone to overfitting, and KNN struggled with high-dimensional data.

#### Key Insights

![Image](https://github.com/Nedu-InfoSoft/Electricity_Consumption_Project/blob/main/images/feature_importances.png)

- Feature Importance: Analysis revealed that features such as population density and electricity consumption per household were the most significant predictors. This insight can help energy planners prioritize areas for monitoring and infrastructure upgrades.
- Demographic Influence: The results highlighted a strong link between demographic factors and electricity usage patterns. Postcodes with higher population densities had more consistent and predictable consumption patterns, while areas with lower population densities showed greater variability.

#### Broader Implications

- Energy Conservation: The ability to detect and predict anomalies at a granular level enables the implementation of energy conservation measures in areas where inefficiencies are most pronounced.
- Policy Development: Policymakers can use these insights to create data-driven energy policies that account for demographic trends and consumption behaviors, promoting sustainable energy usage.
---

### Error Analysis

Error analysis was a crucial part of evaluating the performance of the models. The main findings from the error analysis are outlined below:

![Image](https://github.com/Nedu-InfoSoft/Electricity_Consumption_Project/blob/main/images/misclassified_correlation_matrix.png)

- **Misclassified Instances**: An in-depth review of the misclassified data points revealed that many errors were due to overlapping characteristics between normal and anomalous consumption patterns. For instance, postcodes with medium population density sometimes exhibited usage behaviors similar to both high-density and low-density areas, making them difficult to classify accurately.

- **Feature Sensitivity**: The models were sensitive to certain features, such as population density and electricity consumption per household. The error analysis showed that slight inaccuracies or inconsistencies in these features could lead to significant prediction errors. This emphasizes the importance of careful feature engineering and selection.
- **False Positives**: The Ensemble Method, despite its high detection rate, also had a higher rate of false positives compared to simpler models. This means that it occasionally flagged normal consumption patterns as anomalous, which could lead to unnecessary interventions if applied in a real-world context. Balancing precision and recall was essential to minimize these false alarms.

