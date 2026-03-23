Uğurcan, haklısın; Markdown formatı bazen kopyalarken birbirine girebiliyor. Senin için her şeyi tek bir blok içinde, en sade ve en profesyonel haliyle hazırladım.

Aşağıdaki kutucuğun içindeki metni en başından en sonuna kadar tek seferde kopyala, GitHub'daki README.md dosyasının içindeki her şeyi silip bunu yapıştır:
SQL Security Investigation: Filtering for Insights
Project Overview

In this project, I acted as a cybersecurity professional investigating security incidents at a large organization. I analyzed data from the employees and log_in_attempts tables to identify potential threats and manage security updates. By using SQL filters like AND, OR, NOT, and LIKE, I retrieved specific information to help keep the organization's systems secure.
Technical Tasks & SQL Queries
Investigating After-Hours Failed Login Attempts

I reviewed login activity that occurred after business hours (18:00) to identify failed attempts. I used the AND operator to filter for values greater than '18:00' in the login_time column and 0 in the success column.
SELECT * FROM log_in_attempts WHERE login_time > '18:00' AND success = 0;
Reviewing Login Attempts on Specific Dates

A suspicious event occurred between 2022-05-08 and 2022-05-09. I used the OR operator to pull all login records from these two specific dates to analyze the traffic volume.
SELECT * FROM log_in_attempts WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';
Filtering Login Attempts Outside of Mexico

The security team confirmed that certain threats did not originate in Mexico. I used the NOT operator with the LIKE keyword and the % wildcard to exclude all attempts from Mexico (MEX and MEXICO).
SELECT * FROM log_in_attempts WHERE NOT country LIKE 'MEX%';
Identifying Marketing Employees in the East Building

To apply a security patch to specific machines, I filtered the employees table for the Marketing department and office locations starting with 'East'.
SELECT * FROM employees WHERE department = 'Marketing' AND office LIKE 'East%';
Identifying Employees in Sales or Finance

I gathered information for employees in the Sales and Finance departments for a specialized update. I used the OR operator to list all employees belonging to either department.
SELECT * FROM employees WHERE department = 'Sales' OR department = 'Finance';
Excluding IT Department from System Updates

A system-wide update was required for everyone except the IT department. I used the NOT operator to find all employees whose department was not 'Information Technology'.
SELECT * FROM employees WHERE NOT department = 'Information Technology';
Summary

Throughout this project, I demonstrated how to use SQL logical operators and pattern matching to transform raw data into actionable security insights. These queries allowed me to isolate suspicious login behavior and ensure that security protocols were correctly applied to the relevant employee machines.
