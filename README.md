# Module 7 - Pewlett Hackard Analysis

## Overview of Pewlett Hackard Analysis
--Explain the purpose of this analysis


#### The Pewlett Hackard Module was to teach the basics of Postgres SQL. We began with creating a ERD (Entity Relationship Diagram) from Quick DBD to act as a map. Once we understood the relationships of all the data, we could start creating tables, referring to the ERD to see which tables had which data we wanted and why kind of data it was. As we created the tables, we learned the basics of SQL language, like SELECT, FROM and WHERE. Once we began joining data from different tables we also learn INTO, GROUP BY, ORDER BY and the different types of JOINS. Once we had the understanding of those functions we could dive into the challenge.

#### The Pewlett Hackard Analysis taught us how to implement the different functions we learned in the module without giving us the code to reference. The goal of the analysis was to:
#### a) Determine the number of retiring employees per title
#### b) Identify employees who are eligible to participate in a mentorship program
#### In this challenge  we used all of the functions mentioned above with the addition of DISTINCT ON, which allowed us to display the most recent title for employees that were coming up on retirement, throwing out any old titles.


## Pewlett Hackard Analysis Results
--4 bullets of major points from the 2 analysis deliverables 
 * The two most common titles that are nearing retirement are both senior positions, Senior Engineer and Senior Staff. This could be good news for Pewlett Hackard mentor program as the salaries for these roles would be higher compared to non-senior roles. When these employees do transition out of their roles, the company will have extra cash to invest in the mentorship program for a smoother transition.
 
 * From 1/1/2000 - 12/31/2002 only 16,074 employees retired, 2002 is the last year data was reported so it is likely that this was reported in 2003. The time span we took into account for retirement eligible employees was also 3 years and returned 90,398 employees. I think it is unlikely that you would see a spike of 5X the number of retirees, so perhaps a survey would help the company get a better idea of who will be retiring soon rather than an arbitrary birth year range.

 * Based on our retirement eligibility criteria, there are 1,549 employees that could be mentors. If Pewlett Hackard is planning on 90,000 retirees, they may want to expand the criteria of those that are mentor eligible. A 1-to-60 mentorship ratio does not sound like a very intimate mentorship program. Additionally, this is assuming everyone that is eligible would want to be involved in the program.

 * While there are 29,414 Senior Engineers and 14,222 Engineers eligible for retirement, there are 308 Senior Engineers and 384 Engineers eligible for the mentor program. If Pewlett Hackard is to expand their mentorship criteria, they should focus on Senior Engineers, as they will have the most roles to fill but a relatively small number of mentors.
#### Retirement Count
![stacked_launch_outcomes](https://github.com/charlieburd/pewlett_hackard_analysis/blob/main/png/retirement_count.png)
#

#### Mentoring Count  
![stacked_launch_outcomes](https://github.com/charlieburd/pewlett_hackard_analysis/blob/main/png/mentorship_count.png)
#


## Pewlett Hackard Analysis Summary:
--a)Provide high-level responses to the following questions
--b)Provide two additional queries or tables that may provide more insight into the upcoming "silver tsunami."
----How many roles will need to be filled as the "silver tsunami" begins to make an impact?
----Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?
#### In t





* When you look at "retirement_titles.csv" you see there are a total of 133,776 data entries. But when you looks at "unique_titles.csv" and "retiring_titles.cvs" they only have 90,398 data entires. This difference of 43,378 are those duplicated employee's that have had more than one role with Pewlett Hackard. You realize just how many employees have moved roles. There are only 7 roles on the CSV, and of the 90,
