## Analysis Source Code

### Determining how many sales employees have attrition
```
SELECT COUNT(Attrition) AS Attrition
FROM employee_sales
WHERE Attrition LIKE "%Yes%";

SELECT COUNT(Attrition) AS Non_Attrition
FROM employee_sales
WHERE Attrition LIKE "%No%";
```

### Statistical table summaries
Summary tables were created of the monthly incomes from all employees, those with attrition and those without. 
```
SELECT AVG(MonthlyIncome) AS average_monthly_income, MIN(MonthlyIncome) AS min_monthly_income, MAX(MonthlyIncome) AS max_monthly_income
FROM employee_sales;

SELECT AVG(MonthlyIncome) AS average_monthly_income, MIN(MonthlyIncome) AS min_monthly_income, MAX(MonthlyIncome) AS max_monthly_income
FROM employee_sales
WHERE Attrition LIKE "%Yes%";

SELECT AVG(MonthlyIncome) AS average_monthly_income, MIN(MonthlyIncome) AS min_monthly_income, MAX(MonthlyIncome) AS max_monthly_income
FROM employee_sales
WHERE Attrition LIKE "%No%";
```

### Count of attrition by monthly income
```
SELECT MonthlyIncome, COUNT(MonthlyIncome) AS count
FROM employee_sales
WHERE Attrition LIKE "%Yes%"
GROUP BY MonthlyIncome;

SELECT MonthlyIncome, COUNT(MonthlyIncome) AS count
FROM hremployees
WHERE Attrition LIKE "%No%"
GROUP BY MonthlyIncome;
```
