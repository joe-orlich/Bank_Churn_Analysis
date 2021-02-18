# Bank Churn Analysis

![Imgur](https://imgur.com/jSbDZ7X)

*Problem Statement:* Can data associated with bank clients be used to predict their churn? Can that data be anaylzed to determine which features or behaviors contribute to churn?

As data and information becomes more and more avaible to the consumer, the onus falls on companies to respond and adapt to customer needs or face the ever looming threat of a customer leaving for greener pastures. "Churn" as it is referred to in the SAAS space is becoming more and more common area of analysis within organization new and old. One such old industry where the pain of turnover is considerablly steap is [banking](https://customerthink.com/new-customer-retention-a-fundamental-in-retail-financial-services/).

For my project I sought to address this for a company using a two pronged approach:

1. Inferential Modeling - Using simple and highly interpretable models (Logisitic Regression and Decision Tree Classifier) I was able to tune each and found the following features where the most impactful in influencing the model's classification of a novel observation.

* Age
* Being an Active Member
* Country of Origin (Germany)
* Account Balance

The effects of each aforemention feature on the baseline model is shown below.
![Log_analysis](https://i.imgur.com/XYPNoOB.png)

2. Prediction Modeling - By creating new features and employing the much more complex Ensembled Tree Models (in this case XGBoost) I was able to generate and tune highly predictive model that could more accuarately predict customer churn.

Once the model was generated I analyzed its performance at its prebuild .5 (balanced) threshold and found it was weighted towards Precision over recall. The cost benefit of a stronger Recall model outweighed Precision in this business case, so I reviewed its performance along the threshold range and chose an optimal value based on the retainment of Balance and Products being used by the churned cohort.

![Threshold_analysis](https://i.imgur.com/7tPgV1l.png)
