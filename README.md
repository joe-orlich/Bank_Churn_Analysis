# Bank Churn Analysis

![Imgur](https://i.imgur.com/Uvw8pVV.jpg)

*Problem Statement:* Can data associated with bank clients be used to predict their churn? Can that data be anaylzed to determine which features or behaviors contribute to churn?

As data and information becomes more and more avaible to the consumer, the onus falls on companies to respond and adapt to customer needs or face the ever looming threat of a customer leaving for greener pastures. "Churn" as it is referred to in the SAAS space is becoming more and more common area of analysis within organizations old and new. One such old industry where the pain of turnover is considerablly steap is [banking](https://customerthink.com/new-customer-retention-a-fundamental-in-retail-financial-services/).

For my project I sought to address Churn for a European Bank via consumer data posted on [Kaggle](https://www.kaggle.com/sonalidasgupta95/churn-prediction-of-bank-customers) using a two pronged approach:

1. Inferential Modeling - Using simple and highly interpretable models (Logisitic Regression and Decision Tree Classifier) I was able to tune each and found the following features where the most impactful in influencing the model's classification of a novel observation.

* Age
* Being an Active Member
* Country of Origin (Germany)
* Account Balance

The effects of each aforemention feature on the baseline model is shown below.
![Log_analysis](https://i.imgur.com/XYPNoOB.png)

2. Prediction Modeling - By creating new features and employing the much more complex Ensembled Tree Models (in this case XGBoost) I was able to generate and tune a highly predictive model that could more accuarately predict customer churn.

Once the model was generated I analyzed its performance at its prebuild .5 (balanced) threshold and found it was weighted towards Precision over recall. The cost benefit of a stronger Recall model outweighed Precision in this business case, so I reviewed its performance along the threshold range and chose an optimal value based on the retainment of Balance and Products of the churned cohort.

![Threshold_analysis](https://i.imgur.com/7tPgV1l.png)

### Results
*Age* - Primary driver of churn for this dataset, indicating that as customers get older they are more likely to leave the business.

*German Balance restrictions* - There is no observations of a German account below 25k&euro; within the dataset. If account minimums are required for this subset of customers, that will artifically influence accounts closures compared to the rest of the customer base.

*Transaction Activity* - Accounts that have a record of transaction history are less likely to churn.

### Recommendations
It is hard to define concretely without more Product information, but there appears to be a clear incongruence between the older customers and current bank offering. As such exploring products/serices that more attractive to mature investors such as retirement products, scaling decling fees or attractive entrance programs for new customers i.e. their children.

If within the bounds of the EU, German and Banking legislation I suggest considering the removal of the minimum balance requirement for the German clients as it is not ownly driving churn but likely a barrier to entry as well.

#### Notebooks
[Data_Cleaning](https://github.com/joe-orlich/Bank-Churn_Analysis/blob/main/Data_Cleaning_EDA.ipynb)<br />
[Preprocessing and Feature Engineering](https://github.com/joe-orlich/Bank-Churn_Analysis/blob/main/Preprocessing_Feature_Engineering.ipynb)<br />
[Inferential Modeling](https://github.com/joe-orlich/Bank-Churn_Analysis/blob/main/Inferential_Modeling.ipynb)<br />
[Prediction_Modeling](https://github.com/joe-orlich/Bank-Churn_Analysis/blob/main/Prediction_Modeling.ipynb)
