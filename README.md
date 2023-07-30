# Cardiovascular-Risk-Prediction
This project aims to use data from the ongoing cardiovascular study on residents of Framingham, Massachusetts to predict the 10-year risk of future coronary heart disease (CHD) for patients
The dataset consists of over 4,000 records and 15 attributes, including demographic, behavioral, and medical risk factors. The goal of this project is to develop a predictive model that accurately classifies patients based on their risk of CHD.

**Problem Statement**
Despite advances in medical technology, coronary heart disease remains a leading cause of death worldwide. The early detection of CHD risk is crucial for preventing and mitigating its impact. The current cardiovascular study on the residents of Framingham, Massachusetts provides an opportunity to use data to identify patients at risk of CHD. However, with over 4,000 records and 15 attributes, it is difficult to manually identify patients who are at high risk. This project aims to address this challenge by developing a predictive model that accurately classifies patients based on their risk of CHD. This will help to improve the early detection and prevention of CHD, reducing its impact on patients and the healthcare system.

**About Data Set**

**Demographic**
* Sex: male or female("M" or "F")

* Age: Age of the patient;(Continuous - Although the recorded ages have been truncated to whole numbers, the concept of age is continuous)

**Behavioral**
* is_smoking: whether or not the patient is a current smoker ("YES" or "NO")
* Cigs Per Day: the number of cigarettes that the person smoked on average in one day.(can be
considered continuous as one can have any number of cigarettes, even half a cigarette.)
Medical( history)
* BP Meds: whether or not the patient was on blood pressure medication (Nominal)
* Prevalent Stroke: whether or not the patient had previously had a stroke (Nominal)
* Prevalent Hyp: whether or not the patient was hypertensive (Nominal)
* Diabetes: whether or not the patient had diabetes (Nominal)
Medical(current)
* Tot Chol: total cholesterol level (Continuous)
* Sys BP: systolic blood pressure (Continuous)
* Dia BP: diastolic blood pressure (Continuous)
* BMI: Body Mass Index (Continuous)
* Heart Rate: heart rate (Continuous - In medical research, variables such as heart rate though in
fact discrete, yet are considered continuous because of large number of possible values.)
* Glucose: glucose level (Continuous)
Predict variable (desired target)
* 10-year risk of coronary heart disease CHD(binary: “1”, means “Yes”, “0” means “No”) -

**Data Vizualization, Storytelling & Experimenting with charts : Understand the relationships between variables**

Data wrangling, also known as data preprocessing or data cleaning, refers to the process of transforming and preparing raw data into a suitable format for analysis. It involves cleaning, organizing, and transforming data to ensure its quality, consistency, and compatibility with the analytical tasks at hand.

Data visualization is the process of representing data and information graphically to facilitate understanding, exploration, and communication of insights. It involves creating visual representations such as charts, graphs, maps, and infographics to effectively convey patterns, trends, relationships, and comparisons present in the data.

 **Hypothesis Testing**

 * T-test: A t-test is a statistical test used to determine whether there is a significant difference between the means of two groups.The t-test is typically used when the sample size is small, or when the population standard deviation is unknown. There are several types of t-tests, including the Student's t-test and the Welch's t-test, which are used for different types of data and research questions.
 *  chi squared test: The chi-squared test is a statistical test used to determine whether there is a significant difference between the expected frequencies and the observed frequencies in one or more categories. It is commonly used to determine if there is a significant association between two categorical variables.


 **Feature Engineering & Data Pre-processing**

*  Handling Missing Values
*  Handling Outliers
*  Categorical Encoding

**Feature Manipulation & Selection**

Initially, we explored all variables using data wrangling and data visualization to explore their relationships. Based on their importance and impact on producing CHD, we selected specific features. Subsequently, during the feature manipulation stage, we combined certain variables into a single feature and eliminated some unnecessary variables.

Finally, we identified 13 independent features that significantly influence the development of CHD. To validate their importance, we utilized the Embedded method with a random forest classifier feature importance. As depicted in the graph above, all 13 features displayed some level of importance, with none of them having a zero value

