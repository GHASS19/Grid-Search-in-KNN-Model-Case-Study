# Grid Search in K-Nearest Neighbor Model Case-Study

![image](https://user-images.githubusercontent.com/86930309/228668393-7ded6d4a-7981-431c-b39a-72099b8ad380.png)

## This case study is all about using grid searches to identify the optimal parameters for a machine learning algorithm. Here I will use the Pima Indian diabetes dataset from Kaggle and KNN.

## 1. Load the necessary packages

## 2. Load the diabetes [data](https://github.com/GHASS19/Grid-Search-in-KNN-Model-Case-Study/blob/main/Data/Grid%20Search%20in%20KNN%20(Diabetes).csv)

## 3. Data Wrangling

### - Info

### - Describe

### - Replace zeros with nan for: 

 A. Pregnancies 
 
 B. Glucose
 
 C. BloodPressure 
 
 D. SkinThickness
 
 E. Insulin 
 
 F. BMI
 
 ### - Later we will use the mean or the median to fill in the nan for a particular column.

## 4. EDA

 A. This is graph of the number of women and their insulin levels when we replace the zeros with nan:

![image](https://user-images.githubusercontent.com/86930309/228964218-bed616ad-bde2-4011-a9ee-947d711f48e0.png)

Here we have an a positively skewed distribution.

B. Insulin Level column using the median:

![image](https://user-images.githubusercontent.com/86930309/228964679-c604a203-5432-4628-bf9d-b71c629f9305.png)

Using the median to fill in the nan we see that many of the women have a insulin level of just slightly under 200.

C. Skin Thickness column using nan:

![image](https://user-images.githubusercontent.com/86930309/228957515-b36804e4-d3ac-4eac-a984-93839d53c35a.png)

Many of the data points are centered around 30.

D. Skin Thickness column using the median:

![image](https://user-images.githubusercontent.com/86930309/228958133-99615dd4-c191-4e3c-80fe-566c4e7e628a.png)

No real difference between utilizing the nan and median for skin thickness.

- Heatmap of correlations between columns:

![image](https://user-images.githubusercontent.com/86930309/228965556-39bae256-1e01-432a-93c2-963a4e1d543c.png)

A. Age and Pregnancies had the highest correlation of .54

B. Glucose and Outcome had the second highest correlation of .49. Glucose has the biggest impact on our dependant variable that we want to predict.

C. The least correlated values was Diabetes Pedigree Function and Pregnancies at - .034

## 5. Model

- 70% Train / 30% Test Split

- Standard scaler, fit transform on x train/transform on x test, KNeighborsClassifier

- This is a graph of the train and test model performance by number of neighbors:

![image](https://user-images.githubusercontent.com/86930309/228968837-eff49794-58a6-45c1-a347-93ac98fb328b.png)

The highest accuracy score for our test model was at four neighbors.

- Classification Report:

A. Precision:
 
0 Outcome .85

1 Outcome .56 (Our model is having a hard time predicting if that person has diabetes)

B. Recall:

0 Outcome .76

1 Outcome .70 

C. Weighted Average:

Precision .76

Recall .74

- Grid Search Cross Validation for KNN:

Best Score: .7526440879382056

Best Parameters: n_neighbors: 31

- Grid Search Cross Validation for Random Forest Model:

Best Score: .7467289719626168

Best Parameters: n_estimators: 300

## 6. Conclusion:

- The best model was the KNN with 31 different neighbors in predicting if a person had diabetes or not. It had a slightly better accuracy score of .752644 than the random forest model.



