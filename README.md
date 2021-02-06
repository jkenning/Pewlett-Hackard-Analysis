# Pewlett Hackard Analysis

Analysis of retirement trends at a large company with data for over 300,000 employees

## Overview of the Analysis

This project scenario involves employee research and analysis for a large company ("Pewlett Hackard") with several thousand employees. As baby boomers continue to retire at increasing rates, the company is offering retirement packages to those who meet certain criteria and is looking to fill positions that will be vacated in the near future as a result. For the employee analysis the followsing needs to be determined:

* Who will be retiring in the next few years?
* How many positions will need to be filled?

As the pre-existing company data is only available in a number of .csv files, the goal is to to build a more suitable employee database with SQL. Answering these questions through the analysis will help the company plan for future staffing needs. 

### Resources

Software used: PostgreSQL 11.10.2, pgAdmin 4.29, QuickDBD, Visual Studio Code

### Data Preparation and Wrangling

The first stage of the analysis was to create an entitiy relationship diagram (ERD) between the six .csv data files and identify the primary and foreign keys for each data table. With the database schema mapped out, the company employment data from the .csv files was imported into the database and data types were defined. Once in the databse, SQL can be used to retrieve information and help format the data for analysis by filtering, grouping, and joining the tables as necessary.

!()[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/Resources/EmployeeDB.png]

Figure. 1 - ERD diagram for the project data

## Results

### Determining the Number of Retiring Employees by Job Position

With the (ERD)[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/DBD_text.txt] as reference and using SQL (queries)[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/Queries/Employee_Database_challenge.sql], a new table was created containing all employees who are eligible for retirement ((retirement_titles.csv)[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/Data/retirement_titles.csv]). Duplicate employee entries as a result of previous positions held were removed and employees were listed by their most recent title ((unique_titles.csv)[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/Data/unique_titles.csv]). The number of titles filled by employees who are retiring was then queried and results listed ((retiring_titles.csv)[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/Data/retiring_titles.csv]). From these results we can observe:

* Out of 300,024 total employees listed, a significant proportion of 90,398 are eligible for retirement
* Before the removing the duplicate employees as a result of multiple past job titles, the number of entries for retiring employees was larger at 133,776
* Senior Engineer (29,414) and Senior Staff (28,254) are the most common positions held by those retiring - around double the numbers of people than the next highest job title

!()[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/Resources/retirement_titles_table.png]

Figure. 2 - Header for list of employees of retirement eligibility by job title

!()[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/Resources/unique_titles.png]

Figure. 3 - Header for unique list of employees of retirement eligibility with current job titles only

!()[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/Resources/retiring_titles.png]

Figure. 4 - Count of retiring employees by job title

### Determining the Number of Retiring Employees Eligible for a Mentorship Program

As a large percentage of the workforce is close to retiring the company wants to introduce a mentoring program, where experienced employees can step back into a part-time role and mentor new hires that are filling vacancies. Therefore the number of people eligible to be offered participation in this program was calculated using a SQL query ((mentorship_eligibility.csv)[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/Data/mentorship_eligibility.csv]). From the analysis we can determine:

* Only 1549 employees are eligible to participate in the part-time mentorship program for new hires upon retirement

!()[https://github.com/jkenning/Pewlett-Hackard-Analysis/blob/main/Resources/mentorship_eligibility.png]

Figure. 5 - Header for list of employees eligible for the mentorship program

## Summary

**How many roles will need to be filled as the "silver tsunami" begins to make an impact?**

As a result of upcoming retirements, the company could potentially face over 90,000 employees (over 30% of the workforce) leaving in the near future and leaving vacant positions behind. The largest of these vacancies are anticipated to be from Senior Engineer and Senior Staff roles. 

**Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?**

Compared to the high number of vacant positions expected, retiring employees eligible for the mentorshiop program is only a fraction of that number and is unlikely to be enough experienced workers to properly train a sufficient number of newly hired and inexperienced staff. 

**Further Analysis**

Additional information on impacts to the workforce could be gained by analyzing which managers are due to retire. There are relatively few managers, sometimes managing multiple departments and different departments at various times, and their loss may impact those particular areas of the business. Additionally, salary information could be analyzed in relation to retiring employees to help forecast future company budgets and available funds for new hires.