**Handling Imbalanced Dataset**

Due to the highly imbalanced nature of the given data, we employed a popular technique called SMOTE (Synthetic Minority Over-sampling Technique) in our machine learning approach. SMOTE is specifically designed to address the class imbalance problem by oversampling the minority class.

To achieve class balance, SMOTE generates synthetic samples for the minority class. This process involves interpolating between existing minority class samples. By selecting two or more nearest minority class samples and taking linear combinations of their feature values, new synthetic samples are created. These synthetic samples mimic the characteristics of the existing minority class instances, effectively increasing the overall number of minority class samples and restoring balance to the class distribution.

Through the application of SMOTE, we ensured that our machine learning models were better equipped to handle imbalanced data, leading to more accurate and reliable predictions for the minority class.

![image](https://github.com/irfan7210/Cardiovascular-Risk-Prediction/assets/113547056/1bf36b1f-1e15-4965-92c6-cff94bed932a)



 **ML Model Implementation**
 In our project, we explored a diverse set of models, namely Logistic Regression, Random Forest Classifier, SVM Classifier, Decision Tree Classifier, XGBoost, and KNN Classifier. After rigorous evaluation, it became evident that the Random Forest Classifier outperformed all the other models, exhibiting the highest level of predictive accuracy.

To further enhance the model's performance, we employed advanced techniques such as hyperparameter tuning and cross-validation. These practices allowed us to fine-tune the model's parameters and validate its effectiveness on unseen data, leading to improved accuracy in our predictions.

The selection of the Random Forest Classifier for predicting the TenYearCHD was based on its outstanding performance, closely followed by the XGBoost classifier.

Upon applying the Random Forest Classifier, we achieved remarkable accuracy scores of 100% for training data and 90% for test data. For both classes (NoCHD or 0, and CHD or 1), we obtained high precision, recall, and f1-scores, indicating excellent predictive capabilities. The roc_auc_score, which measures the area under the receiver operating characteristic curve, was also commendable, with a value of 89.3% for the test data.

It's worth noting that Random Forest is an ensemble learning technique based on bagging, which involves using multiple decision trees trained on subsets of data and aggregating their outputs through majority voting. Although it proved highly effective in our project, we acknowledge that its interpretability is limited, often referred to as a "black box" model due to its lack of transparency and explanation.


**model explainability**

The Random Forest algorithm uses the bagging technique to train multiple decision tree models on different subsets of the data chosen at random. The model then predicts whether an individual has CHD or NoCHD using the majority voting scheme.

For example, if the model trains 10 decision trees and seven of them predict a result of 1 (CHD) and three of them predict a result of 0 (NoCHD) for a particular observation, the model will give a final result of 1 (CHD).

We used lime (model explainability tool), to represent the feature importance for this model.

![image](https://github.com/irfan7210/Cardiovascular-Risk-Prediction/assets/113547056/a543f1cd-a315-4bef-b27d-b4203710b868)



**Conclusion**


In conclusion, all of the features offered in the dataset are crucial and affect the likelihood of developing CHDs. Although, we can draw some very significant features, such as:


*   The likelihood of being diagnosed with heart disease rises with advancing age.

*   Another important factor that contributes to CHDs is smoking.

*   Patients who struggle with diabetes and high cholesterol have a higher risk of CHDs.

*   The likelihood of receiving a CHD diagnosis is higher in patients with Hypertension.

*    Heart rate is another reason for devolopping CHD

*    Additionally, it has been observed that those without education are more susceptible to CHD

*   CHDs are more likely to occur in patients with high blood sugar levels.

*   The risk of CHD development is higher in patients who have had "strokes."

*   The likelihood of receiving a CHD diagnosis is higher in patients with high BMIs.

*    Finally, we can say that RandomForest Classifier outperformed all other models with an accuracy of 90% and an f1-score of 0.91. It is undoubtedly the highest score we have ever received. We can therefore safely say that RandomForest Classifier offers the best solution to our problem.

