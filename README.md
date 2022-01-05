# Absenteeism Case Study
*This is a case study where I develop a logistic regression model in Python to predict the probability of an individual being excessively absent from work as part of a Data Science course I completed with 365 Data Science.*

## Business Problem
The company in this case study is concerned that there are too many incidents of employees being absent from work and aims to identify the reasons why and predict the probability of a particular employee being absent in order implement at mitigation measures.

Absenteeism is described as being away from work during normal working hours, resulting in temporary incapacity to execute regular working activity. Some important considerations are what information the absenteeism prediction will be based on and how absenteeism will be measured. I would like to explore whether an employee presenting certain characteristics is expected to be away from work at some point in time or not. In other words, I want to know for how many working hours an employee could be away from work based on information such as how far they live from their workplace, how many children and pets they have, do they have higher education or whether they have health issues.

## Data
The [dataset](https://github.com/kmatabane/absenteeism-data-analysis/blob/main/Absenteeism_data.csv) used in this case study is based on an existing study about the prediction of absenteeism at work. Since this data was gathered and organised by others it is secondary data. This is a view of the first couple of rows:

| ID | Reason for Absence | Date | Transportation Expense | Distance to Work | Age | Daily Work Load Average | Body Mass Index | Education | Children | Pets | Absenteeism Time in Hours |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| 11 | 26 | 07/07/2015 | 289 | 36 | 33 | 239.554 | 30 | 1 | 2 | 1 |	4 |
| 36	| 0	| 14/07/2015 | 118 | 13	| 50	| 239.554	| 31	| 1	| 1	| 0	| 0 |

The features are described [here](https://github.com/kmatabane/absenteeism-data-analysis/blob/main/Feature%20Descriptions.csv).

## Pre-processing
The pre-processing steps can be summarised as follows:

1. I reduced "Reasons for Absence" to 4 groups instead of 28 to reduce dimensionality.
2. I created dummy variables for "Reasons for Absence" to prepare for the analysis.
3. I converted "Date" from str to datetime format and split it into "Day of Week" and "Month".
4. I reduced "Education" to 2 categories from 4 to try and balance the data and reduce dimensionality.  

The code can be found [here](https://github.com/kmatabane/absenteeism-data-analysis/blob/main/Absenteeism%20Preprocessing.ipynb).  
The pre-processed dataset can be seen [here](https://github.com/kmatabane/absenteeism-data-analysis/blob/main/Absenteeism_preprocessed.csv).

## Analysis
The aim of the analysis is to classify employees in terms of those who are likely to be excessively absent and those who are not. I decided logistic regression would be suitable to classify the employees. In order to measure absenteeism I used the median value from "Absenteeism Time in Hours", which was 3 hours, to create a target variable for the analysis. The measure would be the an employee who is absent for longer than 3 hours is considered excessively absent (1) and an employee absent for less than 3 hours is not (0). Using the median may not be the best approach but it is suitable and also balances the data well.

After standardising and validating the data, the model achieved a training accuracy of 76.9% and a test accuracy of 75%.  
[Model](https://github.com/kmatabane/absenteeism-data-analysis/blob/main/Absenteeism%20Model.ipynb).  
[Summary Table](https://github.com/kmatabane/absenteeism-data-analysis/blob/main/Regression%20Summary%20Table_2%20(Dimension%20Reduction).csv).  

I created a [module](https://github.com/kmatabane/absenteeism-data-analysis/blob/main/absenteeism_module.py) to [deploy](https://github.com/kmatabane/absenteeism-data-analysis/blob/main/Absenteeism%20Model%20Deploy.ipynb) the model and use it on [unseen data](https://github.com/kmatabane/absenteeism-data-analysis/blob/main/Absenteeism_new_data.csv). The predicted absenteeism can be seen [here](https://github.com/kmatabane/absenteeism-data-analysis/blob/main/Absenteeism_predictions.csv).

## Tools / Packages Used
- Python 3
- Excel 2019
- Tableau Public

## Findings
The following features were found to be strong predictors of absenteeism:
- Reasons 1, 3, 4 then 2
- Transportation Expense
- Children

From this data [visualisation](https://public.tableau.com/views/Absenteeismmodel_16147213356000/AbsenteeismModel?:language=en-US&:display_count=n&:origin=viz_share_link) employees who get infectious diseases (reason 1) are most likely to be excessively absent from work which is not surprising. Pregnant (reason 3) women are not particularly likely to be excessively absent, this could be due to the fact that they only have regular appointments and checkups which do not take up too much time. Additionally, employees who have 1 or more children are more likely to be excessively absent from work compared to those without children. This may be due to the need to address issues that arise, such as if they get sick or have to participate in school activities.  
Based on the findings above the company can research potential ways to improve the health of employees, by providing vaccinations or flu shots for example, or by allowing more flexible working hours for employees with children.
