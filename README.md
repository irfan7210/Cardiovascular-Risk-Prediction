# Cardiovascular-Risk-Prediction
This project aims to use data from the ongoing cardiovascular study on residents of Framingham, Massachusetts to predict the 10-year risk of future coronary heart disease (CHD) for patients
The dataset consists of over 4,000 records and 15 attributes, including demographic, behavioral, and medical risk factors. The goal of this project is to develop a predictive model that accurately classifies patients based on their risk of CHD.

**Problem Statement**
Despite advances in medical technology, coronary heart disease remains a leading cause of death worldwide. The early detection of CHD risk is crucial for preventing and mitigating its impact. The current cardiovascular study on the residents of Framingham, Massachusetts provides an opportunity to use data to identify patients at risk of CHD. However, with over 4,000 records and 15 attributes, it is difficult to manually identify patients who are at high risk. This project aims to address this challenge by developing a predictive model that accurately classifies patients based on their risk of CHD. This will help to improve the early detection and prevention of CHD, reducing its impact on patients and the healthcare system.
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
DV
