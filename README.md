# Airline-Passenger-Satisfication
In the aviation industry, passenger satisfaction is paramount for airline success. Utilizing machine learning, this project analyzes 24 parameters to predict satisfaction, enabling airlines to proactively address customer needs, enhance operational efficiency, and elevate travel experiences.

## Methodology
The process of airline satisfaction prediction using ML typically involves the following steps:
![image](https://github.com/mozartco/Airline-Passenger-Satisfication/assets/45105115/170494a8-273d-4c12-a320-7e8c6e4bded2)

### Data Collection - Proportion of class variable:
![image](https://github.com/mozartco/Airline-Passenger-Satisfication/assets/45105115/1f23f5ed-4f6d-4676-8b2f-1b6c054c83d4)

Proportion of class satisfied: 56428/117844 = 0.47

Proportion of class neutral/dissatisfied = 61416/117844 = 0.53

### Data Preprocessing

a.	Missing Values:
Finding the rows which have null values. Out of 117844, only 364 rows were having null values. Only 0.3% data has null values so we tried two ways to handle missing values:
i. Remove it from the dataset
ii. Replace null values with mean of the column

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

b.	Handling Categorical Data:
Secondly there were 5 categorical columns which we converted into numeric.
The columns were Gender, Customer Type, Type of Travel, Customer Class, Satisfaction

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

c.	Scaling the Values:
Scaling all columns so that all values are in a similar range and no column gets any higher weight.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

d.	Feature Selection: 
There are a total 22 input columns to predict passenger satisfaction. All the columns might not be necessary. So we plotted a correlation heatmap to find out columns which have very little relation in predicting the customer satisfaction. Below is the generated heatmap.

![image](https://github.com/mozartco/Airline-Passenger-Satisfication/assets/45105115/153a1e79-6c65-42f9-b230-392c6fe67541)

Below are the correlation values for columns with customer satisfaction. The values which are very close to zero, we planned to not consider such columns since they are very less correlated to the output column.

![image](https://github.com/mozartco/Airline-Passenger-Satisfication/assets/45105115/95ff1851-ed89-43a4-98d2-7925ebcf431e)

### Model Evaluation

1. Naive Bayes

I. Naive Bayes without pre-processing
All columns were considered

Train for accuracy of NBC algo:  0.5991492146596858

Test for accuracy of NBC algo:  0.6009393286110256

Accuracy: 0.6009393286110256

F1 Score: 0.5993394039738881

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 
II. Naive Bayes with Pre-processing

Train for accuracy of NBC algo:  0.6169380918823427

Test for accuracy of NBC algo:  0.6227894045872268

Accuracy: 0.6227894045872268

F1 Score: 0.6249517803144968

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

III. Naive Bayes with cross validation

Average score:  0.39737579834269077

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

2. Logistics Regression

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
I. Logistic Regression without pre-processing
We took all the input columns in this case irrespective of the correlation value with the output variable and no categorical data was converted into numeric.

Train for accuracy of Logistic Regression:  0.87

Test for accuracy of Logistic Regression:  0.87

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

II. Logistic Regression with pre-processing
We took only columns which were selected using the correlation factor and categorical data was converted into numeric. The null rows were dropped.

Train for accuracy of Logistic Regression:  0.871955516512371

Test for accuracy of Logistic Regression:  0.8735037454629702

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

| Precision  | Recall | F-1
| ------------- | ------------- | -------- |
| 0.88  | 0.90  | 0.89 |
| 0.87  | 0.84  | 0.85 |
| | Accuracy | 0.87  |

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

3. Decision Tree

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
   
I. Decision Tree without Pre-processing:

Train for accuracy of Decision Tree:  1.0

Test for accuracy of Decision Tree:  0.94

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

II. Decision Tree with Pre-processing

We took only columns which were selected using the correlation factor and categorical data was converted into numeric. The null rows were dropped.

Input Columns: 18

Output Column: Passenger Satisfaction

Training Dataset: 80 %

Testing Dataset: 20 %

Train for accuracy of Decision Tree:  1.0

Test for accuracy of Decision Tree:  0.9438566684686076

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

III. Decision Tree with Cross Validation

We took only columns which were selected using the correlation factor and categorical data was converted into numeric. The null rows were dropped.

Input Columns: 18

Output Column: Passenger Satisfaction

Training Dataset: 80 %

Testing Dataset: 20 %

Average score:  0.4359897132530679

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Conclusion
Machine learning offers a valuable tool for airlines to predict and improve passenger satisfaction. By leveraging ML, airlines can gain valuable insights into customer preferences, identify areas for improvement, and proactively address potential dissatisfaction issues. As the aviation industry continues to evolve, ML will play an increasingly important role in enhancing customer satisfaction and driving long-term success.
