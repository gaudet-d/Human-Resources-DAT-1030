# Data
The data is fictional human resource data created by IBM data scientists and can be found on Kaggle at: https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset.

The primary variables of interest in this data are attrition of employees working in the sales department. 

## Importing Data Query for SQL
Once downloaded the data can be uploaded into SQL from Azure HD Insight using:
```
CREATE EXTERNAL TABLE HREmployees

(
Age int, 
Attrition string, 
BusinessTravel string, 
DailyRate int, 
Department string, 
DistanceFromHome int, 
Education int, 
EducationField string, 
EmployeeCount int, 
EmployeeNumber int,
EnvironmentSatisfaction int,
Gender string,
HourlyRate int,
JobInvolvement int,
JobLevel int,
JobRole string,
JobSatisfaction int,
MaritalStatus string,
MonthlyIncome int,
MonthlyRate int,
NumCompaniesWorked int,
Over18 string,
OverTime string,
PercentSalaryHike int,
PerformanceRating int,
RelationshipSatisfaction int,
StandardHours int,
StockOptionLevel int,
TotalWorkingYears int,
TrainingTimesLastYear int,
WorkLifeBalance int,
YearsAtCompany int,
YearsInCurrentRole int,
YearsSinceLastPromotion int,
YearsWithCurrManager int
)

ROW FORMAT DELIMITED FIELDS TERMINATED BY ','
LINES TERMINATED BY '\n'
STORED AS TEXTFILE LOCATION '/Data-Storage'
TBLPROPERTIES("skip.header.line.count"="1");
```
