# Scenario

You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. You recently discovered some potential security issues that involve login attempts and employee machines.

Your task is to examine the organization’s data in their employees and log_in_attempts tables. You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.

## Project description

This project demonstrates how SQL filters can be applied to investigate suspicious login activity and manage employee machine updates. By writing targeted queries, I was able to isolate failed login attempts, review events on specific dates, and exclude or include records based on country and department criteria. The exercises showcase practical use of `WHERE`, `AND`, `OR`, `NOT`, and `LIKE` operators to retrieve relevant data efficiently.

## Retrieve after hours failed login attempts

You recently discovered a potential security incident that occurred after business hours. To investigate this, you need to query the log_in_attempts table and review after hours login activity. Use filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00. (The time of the login attempt is found in the login_time column. The success column contains a value of 0 when a login attempt failed; you can use either a value of 0 or FALSE in your query to identify failed login attempts.)

To search the database for login attempts that occurred after 18:00, I used the following query: 
```sql
SELECT * 
FROM log_in_attempts 
WHERE login_time > '18:00:00' 
  AND success = 0;
```
This query ensures that only login attempts after 6 PM are displayed, and by setting success = 0, it filters exclusively for failed attempts. In MariaDB, boolean values can be represented interchangeably as FALSE/TRUE or 0/1. However, caution is required because other database engines may enforce stricter boolean conventions.

## Retrieve login attempts on specific dates

A suspicious event occurred on 2022-05-09. To investigate this event, you want to review all login attempts which occurred on this day and the day before. Use filters in SQL to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08. (The date of the login attempt is found in the login_date column.)

To isolate the suspicious events that occurred on May 8 and May 9, 2022, I used the following query:

```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09'
   OR login_date = '2022-05-08';
```
By using the OR condition, the query ensures that both dates are included in the results. This way, the database returns all login attempts that occurred on those two days, allowing a detailed review of activity surrounding the suspicious event.

> **Fact:**  
> You can filter multiple values using either `OR` or the `IN` clause.  
> Example:  
> ```sql
> SELECT *
> FROM log_in_attempts
> WHERE login_date IN ('2022-05-08', '2022-05-09');
> ```  
> This compact format is equivalent to using `OR` and is often preferred for readability.

## Retrieve login attempts outside of Mexico

There’s been suspicious activity with login attempts, but the team has determined that this activity didn't originate in Mexico. Now, you need to investigate login attempts that occurred outside of Mexico. Use filters in SQL to create a query that identifies all login attempts that occurred outside of Mexico. (When referring to Mexico, the country column contains values of both MEX and MEXICO, and you need to use the LIKE keyword with % to make sure your query reflects this.)

To investigate suspicious login activity that did not originate in Mexico, I queried the `log_in_attempts` table and applied filters to exclude records where the `country` column contains values related to Mexico. Since the column may contain both `MEX` and `MEXICO`, I used the `LIKE` keyword with `%` to capture all variations.

The SQL query used was:

```sql
SELECT *
FROM log_in_attempts
WHERE country NOT LIKE 'MEX%';
```
This query returns all login attempts where the country value does not begin with MEX. By using NOT LIKE 'MEX%', the filter excludes both MEX and MEXICO, ensuring that only login attempts from outside of Mexico are included in the results. This allows the investigation to focus on external sources of suspicious activity.

## Retrieve employees in Marketing

To identify employee machines in the Marketing department located in the East building, I queried the `employees` table and applied two filters:

1. **Department filter**: The `department` column contains values that include "Marketing". Using the `LIKE` keyword ensures that all variations of Marketing are captured (e.g., "Marketing", "Digital Marketing").
2. **Office filter**: The `office` column contains values such as "East-170" or "East-320". Using `LIKE 'East%'` ensures that only offices in the East building are included.

The SQL query used was:

```sql
SELECT *
FROM employees
WHERE department LIKE 'Marketing'
  AND office LIKE 'East%';
```
This query returns all employees whose department includes "Marketing" and whose office is located in the East building. By combining both conditions with the AND operator, the results are narrowed down to the specific set of employee machines that require security updates.

## Retrieve employees in Finance or Sales

To identify employee machines in the Sales and Finance departments, I queried the `employees` table and applied filters to the `department` column. Since the column contains values that include "Sales" and "Finance", I used the `LIKE` keyword to capture all variations (e.g., "Sales", "Regional Sales", "Finance", "Corporate Finance").

The SQL query used was:

```sql
SELECT *
FROM employees
WHERE department LIKE 'Sales'
   OR department LIKE 'Finance';
```
This query returns all employees whose department includes either "Sales" or "Finance". By combining the conditions with the OR operator, the results include both groups of employees. This ensures that the dataset covers all machines in these two departments, allowing the team to perform the required security updates.

## Retrieve all employees not in IT

To identify employee machines that still require the update, I queried the `employees` table and excluded those in the Information Technology department. Since the `department` column contains values that include "Information Technology", I used the `NOT LIKE` keyword to filter out this department.

The SQL query used was:

```sql
SELECT *
FROM employees
WHERE department NOT LIKE 'Information Technology';
```
This query returns all employees whose department is not "Information Technology". By applying the NOT LIKE condition, the results exclude IT employees and focus only on machines in other departments that still need the update. This ensures the security update is applied to the correct set of employee machines.

> **Fact:**  
> You can make the filter more flexible by using `NOT LIKE 'Info%'` instead of `NOT LIKE 'Information Technology'`.  
> Example:  
> ```sql
> SELECT *
> FROM employees
> WHERE department NOT LIKE 'Info%';
> ```  
> This approach excludes any department name starting with "Info", such as "Information Technology".  
> ⚠️ However, be cautious: if your database contains other departments that also begin with "Info" (e.g., "Infrastructure"), they will be excluded as well. Always verify the actual department values before applying broader filters.

## Summary

Throughout the tasks, I created SQL queries to filter login attempts by time, date, and country, as well as to identify employees in specific departments or buildings. Each query was designed to reflect real-world scenarios, such as investigating security incidents or preparing machines for updates. Together, these exercises highlight how SQL filtering techniques can be used to extract meaningful information from large datasets and support security and operational decision-making.
