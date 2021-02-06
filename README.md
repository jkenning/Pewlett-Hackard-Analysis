# SQL

Analysis of retirement trends at a large company with data for over 300,000 employees

## Overview of the Analysis

This project scenario involves employee research and analysis for a large company with several thousand employees. As baby boomers continue to retire at increasing rates, the company is offering retirement packages to those who meet certain criteria and is looking to fill positions that will be vacated in the near future as a result. For the employee analysis the followsing needs to be determined:

* Who will be retiring in the next few years?
* How many positions will need to be filled?

As the pre-existing company data is only available in a number of .csv files, the goal is to to build a more suitable employee database with SQL. Answering these questions through the analysis will help the company plan for future staffing needs. 

### Resources

Software used: PostgreSQL 11.10.2, pgAdmin 4.29, QuickDBD, Visual Studio Code

### Data Preparation and Wrangling

The first stage of the analysis was to create an entitiy relationship diagram (ERD) between the six .csv data files and identify the primary and foreign keys for each data table. With the database schema mapped out, the company employment data from the .csv files was imported into the database and data types were defined. Once in the databse, SQL can be used to retrieve information and help format the data for analysis by filtering, grouping, and joining the tables as necessary.

!()[]

Figure. 1 - ERD diagram for the project data

## Results

### Determining the Number of Retiring Employees by Job Position

With the ERD as reference and using SQL (queries)[], a new table was created containing all current employees who are eligible for retirement ((retirement_titles.csv)[]). Employees were listed with their most recent title and duplicates employee entries as a result of multiple titles from previous positions held were removed ((unique_titles.csv)[]). The number of titles filled by employees who are retiring was then queried and results listed ((retiring_titles.csv)[]). From these results we can observe:

* Out of 300,024 total employees listed, a significant proportion of 90,398 are eligible for retirement
* Before the removing the duplicate employees as a result of multiple past job titles, the number of entries for retiring employees was larger at 133,776
* Senior Engineer (29,414) and Senior Staff (28,254) are the most common positions held by those retiring - around double the numbers of people than the next highest job title

!()[]

Figure. 2 - Header for list of employees of retirement eligibility by job title

!()[]

Figure. 3 - Count of retiring employees by job title

### Determining the Number of Retiring Employees Eligible for a Mentorship Program

As a large percentage of the workforce is close to retiring the company wants to introduce a mentoring program, where experienced employees can step back into a part-time role and mentor new hires that are filling vacancies. Therefore the number of people eligible to be offered participation in this program was calculated using a SQL query ((mentorship_eligibility.csv)[]). From the analysis we can determine:

* Only 1549 employees are eligible to participate in the part-time mentorship program for new hires upon retirement

!()[]

Figure. 4 - Header for list of employees eligible for the mentorship program

## Summary

**How many roles will need to be filled as the "silver tsunami" begins to make an impact?**




**Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?**