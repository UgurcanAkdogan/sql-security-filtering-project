# SQL Security Filtering Project

## Project Description
In this project, I acted as a security professional investigating potential security incidents at a large organization. My primary goal was to analyze login attempts and employee data to identify unauthorized access and prepare for system-wide security updates. I utilized SQL to filter through large datasets and retrieve specific, actionable information.

## Environments Used
* **SQL Environment:** MariaDB / MySQL
* **Operating System:** Linux (Lab Environment)

## Analysis Tasks & SQL Queries

### 1. Retrieve After-Hours Failed Login Attempts
I investigated failed login attempts that occurred after business hours (18:00).
- **Query:** ```sql
  SELECT * FROM log_in_attempts WHERE login_time > '18:00' AND success = 0;# sql-security-filtering-project
2. Retrieve Login Attempts on Specific Dates

I reviewed all login activities for a specific 48-hour window (May 8th and 9th, 2022).

    Query: ```sql
    SELECT * FROM log_in_attempts WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';

    Logic: Used OR to include records from both specific dates.
3. Retrieve Login Attempts Outside of Mexico

The team determined that certain suspicious activity did not originate in Mexico. I filtered for all other locations.

    Query: ```sql
    SELECT * FROM log_in_attempts WHERE NOT country LIKE 'MEX%';

    Logic: Used NOT and LIKE with the % wildcard to exclude both 'MEX' and 'MEXICO'.
    4. Retrieve Employees in Marketing (East Building)

I identified specific machines in the Marketing department located in the East building for a security patch.

    Query: ```sql
    SELECT * FROM employees WHERE department = 'Marketing' AND office LIKE 'East%';

    Logic: Used LIKE 'East%' to capture all office numbers starting with that pattern.

5. Retrieve Employees in Finance or Sales

I filtered for employees in the Finance or Sales departments for a different update.

    Query: ```sql
    SELECT * FROM employees WHERE department = 'Sales' OR department = 'Finance';


6. Retrieve All Employees Not in IT

I identified all employees who are NOT in the IT department, as they still required a mandatory machine update.

    Query: ```sql
    SELECT * FROM employees WHERE NOT department = 'Information Technology';


Summary

By using SQL logical operators (AND, OR, NOT, LIKE), I was able to precisely filter organizational data to enhance security monitoring. These queries helped identify high-risk login patterns and ensured that security updates were applied to the correct employee machines, demonstrating the power of SQL in a cybersecurity workflow.
