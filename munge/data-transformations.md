## Pre-processing Data Transformations 
The following data transformations were used to allow for the desired data analysis. Following each transformation of the data, the command `SELECT * FROM employee_sales LIMIT 10;` was used to verify changes.

### Creating the data subset.
```
CREATE TABLE employee_sales
(
Attrition string, 
Department string,
JobSatisfaction int,
MonthlyIncome int
);
```


### Choosing desired variables
```
INSERT OVERWRITE TABLE employee_sales

SELECT Attrition, Department, JobSatisfaction, MonthlyIncome
FROM hremployees;
```

### Rounding Monthly Income to the nearest 1000. 
```
INSERT OVERWRITE TABLE employee_sales

SELECT Attrition, Department, JobSatisfaction, ROUND(MonthlyIncome, -3) AS MonthlyIncome
FROM employee_sales;
```

### Filtering for only employees in the Sales Department
```
INSERT OVERWRITE TABLE employee_sales

SELECT *
FROM employee_sales
WHERE Department LIKE "%Sales%";
```

### Sorting by job satisfaction from highest to lowest. 
```
INSERT OVERWRITE TABLE employee_sales

SELECT *
FROM employee_sales
ORDER BY JobSatisfaction DESC;
```

