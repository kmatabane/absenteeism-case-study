# Absenteeism Case Study
*This is a repository where I develop a logistic regression model in Python to predict the probability of an individual being excessively absent from work.*

## Introduction
This repository showcases a case study in which I address the problem of employees being absent at a company during work hours as part of a Data Science course I completed with 365 Data Science. The business environment of today can be complicated to navigate as people have to balance their professional and personal lives and ensure that neither are adversely affected. Unfortunately it often happens that employees need to sacrifice working hours to deal with personal matters, such as in this case. The company in this case study is concerned that there are too many incidents of employees being absent from work and aims to identify the reasons for this absence and predict the probability of a particular employee being absent in order look at mitigation measures.

The business problem will be addressed from the perspective of management who have an incentive to maintain positive productivity. Specifically, we would like to explore whether a person presenting certain characteristics is expected to be away from work at some point in time or not. In other words, we want to know for how many working hours an employee could be away from work based on information such as how far they live from their workplace, how many children and pets they have, do they have higher education or whether they have health issues.

## Data
The dataset used in this case study is based on an existing study about the prediction of absenteeism at work. Since this data was gathered and organised by others it is secondary data. The data was obtained in a .csv file format. This is a view of the first few rows of the dataframe:

| ID | Reason for Absence | Date | Transportation Expense | Distance to Work | Age | Daily Work Load Average | Body Mass Index | Education | Children | Pets | Absenteeism Time in Hours |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| 11 | 26 | 07/07/2015 | 289 | 36 | 33 | 239.554 | 30 | 1 | 2 | 1 |	4 |
| 36	| 0	| 14/07/2015 | 118 | 13	| 50	| 239.554	| 31	| 1	| 1	| 0	| 0 |

Some of the features, like Date, are self explanetory. Others, not so much. Reason for absence contains data from a survey question which has been converted into a number between 1 and 20. Daily work load average describes the xxx. Education is a number from 1 to 3 indicating level of eduction from matric to xxx. The target variable in this dataset is the Absenteeism Time in Hours which we will try and predict.

## Pre-processing
The dataset contains no null values
1. Ask
2. Prepare
3. Process
4. Analyse
5. Share
6. Review

## Analysis
Linear Regression

## Tools / Packages Used
- Python
- Excel
- Tableau

## Findings

## References
