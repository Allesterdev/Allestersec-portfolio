## Project description

You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. You recently discovered some potential security issues that involve login attempts and employee machines.

Your task is to examine the organization’s data in their employees and log_in_attempts tables. You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.

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


