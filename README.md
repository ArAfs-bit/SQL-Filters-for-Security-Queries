# SQL Filters for Security Queries

This repository contains a collection of SQL queries aimed at enhancing system security by retrieving specific login and employee information. Each query is designed to address unique security or administrative needs, such as filtering login attempts outside business hours, retrieving employee details for department-specific updates, and more. These examples demonstrate the practical application of SQL filters for managing and securing organizational data.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Queries](#queries)
    - [After Hours Login Attempts](#after-hours-login-attempts)
    - [Login Attempts on Specific Dates](#login-attempts-on-specific-dates)
    - [Login Attempts Outside of Mexico](#login-attempts-outside-of-mexico)
    - [Retrieving Employees in Marketing](#retrieving-employees-in-marketing)
    - [Retrieving Employees in Finance or Sales](#retrieving-employees-in-finance-or-sales)
    - [Retrieving All Employees Not in IT](#retrieving-all-employees-not-in-it)
3. [Screenshots](#screenshots)
4. [Summary](#summary)

## 1.Project Overview

The purpose of this project is to demonstrate how SQL filters can be used for security-related tasks within an organization. By applying filters to login attempts and employee data, the organization can improve data security, quickly identify potential threats, and efficiently manage employee information.

## 2.Queries

### After Hours Login Attempts
Identifies login attempts that occurred outside of business hours (after 18:00). This query is essential for investigating potential security incidents that may occur outside regular working hours.

**SQL Query Example**:
```sql
SELECT * FROM log_in_attempts
WHERE login_time > '18:00' AND success = FALSE;
```

**Screenshot**:  
![After Hours Login Attempts](path_to_after_hours_login_attempts_screenshot.png)

### Login Attempts on Specific Dates
Retrieves all login attempts that took place on 2022-05-08 and 2022-05-09. This query assists in investigating any suspicious activities on specific dates.

**SQL Query Example**:

```sql
SELECT * FROM log_in_attempts
WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';
```

**Screenshot**:  
![Login Attempts on Specific Dates](path_to_login_attempts_on_specific_dates_screenshot.png)

### Login Attempts Outside of Mexico
Filters login attempts originating from countries other than Mexico. This helps identify potential unauthorized access from foreign locations.

**SQL Query Example**:

```sql
SELECT * FROM log_in_attempts
WHERE country NOT LIKE 'MEX%';
```

**Screenshot**:  
![Login Attempts Outside of Mexico](path_to_login_attempts_outside_of_mexico_screenshot.png)

### Retrieving Employees in Marketing
Fetches details of employees working in the Marketing department in the East building, which aids in department-specific updates.

**SQL Query Example**:
```sql
SELECT * FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
```

**Screenshot**:  
![Retrieving Employees in Marketing](path_to_retrieving_employees_in_marketing_screenshot.png)

### Retrieving Employees in Finance or Sales
Retrieves information on employees in either the Finance or Sales departments, enabling targeted updates for these departments.

**SQL Query Example**:
```sql
SELECT * FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```

**Screenshot**:  
![Retrieving Employees in Finance or Sales](path_to_retrieving_employees_in_finance_or_sales_screenshot.png)

### Retrieving All Employees Not in IT
Filters out employees who are not in the Information Technology department. This query is useful for general updates that exclude IT personnel.

**SQL Query Example**:
```sql
SELECT * FROM employees
WHERE department != 'IT';
```

**Screenshot**:  
![Retrieving All Employees Not in IT](path_to_retrieving_all_employees_not_in_it_screenshot.png)

## Screenshots

Screenshots of the queries and their respective outputs are included in the repository. Each screenshot showcases the query structure and a portion of the data returned to illustrate the filtered results.

## Summary

This project applies various SQL filtering techniques to login and employee data. By using the `AND`, `OR`, and `NOT` operators, as well as `LIKE` and wildcard characters, these queries provide targeted insights into login activities and departmental employee information, supporting enhanced security measures and efficient system management.
